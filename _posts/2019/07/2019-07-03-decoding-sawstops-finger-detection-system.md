---
title: "Decoding SawStop's Finger Detection System"
layout: post
---
![](/assets/images-posts/2019/07/2019-07-03.1.01.jpg)
<br/>
<br/>
Let's go sleuthing! We're going to uncover the **secrets of a SawStop brake**, like how it knows if the **blade touched your finger** or just a nail. And we'll discover that it's not as simple as we thought. So if **you think you know everything** there is to know about how, when, and why a SawStop brake gets triggered, <span style="color:blue">***Wait! There's more!***</span>

![](/assets/images-posts/2019/07/2019-07-03.1.16.jpg){: width="46px" style="transform: translateY(2px)"}{: .align-left}
No, I'm not ***actually*** going share industry secrets [^1]. But I ***am*** going to delve into details you've <span style="color:blue">**probably never thought about before**</span>.

{:style="clear: left"}

This post is the result of a lot of research, debugging, testing, and general sleuthing I've been doing over the <span style="color:red">**past 10 days**</span>(!), as well as multiple phone calls I've had with SawStop personnel. If you haven't been following along, this all started with an [issue I had with the the Infinity Throat Plate]({{ site.baseurl }}{% post_url 2019/06/2019-06-23-my-infinity-throat-plate-plus-a-cross-cut-sled-triggers-sawstop's-warning-light %}) and my [SawStop PCS]({{ site.baseurl }}{% post_url 2019/03/2019-03-24-sawstop-pcs-pt1 %}).

![](/assets/images-posts/2019/07/2019-07-03.1.17.jpg){: style="transform: translateY(6px);margin-bottom:50px"}{: .align-left}
<span style="color:blue">**I highly recommend not skipping a section**</span> as you read along, because even if it's something you *think* you already know, I've sprinkled in <span style="color:red">**some goodies**</span> you probably don't know.

{:style="clear: left"}

> **NOTE:** Although this is article is fairly detailed, I'm not trying to cover every possible scenario.

![](/assets/images-posts/2019/07/2019-07-03.1.19.jpg){: style="transform: translateY(1px)"}{: .image-border}{: .align-left}
<p style="transform: translateY(4px)">If you don't know anything about SawStop safety technology, <a href="https://youtu.be/T3IGPCkirdU" target="_blank">watch this short video first</a>. (Less than 2 minutes.)</p>

{:style="clear: left"}


<br/>


<hr class="hr-thick">

<p></p>

## ![](/assets/images-posts/2019/07/2019-07-03.1.05.jpg) <span style="color:black">The Basics</span>

![](/assets/images-posts/2019/07/2019-07-03.1.03.jpg){: .align-left}

When the power to a SawStop saw is turned on, the saw sends a small electrical signal through the arbor into the blade (yellow circles). It does this *even when the motor isn't running*.

A <span style="color:blue">**digital signal processor (DSP)**</span> inside the brake cartridge is monitoring the signal for change.

It monitors the signal from ***across the gap*** between the brake and the blade (red circle) [^2].

{:style="clear: left"}

<br/>

<hr class="hr-thick">

<p></p>

## ![](/assets/images-posts/2019/07/2019-07-03.1.06.jpg){: width="150px"}{: .image-border} <span style="color:black">Modes</span>

You probably already know this, but bear with me. The SawStop saw can be in one of three different modes:

1. **Standby Mode**. The power is turned on, but the blade isn't spinning.

1. **Bypass Mode**. The motor is running, the blade is spinning, but the brake won't fire. The status lights will tell you if the brake ***would have*** fired, though.

1. **Normal Operation**. The motor is running, the blade is spinning, and the brake will actually fire if the **DSP** thinks it should.

In addition to those, there's a sub-mode for #2 and #3:

* **Spinning Down**. The motor has been turned off, the blade is slowing down, but it hasn't stopped yet. The green indicator light flashes until the blade stops spinning.

<br/>

<hr class="hr-thick">

<p></p>

## ![](/assets/images-posts/2019/07/2019-07-03.1.04.jpg){: width="150px"}{: .image-border} <span style="color:black">Signal Changes</span>

As mentioned earlier, the **DSP** monitors the electrical signal for change, but be aware:

![](/assets/images-posts/2019/07/2019-07-03.1.07.jpg){: .align-left}
The **amount** the signal changes can **vary significantly** [^3]. <span style="color:red">**This is an extremely important concept**</span>, which we'll learn later on.

