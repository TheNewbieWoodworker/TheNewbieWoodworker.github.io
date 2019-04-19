---
title: "New video, and thoughts on FCPX Automation"
layout: post
---
I'm sure most of you know by now, but I've got a new video out, so be sure to check it out. But I wanted to blog about some geek stuff.

{% include youtube-player.html id="GTVLeeUJFHI" %}
*New SawStop PCS*

## Thoughts on FCPX Automation

*Disclaimer*

> These thoughts will be of limited to no value for the vast majority of people, but I feel compelled to blog them anyway. Also, some of this is generalized, and although correct, I might not use the exact right terms.

I spend a lot of time editing videos on my Mac using FCPX (Final Cut Pro X). And I do a lot of repetitive tasks while editing the videos. I've managed to automate a lot of those tasks, no thanks to FCPX itself.

### OS/X Automation

OS/X has a lot of built-in support for automating applications through AppleScript, and more recently JXA (Javascript for Automation, and yes, the acronym doesn't match the name).

If the developers of an application want to, they can add extra support for automation by exposing all sorts of things.

For example, the iTunes developers added support for automation, so I can do things like get a list of songs, playlists, etc. I can play songs and videos. All sorts of things. And if iTunes doesn't have a keyboard shortcut for something, I might be able to create the equivalent using automation. (There's other ways to create shortcuts on a Mac, but this is just an example.)

*(This is just an example. I don't actually automate anything in iTunes.)*

### Keyboard Maestro

I also use a program called [Keyboard Maestro](https://www.keyboardmaestro.com){:target="_blank"}, which is only available on Macs (unfortunately). It's much, much more than just a "macro" program, and it's unbelievable the number of things I've accomplished with it.

Before I started my YouTube channel, I used to practically live on the [Keyboard Maestro forum](https://forum.keyboardmaestro.com){:target="_blank"}. I learned a lot, and I've helped a lot of people. Bunches of people still use macro libraries I created, and yes, I'm proud of what I've done.

### FCPX Automation Support (none)

So back to FCPX. Apple has ***no support in FCPX for automation***, aside what comes natively for all OS/X applications. None whatsoever. <span style="color:red">***It's almost criminal***</span>.

What a joy it would be to have full automation support, so it would be easy to automate the repetitive tasks a lot of us have to do.

### But All Is Not Lost

Fortunately, being the sneaky-ass developer I am (did you know I'm a retired software developer?), I've been able to automate tons of UI things that a lot of people would never dream could be automated.

And I'd love to share this information. The problem is, sometimes when Apple releases new versions, some of my automation stuff breaks. And I don't want to be responsible for maintaining the code. I just want to share the knowledge with other developers like me.

## What's My Point?

None whatsoever, except to wish that some other developers like me might stumble across this blog post and contact me. It's highly unlikely. But the chances are greater than 0%, so what the heck.

## Why Now?

Why am I blogging about this now? Because whenever I finish a video, I do all sorts of things before I archive the video project. Including deleting video clips that end up not being used. This is one of the places I've done some extensive automation.

And I just now figured out how to automate one particular thing that had been driving me crazy. But there's no one to share this with, because the amount of arcane knowledge required to even understand what I've accomplished is beyond the vast majority of people.

So instead, I'm crowing about it out into the void of the 'Net.
