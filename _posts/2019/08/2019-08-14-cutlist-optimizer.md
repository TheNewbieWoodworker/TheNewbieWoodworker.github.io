---
title: "CutList Optimizer"
layout: post
permalink: "/articles/cutlistoptimizer/"
redirect_from:
  - "/cutlistoptimizer/"
  - "/CutListOptimizer"
  - "/CutlistOptimizer"
category: article
article-image: "/assets/images-posts/2019/08/2019-08-14.1.05.jpg"
article-description: "CutList Optimizer is a great website for generating cut lists. This articles explains how to use the site."
---
![](/assets/images-posts/2019/08/2019-08-14.1.01.jpg)
<br/>
<br/>
There's a great website I've been meaning to talk about for quite a while, called [CutList Optimizer](https://www.cutlistoptimizer.com/){:target="_blank"}. I'm currently working on a video about it, and this is the accompanying article. As the name says, CutList Optimizer generates lists for the optimal way to cut stock into the sizes you need for a project.

You can save the cut list as a PDF file. [Click here for a simple sample](/assets/downloads/cutlist-optimizer-simple-example.pdf){:target="_blank"}.

<p class="panel-note">I use inches with decimal places throughout this document, but CutList Optimizer supports fractional inches, metric, and other <a href="#units">units</a>.</p>



<p id="top-note" class="panel-warning" markdown="1">NOTE: Websites change all the time. As far as I know, this information was accurate as of **2019-08-15**. If something significant changes, I'll try to keep this updated.<br/><br/>

**Update History:**<br/>
**2019-08-16:** Re-did the [Simple Example](#simpleexample) section to make it a little more clear.<br/>
**2019-08-15:** Changes to the [Error Messages / Bugs](#errormessagesbugs) section to clarify that the error messages may in fact be legitimate.
</p>

<hr class="hr-thick" style="margin-bottom: 30px;">




## Table of Contents

<span style="color:red; font-size: 1.5em;">**!!**</span> Please read the sections marked with red exclamation marks <span style="color:red; font-size: 1.5em;">**!!**</span>

1. [Simple Example](#simpleexample)
   1. [The Cut List](#the-cut-list)
   1. [The “Cuts” Panel](#the-cuts-panel)
   1. [The Cut Sheet](#the-cut-sheet)
1. [Complicated Example](#complicatedexample)
1. [Export, Save & Load Options](#exportsaveloadoptions)
1. <span style="color:red; font-size: 1.5em;">**!!**</span> [Other Save/Load Options](#othersaveloadoptions)
1. [SketchUp](#sketchup1)
1. <span style="color:red; font-size: 1.5em;">**!!**</span> [Error Messages / Bugs](#errormessagesbugs)
1. [Settings](#_settings)
   1. [Optimization level](#optimization-level)
   1. [Units](#units)
   1. [Cut / blade / kerf thickness](#cut--blade--kerf-thickness)
   1. [Consider Material](#consider-material)
   1. [Consider grain direction](#consider-grain-direction)
1. [YouTube Video](#youtubevideo)




<hr id="simpleexample" class="hr-thick" style="margin-bottom: 30px;">

## Simple Example

![](/assets/images-posts/2019/08/2019-08-14.1.11.jpg){: .image-border}{: .align-left}
I should mention that I'm using these options. The first two options are self-explanatory.

The third option generates numbers for the order of the cuts. I'll explain more in a moment.

{:style="clear: left"}

<hr style="margin-bottom: 40px"/>

![](/assets/images-posts/2019/08/2019-08-14.1.02.jpg){: .image-border}{: .align-left}
Let's say you need to cut these pieces, from a sheet of plywood.

{:style="clear: left"}

![](/assets/images-posts/2019/08/2019-08-14.1.03.jpg){: .image-border}{: .align-left}
And here's the stock you want to cut them from.

{:style="clear: left"}

![](/assets/images-posts/2019/08/2019-08-14.1.09.jpg){: width="500px"}{: .image-border}{: .align-left}
After you enter the above information, click the "Calculate" button, and it generates the cut list.

<p style="clear: left"> </p>
---



### The Cut List

[![](/assets/images-posts/2019/08/2019-08-14.1.05.jpg)](/assets/images-posts/2019/08/2019-08-14.1.05.jpg){:target="_blank"}
*Click image to view full sized*

So let's break down what we get.

#### The "Cuts" Panel

![](/assets/images-posts/2019/08/2019-08-14.1.06.jpg){: width="300px"}{: .image-border}{: .align-left}
The "Cuts" panel shows the cuts you need to make.

{:style="clear: left"}

#### The Cut Sheet

![](/assets/images-posts/2019/08/2019-08-14.1.07.jpg){: .image-border}{: .align-left}

This is the cut sheet. Each of the cuts are numbered to match the numbers in the Cuts panel (above).

{:style="clear: left"}

![](/assets/images-posts/2019/08/2019-08-14.1.25.jpg){: .image-border}{: .align-left}
If you put your mouse over the first cut (**A**), it shows you where the first cut is (**B**).

And of course you can mouse over the other cuts too.

{:style="clear: left"}



![](/assets/images-posts/2019/08/2019-08-14.1.08.jpg){: .image-border}{: .align-left}
This is the bottom right of the cut sheet.

#1 is the first cut. The red number is right next to the red cut line.

{:style="clear: left"}

![](/assets/images-posts/2019/08/2019-08-14.1.10.jpg){: .image-border}{: .align-left}
This is the bottom left of the cut sheet.

#2 is the second cut, and the blue number is right next to the blue cut line.

And it continues like that.

{:style="clear: left"}

<br/>




<hr id="complicatedexample" class="hr-thick" style="clear: left; margin-bottom: 30px;">

## Complicated Example

![](/assets/images-posts/2019/08/2019-08-14.1.12.jpg){: .image-border}{: .align-left}
As you can see, this one's *a little more complicated*.

I've got 38 pieces, from three different materials:

<p>● Plywood 3/4"<br/>● Plywood 1/4"<br/>● Pine</p>

I've got the option for "Consider Material" turned on, so each piece can come from a different material.<br/>(See ["Settings"](#_settings), below.)

I actually don't recommend doing this because it makes "Calculate" take a long time. It's probably better to do one material type at a time.

{:style="clear: left"}

![](/assets/images-posts/2019/08/2019-08-14.1.13.jpg){: .image-border}{: .align-left}
When you've entered a lot of items and you click the calculate button...

{:style="clear: left"}

![](/assets/images-posts/2019/08/2019-08-14.1.14.jpg){: .image-border}{: .align-left}
(**1**) the "Calculate" button changes to "Cancel",

(**2**) and it says "Initializing...".

This doesn't usually take long, but you can click the "Cancel" button if you want to. [^1]

{:style="clear: left"}

Once it's done initializing, the screen changes like this:

![](/assets/images-posts/2019/08/2019-08-14.1.15.jpg)

(**1**) The button will change to "Accept".

(**2**) It'll say "Searching for best solution...".

(**3**) And for a while, it may also show a panel with pieces it was "Unable to fit". Assuming you've supplied enough "Stock sheets", this will eventually go away.

![](/assets/images-posts/2019/08/2019-08-14.1.16.jpg){: .image-border}{: .align-left}
Then it will start showing a percentage.

{:style="clear: left"}

At any point you can click the "Accept" button [^2], which will cause it to stop calculating, and show you what it currently thinks is the best solution.

[![](/assets/images-posts/2019/08/2019-08-14.1.17.jpg){: .image-border}](/assets/images-posts/2019/08/2019-08-14.1.17.jpg){:target="_blank"}
*Click image to view full sized*





<hr id="exportsaveloadoptions" class="hr-thick" style="margin-bottom: 30px;">

## Export, Save & Load Options

![](/assets/images-posts/2019/08/2019-08-14.1.18.jpg){: .image-border}{: .align-left}
When you click button as shown, you get this popup menu. Here's some notes:

**Save/Load Project:** As far as I know, this information is stored in your browser's cookies, and may get deleted at some point in time.

**Export to PDF:** Allows you to download a PDF of the cut list.

{:style="clear: left"}





<hr id="othersaveloadoptions" class="hr-thick">

<h2 id="-other-saveload-options" style="margin-top: 30px"><span style="color:red">!!</span> Other Save/Load Options</h2>

![](/assets/images-posts/2019/08/2019-08-14.1.19.jpg){: width="200px"}{: .image-border}{: .align-left}
If you click the menu button (red circle) on either the "Panels" or the "Stock sheets" panels, you get this menu.

**Load list** and **Save list**: Loads or saves the data in the list, to your browser's cookies (I think).

**Export to CSV** and **Import from CSV**: These save CSV files to your computer, or loads them from your computer.

<p class="panel-warning">Since cookies can get deleted in various ways, if you want to save your data, I recommend using CSV files.</p>

{:style="clear: left"}





<hr id="sketchup1" class="hr-thick" style="margin-bottom: 30px">

## SketchUp

If I learn of any plugins that allow you to export CSV files from SketchUp that can be used with CutList Optimizer, I'll post that here. And if you know of any, leave a comment and let me know. Thanks!





<hr id="errormessagesbugs" class="hr-thick">

<h2 id="-error-messages-bugs" style="margin-top: 30px"><span style="color:red">!!</span> Error Messages / Bugs</h2>

There's a couple of error messages that you might encounter, and I think <span style="color:red">**sometimes you get them as a result of a bug**</span>.

![](/assets/images-posts/2019/08/2019-08-14.1.20.jpg){: .align-left}
This one means you can't run "Calculation" in multiple browser windows or tabs at the same time.

{:style="clear: left"}

![](/assets/images-posts/2019/08/2019-08-14.1.24.jpg){: .align-left}
This one is kind of self-explanatory. I'd like to say this to people myself, sometimes. "*My brain is experiencing some issues. Try again later.*"

{:style="clear: left"}

I've received these error messages a couple of times when I'm pretty sure they were the result of a bug of some kind. In other words, they didn't really mean what they said.

I got them after I "canceled" a "calculation", when I was only using one browser tab.

* The first time I got the error, I was using Safari, so I switched to Chrome, and the problem went away.

* The second time I got the error, I cleared the cookies for the CutList Optimizer website, and the problem went away.

  <p class="panel-warning" markdown="1">Clearing cookies wiped out my data (which is why I think CutList Optimizer saves data in cookies).<br/><br/>Fortunately, I had [exported both of my "list" panels](#-other-saveload-options), so it didn't take me long to get it running again.</p>

  [Here's an article](https://www.lifewire.com/clear-cookies-for-one-site-4587347){:target="_blank"} that shows how to delete cookies for a specific website.

So just be aware of these potential problems.





<hr id="_settings" class="hr-thick" style="margin-bottom: 30px;">

## Settings

When you start a new session, you get this dialog.

![](/assets/images-posts/2019/08/2019-08-14.1.21.jpg){: .image-border}

![](/assets/images-posts/2019/08/2019-08-14.1.22.jpg){: .image-border}{: .align-left}
You can also get it by clicking the Gear icon in the upper right.

{:style="clear: left"}

You can guess what most of the settings do. Here's some tips on some of them:

### Optimization level

<div style="margin-left: 40px">
  <div>
    <span><b>Values:</b></span><br/>
    <ul>
      <li>Low</li>
      <li>Normal</li>
      <li>High</li>
    </ul>
  </div>

  <div>
    <span><b>Notes:</b></span><br/>
    <ul>
      <li>If it's taking too long to calculate your cut list, try using one of the lower settings.</li>
    </ul>
  </div>
</div>


### Units

<div style="margin-left: 40px">
  <div>
    <span><b>Values:</b></span><br/>
    <ul>
      <li>Generic (16.5)</li>
      <li>Millimeters (16.5mm)</li>
      <li>Centimeters (16.5cm)</li>
      <li>Inches (16.5")</li>
      <li>Decimal Feet & Inches (1' 4.5")</li>
      <li>Fractional Feet & Inches (1' 4 1/2")</li>
    </ul>
  </div>

  <div>
    <span><b>Notes:</b></span><br/>
    <ul>
      <li>I wish there was an option for <b>Fractional Inches (16 1/2")</b>, because I don't like <b>1' 4 1/2"</b>.</li>
      <li>You can switch units during a project, but for me, <span style="color:red"><b>it didn't always work right</b></span>. So decide what units you want before you go to far.</li>
    </ul>
  </div>
</div>

### Cut / blade / kerf thickness

<div style="margin-left: 40px">
  <div>
    <span><b>Notes:</b></span><br/>
    <ul>
      <li>Use this to tell CutList Optimizer the size of your kerf [^3], so it can take that into account. For example, you can’t cut two 16” pieces from one 32” piece, because the kerf eats up some of the available wood.</li>
    </ul>
  </div>
</div>

### Consider Material

<div style="margin-left: 40px">
  <div>
    <span><b>Notes:</b></span><br/>
    <ul>
      <li>If you're only cutting from one kind of stock, then you don't need this. But in my <a href="#complicatedexample">Complicated Example</a>, it's how I could do all three materials at once. Still, it's probably best to do them one at a time.</li>
    </ul>
  </div>
</div>


### Consider grain direction

<div style="margin-left: 40px">
  <div>
    <span><b>Notes:</b></span><br/>
    <ul>
      <li>This is a cool feature, but I'll let you figure out how to use it. Hint:<br/><img src="/assets/images-posts/2019/08/2019-08-14.1.23.jpg" alt=""></li>
    </ul>
  </div>
</div>




<hr id="youtubevideo" class="hr-thick" style="margin-bottom: 30px">

## YouTube Video

I may or may not add more to this article. Right now my plan is to start working on the YouTube video, and that may lead to changes to this article. If I update this article, I'll change the date mentioned in the [top "Note"](#top-note).

{% include footnote-title.html %}

[^1]: I think there's a bug that sometimes crops up when you do this. See the "[Error Messages / Bugs](#errormessagesbugs)" section.
[^2]: [Ibid](https://research.wou.edu/c.php?g=551307&p=3785494){:target="_blank"}.
[^3]: The "kerf" is the size of the slot your blade cuts. Typically this is 1/8", or a little less for thin-kerf blades.
