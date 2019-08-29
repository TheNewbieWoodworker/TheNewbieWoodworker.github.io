---
title: "One way to add Info and Warning Panels to a Jekyll-based website"
layout: post
---
If you have a [Jekyll](https://jekyllrb.com/){:target="_blank"}-based website, you might be interested in how I added Information and Warning panels. This is in a site based on the [Basically Basic theme](https://github.com/mmistakes/jekyll-theme-basically-basic){:target="_blank"}.

I don't claim to know what I'm doing, so <span style="color:red">**if there's a better way, please, I beg of you, let me know!**</span>

> **NOTE** The CSS is shown later on in this article.

<hr class="hr-medium" style="margin-bottom: 30px"/>




### Note Panel

<p class="panel-note" markdown="1">This is a **Note** panel, using my 48x48 site icon. All of these allow you to use Markdown inside the panel.</p>

```
<p class="panel-note" markdown="1">This is a **Note** panel, using my 48x48 site icon. All of these allow you to use Markdown inside the panel.</p>
```

<hr class="hr-medium" style="margin-bottom: 30px"/>




### Warning Panel

<p class="panel-warning" markdown="1">This is a **Warning** panel.
Not sure this is the best icon for a warning, but you can obviously replace this with anything.</p>

```
<p class="panel-warning" markdown="1">This is a **Warning** panel. Not sure this is the best icon, but you can obviously replace this with anything.</p>
```

<hr class="hr-medium" style="margin-bottom: 30px"/>




### Multiple "Paragraphs"

<p class="panel-note" markdown="1">In order to have multiple "paragraphs", you have to use HTML `<br/>` elements.
Otherwise Jekyll screws up the paragraph.<br/>
<br/>All the text is indented the same, even when the icon is no longer in play.
</p>

```
<p class="panel-note" markdown="1">In order to have multiple "paragraphs", you have to use HTML `<br/>` elements.
Otherwise Jekyll screws up the paragraph.<br/>
<br/>All the text is indented the same, even when the icon is no longer in play.
</p>
```

<hr class="hr-medium" style="margin-bottom: 30px"/>







### Single lines can look odd

<p class="panel-note" markdown="1">A single unwrapped line looks a little funny.</p>

```
<p class="panel-note" markdown="1">A single unwrapped line looks a little funny.</p>
```

<hr class="hr-medium" style="margin-bottom: 30px"/>





### Better single line

<p class="panel-note top-padding" markdown="1">This looks better, but the CSS isn't exactly "responsive".</p>

```
<p class="panel-note top-padding" markdown="1">This looks better, but the CSS isn't exactly "responsive".</p>
```

<hr class="hr-medium" style="margin-bottom: 30px"/>





### "Heading" Line

<p class="panel-warning" markdown="1"><span style="color:red; font-size: 1.15em">**This is kind of like a heading.**</span><br/>
<br/>I still don't have the top margin working properly.
</p>

```
<p class="panel-warning" markdown="1"><span style="color:red; font-size: 1.15em">**This is kind of like a heading.**</span><br/>
<br/>I still don't have the top margin working properly.
</p>
```

<hr class="hr-medium" style="margin-bottom: 30px"/>





### CSS

Add this code to your \assets\stylesheets\main.scss file. I completely admit that I have very little idea what I'm doing. I stitched together a bunch of stuff I found on the 'Net.

And like I said at the start, <span style="color:red">**if you can improve this, please, for the love of God, let me know!**</span>

Obviously replace the background images, which are 48x48.

```
.panel-note
{
  -moz-border-radius: 6px;
  -webkit-border-radius: 6px;
  background-color: #f0f7fb;
  background-image: url(/assets/images/saw_blade_warning.png);
  background-position: 5px 15px;
  background-repeat: no-repeat;
  border: solid 1px #3498db;
  border-radius: 6px;
  overflow: hidden;
  padding: 13px 20px 15px 65px;
  min-height: 80px;
}

.panel-note.top-padding {
  padding-top: 25px;
}

.panel-warning
{
  -moz-border-radius: 6px;
  -webkit-border-radius: 6px;
  background-color: rgb(252, 248, 227);
  background-image: url(/assets/images/icon-warning.png);
  background-position: 5px 15px;
  background-repeat: no-repeat;
  border: solid 1px #3498db;
  border-radius: 6px;
  overflow: hidden;
  padding: 13px 20px 15px 65px;
  min-height: 80px;
}

.panel-warning.top-padding {
  padding-top: 25px;
}
```

Later.