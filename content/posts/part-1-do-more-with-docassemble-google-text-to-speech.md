+++ 
date = 2022-05-16T00:06:18+08:00
title = "[Part 1] Do more with docassemble: Google Text to Speech"
description = "I explore how to extend the capabilities of docassemble by integrating Google Text to Speech, demonstrating how to call an API, get a response, and provide it to a user. This post includes a practical example and a link to the completed code on GitHub."
slug = "part-1-do-more-with-docassemble-google-text-to-speech"
tags = ["docassemble", "Google Text to Speech", "API Integration", "LegalTech", "Automation", "Programming", "Tutorial"]
series = ["Do more with Docassemble: Google Text to Speech"]
+++

![Feature image](https://raw.githubusercontent.com/houfu/lovelawrobots-content/master/2022/05/docassemble-googleTTS-1.png)

Most people associate docassemble with assembling documents using guided interviews. That’s in the name, right? The program asks a few questions and out pops a completed form, contract or document. However, [the documentation](https://docassemble.org/) makes it quite clear that docassemble can do more:

> Though the name emphasizes the document assembly feature, **docassemble** interviews do not need to assemble a document; they might submit an application, direct the user to other resources on the internet, [store](https://docassemble.org/docs/functions.html#storage) user input, interact with [APIs](https://docassemble.org/docs/functions.html#google%20sheets%20example), or simply provide the user with information.

In this post, let’s demonstrate how to use docassemble to call an API, get a response and provide it to a user. You can check out the completed code on [Github](https://github.com/houfu/docassemble-googleTTS/tree/blog) (NB: the git branch I would recommend for following this post is `blog`. I am actively using this package, so I may add new features to the main branch that I don’t discuss here.)

## Problem Statement

I do a lot of internal training on various legal and compliance topics. I think I am a pretty all right speaker, but I have my limitations — I can’t give presentations 24/7, and my performance varies in a particular session. Wouldn’t it be nice if I could give a presentation at any time engagingly and consistently?

I could record my voice, but I did not like the result.

I decided to use a text-to-speech program instead, like the one provided by Google Cloud Platform. I created a computerised version of my speech in the presentation. My audience welcomed this version as it was more engaging than a plain PowerPoint presentation. Staff whose first language was not (Singapore) English also found the voice clear and understandable.

The [original code](https://github.com/houfu/TTS-experiments) was terminal based. I detailed my early exploits in [this blog post last year](let-the-robots-do-the-talking-exploring-tts/). The script was great for developing something fast. However, as more of my colleagues became interested in incorporating such speech in their presentations, I needed something more user-friendly.

I already have a docassemble installation at work, so it appears convenient to work on that. The program would have to do the following:

  * Ask the user what text it wants to transform into speech
  * Allow the user to modify some properties of the speech (speed, pitch etc.)
  * Call Google TTS API, grab the sound file and provide it to the user to download

<video controls  >
<source src="https://res.cloudinary.com/lovelawrobots/video/upload/f_auto:video,q_auto/v1/blog-videos/mdzntfhjg4srzizlwz3j" type="video/mp4">
Your browser does not support the video tag.
</video>


## Assumptions

To follow this tutorial, you will need the following:

  * A working docassemble install. You can start up an instance on your laptop by following [these instructions](https://docassemble.org/docs/docker.html#starting).
  * A Google Cloud Platform (GCP) account with a service account enabled for Google TTS. You can [follow Google’s instructions here](https://cloud.google.com/text-to-speech/docs/create-audio-text-command-line) to set one up.
  * Use the [Playground](https://docassemble.org/docs/playground.html) provided in docassemble. If you'd like to use an IDE, you can, but I wouldn’t be providing instructions like creating files to follow a docassemble package's directory structure.
  * Some basic knowledge about docassemble. I wouldn’t be going through in detail how to write a block. If you can follow the [Hello World example](https://docassemble.org/docs/helloworld.html), you should have sufficient knowledge to follow this tutorial.



## A Roadmap of this Tutorial

In the next part of this post, I talk about the thinking behind creating this interview and how I got the necessary information (off the web) to make it.

In [Part 2](/posts/part-2-do-more-with-docassemble-start-a-project-and-write-a-few-questions/), we get the groundwork done by creating four pages. This provides us with a visual idea of what happens in this interview. 


In [Part 3](/posts/part-3-do-more-with-docassemble-getting-work-done-in-a-background-action/), I talk about docassemble's background action and why we should use it for this interview. Merging the visual requirements with code gives us a clearer picture of what we need to write.

In [Part 4](/posts/part-4-do-more-with-docassemble-calling-google-text-to-speech/), we work with an external API by using a client library for Python. We install this client library in our docassemble's python environment and write a python module.

In [Part 5](/posts/part-5-do-more-with-docassemble-provide-an-audio-file-for-your-user-to-download/), we finish the interview by coding the end product: an audio file in the guise of a DAFile. You can run the interview and get your text transformed into speech now! I also give some ideas of what else you might want to do in the project. 


## Part 1: Familiarise yourself with the requirements

To write a docassemble interview, it makes sense to develop it backwards. In a simple case, you would like docassemble to fill in a form. So you would get a form, figure out its requirements, and then write questions for each requirement.

An API call is not a contract or a form, but your process is the same.

Based on Google’s [quickstart](https://github.com/googleapis/python-texttospeech/blob/HEAD/samples/snippets/quickstart.py), this is the method in the Python library which synthesises speech.
    
 ```python   
    # Set the text input to be synthesized
        synthesis_input = texttospeech.SynthesisInput(text="Hello, World!")
    
    # Build the voice request, select the language code ("en-US") and the ssml
    # voice gender ("neutral")
        voice = texttospeech.VoiceSelectionParams(
            language_code="en-US", 
            ssml_gender=texttospeech.SsmlVoiceGender.NEUTRAL
        )
    
    # Select the type of audio file you want returned
        audio_config = texttospeech.AudioConfig(
            audio_encoding=texttospeech.AudioEncoding.MP3
        )
    
    # Perform the text-to-speech request on the text input with the selected
    # voice parameters and audio file type
        response = client.synthesize_speech(
            input=synthesis_input, voice=voice, audio_config=audio_config
        )
```    

From this example code, you need to provide the program with the input text (synthesis input), the voice, and audio configuration options to synthesise speech.

That looks pretty straightforward, so you might be tempted to dive into it immediately.

However, I would recommend going through the documents provided online.

  * docassemble provides some of the most helpful documentation, great for varying proficiency levels.
  * Google’s Text To Speech’s documentation is more typical of a product offered by a big tech company. Demos, use cases and guides help you get started quickly. You’re going to have to [dig deep](https://cloud.google.com/python/docs/reference/texttospeech/latest) to find the one for Python. It receives less love than the other programming languages.



Reading the documentation, especially if you want to use a third-party service, is vital to know what’s available and how to exploit it fully. For example, going through the docs is the best way to find out what docassemble is capable of and learn about existing features — such as [transforming a python list of strings into a human-readable list](https://docassemble.org/docs/functions.html#comma_and_list) complete with an “and”.

You don’t have to follow the quickstart if it does not meet your use case. Going through the documentation, I figured out that I wanted to give the user a choice of which voice to use rather than letting Google select that for me. Furthermore, audio options like how fast a speaker is will be handy since non-native listeners may appreciate slower speaking. Also, I don’t think I need the user to select a specific file format as mp3s should be fine.

## Let’s move on!

This was a pretty short one. I hope I got you curious and excited about what comes next. Continue to the next part, where we get started on a project!

👉🏻 **[Head to the next part of this tutorial!](/posts/part-2-do-more-with-docassemble-start-a-project-and-write-a-few-questions/)**
