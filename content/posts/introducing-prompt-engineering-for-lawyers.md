+++ 
date = 2023-05-23T07:33:31+08:00
title = "Introducing: Prompt Engineering for Lawyers"
slug = "introducing-prompt-engineering-for-lawyers"
description = "I introduce my latest work - a set of tutorials on prompt engineering for the legal domain and talk about my vision and aspirations for it."
tags = ["AI","Generative AI","ChatGPT","Legal Tech","Prompt Engineering", "Lawyers","Technology","Tutorials", "Innovation"]
categories = ["posts"]
+++

![Feature photo by Isis França / Unsplash](https://images.unsplash.com/photo-1524514587686-e2909d726e9b?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3wxMTc3M3wwfDF8c2VhcmNofDIxfHxlbmdpbmVlcmluZ3xlbnwwfHx8fDE2ODQ1OTkyODh8MA&ixlib=rb-4.0.3&q=80&w=1200)

"Generative AI isn’t going anywhere", declares [Alex Su in his takeaway](https://www.alexofftherecord.com/p/what-i-learned-at-cloc-2023?ref=lovelawrobots.com) from the annual [CLOC](https://events.cloc.org/event/1d32983d-33ab-47ff-a8ae-9994043fcd1f/summary?ref=lovelawrobots.com) conference. He elaborates:

> What was driving all this interest in AI? Well, the ubiquity of ChatGPT. Everyone’s talking about it and trying to figure out how to incorporate it into the business. And not just in the U.S. It’s a worldwide trend. Word on the street is that it’s a CEO-level priority. Everywhere. So naturally it trickles down to the legal department.

Even so, I was surprised that most lawyers have never tried ChatGPT. Most people's understanding of the technology was formed through media reports and hearsay. Generative AI wasn't "spicy autocomplete". It's an evil magic genie.

I was surprised because I was having fun with this technology for a while... since a few months ago when GPT-3 and ChatGPT came out. Notwithstanding, I felt that the experiences others were sharing were very superficial. To make conclusions based on such assumptions seems undesirable to me.

---

I believe I can make a small contribution using my knowledge of generative AI and the legal domain. Introducing my work in progress: Prompt Engineering for Lawyers.

**"Prompt Engineering for Lawyers" is a web app that provides exercises and experiments which guide you towards making more effective prompts.** This allows you to get the most out of your prompts and also have some experience with what the technology is capable of.

So you'd get a demonstration of what prompts can do in a specialised domain like law. I've tried to pitch it as low as I can go in terms of narration and difficulty. Needless to say, even though it's "for lawyers", anyone can go through it.

<iframe
  src="https://prompt-engineering-lawyers.streamlit.app/?embed=true"
  height="450"
  style="width:100%;border:none;"
></iframe>

At the end of the course, you should think of generative AI more as "spicy autocomplete" rather than "magic genie". Hopefully, with many more vendors now associating their products with "AI", you can explore their claims confidently. (For example, I had the pleasure of watching document assembly claim to be AI.)

## A place to experiment and learn

One of the most important features I wanted in this course is a practice area where you can not only get some guidance on the topic being discussed but also experiment with the prompt in any way you like.

I considered various platforms such as Jupyter notebooks and [pynecone](https://pynecone.io/?ref=lovelawrobots.com). In the end, I chose streamlit because it has a simple interface which allows me to focus on the content rather than the code. Its product is also clean and straightforward, so it looks like a web app rather than some strange, geeky thing which may turn off newcomers.

Here's how it works on the topic of rewriting text. After reading an example, the user would simply click submit and watch the results. I can then suggest various exercises for the user to apply what I mentioned in the text. It's more interactive than a web tutorial or video and definitely more suited for learning than the original ChatGPT interface.

<video width="600" controls>
  <source src="https://res.cloudinary.com/lovelawrobots/video/upload/f_auto:video,q_auto/v1/blog-videos/ibpaqjnvgvbyonvvnlnj" type="video/mp4">Check out a demo of the exercise area.
</video>

The bad news is that you need to get [an OpenAI API key](https://platform.openai.com/signup?ref=lovelawrobots.com) in order to run the web app. Until the day someone provides a free API to their large language model (HAHA), it's probably unavoidable. Luckily, there are [more uses](https://techcrunch.com/2023/05/03/plexs-music-player-plexamp-now-works-with-chatgpt-for-playlist-creation/?ref=lovelawrobots.com) for an OpenAI API key these days.

## A roadmap to learning more about prompt engineering

One of the most difficult aspects of learning prompt engineering is the lack of materials. Well, there are lots of materials out there (see, for example, the [OpenAI Cookbook](https://github.com/openai/openai-cookbook?ref=lovelawrobots.com) and scientific papers if you are willing to dig into it).

However, if you just want to get your hands dirty in the tech, or you would like to know what's the big deal about it. It's hard to find something relevant.

As such, I would like to do two things:

* Have a simple roadmap for someone to be proficient in prompt engineering
* Have it apply to the Legal domain so that lawyers and others know that the technology is readily applicable today.

As I mentioned above, this is still a work in progress, but some of the questions the course should get users to try are:

*  See prompt engineering as more like programming in natural language rather than granting wishes (or some [strange monkey paw version of this idea](https://en.wikipedia.org/wiki/The_Monkey's_Paw?ref=lovelawrobots.com))
*  Compare different models on the basis of power, ability, cost and responsiveness, and not just more parameters or the latest = more win.
*  Conceiving of prompting a model as an iterative and agile process. You get better with more practice, and you get better output when you keep evaluating your prompts.

Of course, we should always do cool stuff like:

*    Few shot classification
*   Data-augmented search or question answering
*   Chain of thought
*   Ask the model to evaluate or moderate its own response

And much more.

## Open-sourcing the knowledge

Like many of my personal projects, I am [open-sourcing this one](https://github.com/houfu/prompt-engineering-lawyers?ref=lovelawrobots.com). So it's free. You can copy it, distribute it, remix it, or even sell it (as long as you keep to the CC-BY-SA license)

I am motivated by the ideals of sharing openly and freely, while also promoting collaborations which may be unusual in the legal profession.

These are altruistic reasons, but in my mind, it's purely business. There's a lot of scope for this project, and given my time constraints and desire to work on other stuff, getting contributors as early as possible is important.

In _Forge Your Future with Open Source_, author VM Brasseur comments on "Share the Burden Early":

> While documentation, boundaries, and other types of expectation setting will go a long way toward avoiding burnout, nothing makes as large of a difference as having other people to help you. By sharing the burden of project maintenance, you reduce the impact on any one person while improving the project’s bus factor and therefore, also its longevity and resilience.

Since brewing this project, I already have a suggestion but not a PR.

Of course, just because something is a good idea (at least to me) is hardly a guarantee that someone wants to help contribute to it. To me, though, if it ain't working out, I can walk away.

So, I've gotta spend some time dolling up the Contributing file and setting up the issue templates.

## Conclusion

Currently, there are still some ways to go before the material matures, but you can already play with it now. I hope it's still useful. What do you think about it? Is there something I should include? Feel free to let me know.