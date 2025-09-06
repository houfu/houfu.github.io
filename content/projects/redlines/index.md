+++ 
date = 2024-09-05T11:41:15+08:00
title = "Redlines"
image = "repository-open-graph.png"
description = "Open-source document comparison tool for legal teams. Fast contract review and version control without enterprise software costs."
+++
![Redlines banner image](repository-open-graph.png)

**Document Comparison Tool Built for Legal Workflows**

Faster contract review and version control for legal teams that can't afford enterprise document management systems. Shows changes in the familiar strike-through/underline format lawyers recognize from Microsoft Word.

## Business Value for Legal Teams

**Time Savings**: Instantly spot changes between contract versions  
**Cost Effective**: Open-source alternative to expensive comparison tools  
**Familiar Interface**: Strike-through/underline format lawyers already know  
**Multiple Formats**: Export comparisons as Markdown, HTML, or terminal display  
**No Vendor Lock-in**: Own your tool, customize as needed  

## Perfect For:
* Solo counsels reviewing contract revisions without enterprise tools
* Small legal teams needing efficient document version control
* Corporate counsel working with multiple contract iterations
* Legal professionals who want tool independence from vendors

## Technical Implementation

`Redlines` uses Python's `SequenceMatcher` to find differences between documents at the word level. The output format mimics Microsoft Word's track changes but works with any text format - perfect for contract review workflows where you need to quickly identify what changed between versions.

**Why This Matters**: Many legal teams pay thousands for document comparison features in enterprise software. Redlines gives you the core functionality you actually use, without the enterprise overhead.

{{< linkcard
    url="https://houfu.github.io/redlines/"
    title="Documentation"
    description="Read the documentation on how to use this library"
>}}

{{< linkcard
    url="https://github.com/houfu/redlines"
    title="Github Repository"
    description="Explore the code and take part in development of this open source library"
    image="images/github-mark.png"
>}}

I gave a talk on it too!

{{< youtube jkfVJ36zWZY >}}

Check out the presentation here too:

{{< pdf src="https://res.cloudinary.com/lovelawrobots/image/upload/geekcamp-prez_y8xro8.pdf" width=800 height=600 >}}
