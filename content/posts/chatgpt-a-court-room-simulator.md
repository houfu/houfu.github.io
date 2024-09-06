+++ 
date = 2023-07-03T01:03:49+08:00
title = "ChatGPT: A Court Room Simulator?"
description = "I created a courtroom simulator using ChatGPT to help train lawyers in advocacy. This simulator allows ChatGPT to play the roles of both judge and opposing counsel, providing a unique and interactive way to practice courtroom skills. Despite some bugs, the simulator is functional and available for testing by anyone with an OpenAI key. If you're interested, you can try out the simulator and see if you can beat ChatGPT."
slug = "chatgpt-a-court-room-simulator"
tags = ["ChatGPT", "AI", "LegalTech", "Courtroom Simulation", "Lawyer Training", "Advocacy Skills", "Prompt Engineering", "Legal Education", "Role-Playing", "OpenAI", "Legal Practice", "Technology in Law"] 
+++

_Large language models like #ChatGPT present a unique opportunity to train #lawyers in new ways. I discuss a simple courtroom #simulator I created that is able to mimic the cuts and thrusts of advocacy, and wonder whether anyone will use it._

![A cockpit with many lights; Photo by ](https://res.cloudinary.com/lovelawrobots/image/upload/f_auto,q_auto/v1/blog-images/knyo5bws8kiwsykq4wz2)

<!--more-->

One of the many challenges of writing [Prompt Engineering for Lawyers](introducing-prompt-engineering-for-lawyers/) is that I wanted law-specific examples to demonstrate prompt engineering concepts.

For the topic of "role-playing", I decided to create a courtroom simulator. Basically, ChatGPT plays judge and opposing counsel, and your job is to beat opposing counsel and convince the judge to deny his application. It's deceptively simple. ChatGPT can play two roles in the same chat, but helping ChatGPT handle those jobs requires more than describing them.

It's obviously not 100% bug-free, but it works for the most part. 

{{< video "https://res.cloudinary.com/lovelawrobots/video/upload/v1688231807/thorxnmarrzynstd3p2g.webm" >}}

As I further tested and refined the prompt, I realised that I was getting better at beating ChatGPT and persuading ChatGPT to deny the order. The point, however, is not beating ChatGPT. Running the scenario repeatedly allowed me to think more about my response and evaluate several possible arguments for the same fact scenario. While I was training ChatGPT... I was training myself.

I think there's a lot of value in such a training simulator, especially for training young lawyers. As I noted in a footnote for this exercise:

Some people are concerned that [the opportunities for young lawyers today to practice advocacy are shrinking](https://journalsonline.academypublishing.org.sg/Journals/SAL-Practitioner/Advocacy-and-Procedure/ctl/eFirstSALPDFJournalView/mid/589/ArticleId/1285/Citation/JournalsOnlinePDF). Is this a cause for concern?

If you enjoyed the exercises in this section, you might already know what the future might hold. Much like aircraft pilots, law students and lawyers can clock hours of trainings in "simulators" powered by LLMs. While certain vaunted aspects of advocacy (such as following the judge's pen) might be impossible to teach in a chat setting, lawyers can still be exposed to a wide range of situations in simulated environments and can evaluate the effects of their actions without causing loss to the client (or anxiety to the lawyer). Clients also will not be forced to pay a law firm to train their young lawyers on their matters.

The idea of simulator training was also mentioned by Richard Susskind as a response towards the possible loss of skills when work is displaced by smart systems. (See [The End of Lawyers](https://orreadi.com/book/26677/s/the-end-of-lawyers), page 118)

I haven't heard of anyone deploying this for real, but the idea of simulators is probably very actionable with some refinement and fine-tuning.

However, when I further considered who would train their lawyers this way, I realised that such simulator training is probably non-billable if they can't be linked to a live matter. If it's non-billable... I rather my associates be doing stuff that is billable.

It's fascinating that airline pilots are required to clock such simulator hours even when they aren't paid for it. We expect pilots to know their stuff even when they might not be able to find a real plane to fly in. Instead, many associates might find themselves doing OJT on matters where other people's lives are at stake. I guess it goes to show the kind of perverse incentives the law firm business model might find itself.

Maybe I should focus instead on an "Ace Attorney" generator instead. That might be a better-received idea.
![A GIF capture of a video game](https://media.giphy.com/media/NVEtOZRkhukZVBB32W/giphy.gif)