{:style="clear: left"}

Here's some things that can affect the electrical signal:

### Us

Obviously the main purpose for the signal is to help detect if the blade touches flesh, like a finger. And since our bodies are basically large capacitors [^4], contact with them will certainly have an affect. To both us and the signal!

### Metal

If the blade makes contact with metal, it will change the signal. If we're *touching* the metal, the change will be much greater.

![](/assets/images-posts/2019/07/2019-07-03.1.18.jpg){: .align-left}
But did you know that <span style="color:red">***even close proximity to metal***</span> can change the signal to some degree? Well, it can. We'll talk more about this "proximity effect" shortly, and you'll see the proof for yourself.

{:style="clear: left"}

### ~~Hot Dogs~~ Other Conductors

Any other kind of conductive material can also cause the changes to the signal.

<br/>

<hr class="hr-thick">

<p></p>

## ![](/assets/images-posts/2019/07/2019-07-03.1.12.jpg){: width="150px"}{: .image-border} <span style="color:black">Taking Action</span>

<p></p>

I'll discuss how the **DSP** decides *whether* to take action or not, in a moment. But I want to quickly cover some of the actions it might take.

* **The DSP will only fire the brake if the blade is spinning** (but see the next point). Well, technically, I think there's a split second between when the blade stops spinning and the light actually stops flashing, so I suppose it *might* fire if you touched the blade in that split second.

* **If the saw is running in Bypass Mode, the brake won't fire.**

* **The indicator lights tell you what action the DSP took**, or ***would have taken***, if the saw is in bypass mode.

<span style="color:blue">So, when I use a phrase like "take action", this is what I'm referring to.</span>

<br/>

<hr class="hr-thick">

<p></p>

## ![](/assets/images-posts/2019/07/2019-07-03.1.08.jpg){: width="150px"}{: .image-border} <span style="color:black">Decisions, Decisions</span>

OK, something has caused the signal to change. Now what?

This is where SawStop makes its money, so to speak. I'm sure the logic and signal processing they do is a closely guarded secret.

### Let's pretend it's simple

For the purposes of this article, let's pretend that the **DSP**'s' logic is based solely on the *strength* of the electrical signal. Specifically, if something affects the signal, the signal strength drops. And if that something stops affecting the signal, the signal strength goes back up.

As I said before, I'm sure it's more complicated than this. But this will do for now.

Here's some common scenarios:

### Nails

![](/assets/images-posts/2019/07/2019-07-03.1.09.jpg){: .align-left}
What happens if you hit a nail? The signal drops a little, but the **DSP** decides it isn't enough to be a person, so it doesn't do anything. [^5]

***But it remembers.***

And if you hit *more* nails right after that, the **DSP** may decide "I don't want to take any chances, this might be a person, so <span style="color:red">***take action***</span>".

{:style="clear: left"}

<p></p>

### Fingers (or hot dogs)

![](/assets/images-posts/2019/07/2019-07-03.1.10.jpg){: .align-left}
What happens if you touch the blade?

The signal drops a ***lot***, because your body can conduct a lot of electricity.

So the **DSP** says "**HOLY CRAP!**" [^6] and <span style="color:red">***takes action***</span>.

{:style="clear: left"}

<p></p>

### Proximity

![](/assets/images-posts/2019/07/2019-07-03.1.13.jpg){: .align-left}
As I mentioned earlier, if metal is just within *close proximity* to the blade, it can affect the signal [^7].

If that's hard for you to believe, don't forget that the **DSP** monitors the signal *across* the gap between the blade and the brake, without needing to be in direct contact with the blade (good thing).

And if you've ever been zapped with static electricity by a door knob, then you've probably already experienced the proximity effect [^8].

{:style="clear: left"}

<p></p>

<span style="color:red">***But neither of those explanations matter***</span>, because <span style="color:blue">***we can demonstrate the effect***</span>, which you'll see in the next section.

<br/>

<hr class="hr-thick">

<p></p>

## ![](/assets/images-posts/2019/07/2019-07-03.1.15.jpg){: .image-border}{: width="150px"} <span style="color:blue">Infinity Throat Plate</span>

![](/assets/images-posts/2019/07/2019-07-03.1.11.jpg)

#### <span style="color:blue">***And this is where it gets interesting.***</span>

> **NOTE:** When I talk about how long the red light flashes, understand that it can vary, and it doesn't always work the exact same way every time.

On the advice of many people on the [SawStop Users' Group on Facebook](https://www.facebook.com/groups/sawstopusersgroup/){:target="_blank"}, I bought the above [Infinity Throat Plate](https://www.infinitytools.com/sawstop-zero-clearance-throat-plate-with-two-inserts-4750){:target="_blank"}. And something happened right away that had me wondering.

### The Issue

It didn't take long for me to discover an extremely odd problem that started me on this week-and-a-half-long journey.

Depending on a lot of different circumstances, sometimes when I was using the Infinity plate and I raised the blade, <span style="color:blue">**it would trigger the "Contact Detected During Standby"**</span> warning light pattern, which I'll refer to as the <span style="color:red">**flashing light**</span> from here on out.

<span style="color:blue">**It never triggered the brake**</span>, because I never got this while running the motor. But that doesn't mean it couldn't, although let's leave that discussion for a little later [^9].

![](/assets/images-posts/2019/07/2019-07-03.1.20.jpg){: width="50px"}{: .align-left}
**Here's some things to note**, so I don't have to spend a lot of time on them. This article is not a proof, so just take my word for these things. Or not.

{:style="clear: left"}

1. At first I thought the problem was my cross-cut sled. But after some testing, I discovered that I could get the problem to occur *without* using a sled (more on this in a moment).

2. I verified that the blade is NOT touching the insert plate. I believe this problem is an example of the "proximity effect", which I didn't even know was possible at the time.

3. Other people on the SawStop forum can duplicate this problem. Whether you can or not probably depends on all sorts of things, including type of blade and whether the moon is in the seventh house or not. (Just kidding. Sort of.)

<span style="color:blue">**So, here's some of the ways the issue manifests itself, and then I'll discuss what I think is happening.**</span>

---

### Case #1: Raising the Blade Fast, with a Sled

When I use one of my cross-cut sleds with the Infinity insert, and I raise the blade up quickly, I get the flashing light. In this case, it usually flashes for 20-25 seconds, but if you're not looking for it, you may not notice.

{% include youtube-player.html id="Y6a1YTZ7hTI" %}

<p style="margin-top: 22px">I first noticed this when I tried to start the motor pretty soon after I raised the blade. I didn't see the flashing light at first, but when I turned on the motor and it didn't start running, that's when I noticed the flashing light.</p>

<p></p>

---

### Case #2: Raising the Blade Fast, *without* a Sled

As I mentioned before, at first I thought I could only duplicate the problem when I used my cross-cut sled, so I spent some time down the rabbit hole of trying to figure out what was wrong with my sled.

But it turns out it's just *easier* to duplicate with the sled. Without the sled, I have to raise the blade quickly and usually almost all the way up before I get the flashing light.

{% include youtube-player.html id="teFxWPjpCvk" %}

<p style="margin-top: 22px">So I'll use a sled for the rest of the examples, but as I said, you *can* duplicate them without a sled. It's just a little more finicky.</p>

<p></p>

---

### Case #3: Raising the Blade Slowly

If I raise the blade slowly, and stop as soon as the I get the flashing light, the light stops flashing much more quickly. I can keep repeating it if I'm slow enough.

{% include youtube-player.html id="RvyV0XLbBF8" %}

<p></p>

---

## Case #4: Touching the Sled

This case happened while I was creating these short videos. In this clip, it took WAY longer than 20-25 seconds for the light to stop flashing. I had no idea why. But as I was typing this section of this article, I had a brainstorm.

I wonder if, when I touched the sled, it restarted the **DSP**'s internal timer. So I started my timer *after* I released the sled:

{% include youtube-player.html id="7j2flLVxncs" %}

<p style="margin-top: 22px">And yep, that's exactly what happened.</p>

<p></p>

---

## Case #5: Raising the Blade Slowly *without* a Sled

This final case shows that if I raise the blade slowly, without a sled, the light never flashes. I can do this *with* a sled also, but I have to raise it *excruciatingly* slowly, so I won't subject you to that torture.

{% include youtube-player.html id="t8u-vq8rFsk" %}

<br/>

<hr class="hr-thick">

<p></p>

## ![](/assets/images-posts/2019/07/2019-07-03.1.14.jpg){: width="150px"}{: .image-border} <span style="color:black">Drawing Conclusions</span>

So how do we account for what we've just seen? Let's see if I can make sense of it.

### Different Rules

First of all, whatever effect the insert plate has on the electrical signal, it's apparently different from the effect that touching flesh produces, so it seems like a different set of rules applies. Or else it's the same rules, but since they're being applied to a smaller effect, the rules produce different results.

### Surface Area

I don't know for sure *where* the insert plate's proximity to the blade is having the greatest effect, but let's say it's where the blade goes ***through*** the kerf in the insert plate.

When the blade is all the way down, not much of the blade is near the kerf, so there isn't much change to the signal. As I raise the blade up, a wider and wider section of the blade passes through the kerf. And with more surface area in proximity, the effect is greater.

### Cases

So let's look at some of the cases mentioned above.

1. **Case #1: Raising the Blade Fast, with a Sled:** Since the <span style="color:blue">**surface area**</span> of the blade passing through the kerf <span style="color:red">**increases quickly**</span>, the <span style="color:blue">**effect on the signal**</span> <span style="color:red">**increases quickly**</span>, so the **DSP** thinks there's an issue and takes action.

2. **Case #2: Raising the Blade Fast, *without* a Sled:** For some reason, a cross-cut sled amplifies the proximity effect. I don't have an explanation for this, but since it happens, it's apparently true.

3. **Case #3: Raising the Blade Slowly:** When I raise the blade <span style="color:blue">**slowly**</span>, the surface area of the blade passing through the kerf i<span style="color:red">**ncreases slowly**</span>, so the <span style="color:blue">**effect on the signal**</span> <span style="color:red">**increases slowly**</span>. The **DSP** decides this is enough of a change to warrant either a warning or action, so it starts to flash the light. But when I quickly stop raising the blade, the effect on the signal stops changing, so the **DSP** apparently decides "Never mind".

4. **Case #4: Touching the Sled:** I don't know why my touching the sled has an effect. But apparently it does.

5. **Case #5: Raising the Blade Slowly:** This is the important one. If the change to the signal happens over a slow enough period of time, the **DSP** apparently isn't too worried about it.

<br/>

<hr class="hr-thick">

<p></p>

### ![](/assets/images-posts/2019/07/2019-07-03.1.21.jpg){: .image-border} How Come Nobody Notices This?

My theory is this:

1. People don't generally raise the blade quickly while it's running.

1. If you *do* raise it while it's running, like when you're cutting the kerf into the insert blank, you raise it very slowly.

## ![](/assets/images-posts/2019/07/2019-07-03.1.22.jpg) And this is when I wanted to crawl in a hole:

I had some more ideas, and I wanted to test them. So I tried to duplicate the issue while running the saw in bypass mode.

Guess what? <span style="color:blue">**I couldn't get the warning lights when running the saw in bypass mode.**</span> No matter what I tried.

And if the warning lights won't happen in bypass mode, there's a 99% chance that <span style="color:red">***this issue will never trigger the brake, when running in normal mode***</span>.

### And that means...

* Well, first, it means I'm a frigging idiot for not testing this first.

* I wasted 10 days tracking down the reasons for a problem that ended up being irrelevant. *So what* if the warning lights come on in standby mode? If it's not going to affect the saw while it's running, then it just doesn't matter.

* After spending all this time writing this article, I'd either have to trash it, or publish it as is.

Which means that yes, I sort-of tricked you into reading an article that's probably not going to help you in the least.

<span style="color:blue">***But hey, what would you have done?***</span>

{% include youtube-player.html id="fZLeaSWY37I" %}

<br/>

<hr class="hr-thick">

<p></p>

### I'll post my final conclusions on the Infinity plate in an upcoming post.

Later.

{% include footnote-title.html %}

[^1]: At least I don't think I am. But if I am, it's only because I got lucky, not because someone told me something they shouldn't.
[^2]: Source: a SawStop employee.
[^3]: It's probably more than just the signal strength that changes - I'm sure it's more complicated than that. But just go with it for now.
[^4]: I think. 😛
[^5]: It *might* flash lights, I'm not sure.
[^6]: Actually, it uses harsher words than that, but this is a family blog.
[^7]: The proximity effect probably applies to other conductors as well, of course. And I don't know the minimum distance.
[^8]: It might be a different *type* of electricity, I'm not sure, but the concept is similar.
[^9]: As it turned out, I should have investigated this further, as you'll see...
