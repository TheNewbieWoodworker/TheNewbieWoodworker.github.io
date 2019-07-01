---
title: "SawStop Brake Logic; Infinity Insert Plates"
layout: post
---
![](/staging/2019-06-30.1.01.jpg)
<br/>
<br/>
This post is the culmination of a lot of research, debugging, testing, and general sleuthing I've been doing over the past week, as well as multiple phone calls I've had with SawStop personnel. Even if you think you know everything there is to know about how, when, and why a SawStop brake gets triggered, chances are good you'll learn something new here. ***So don't skip over anything!***

Grab a cup of coffee, put on your reading glasses and sleuthing equipment, and follow along as I tell you a story that'll make your... [^1] never mind, just keep reading.

In case you haven't been following along, this all started with an issue I have with the [Infinity Throat Plate](https://www.infinitytools.com/sawstop-zero-clearance-throat-plate-with-two-inserts-4750){:target="_blank"} and my [SawStop PCS]({{ site.baseurl }}{% post_url 2019-03-24-sawstop-pcs-pt1 %}). If you don't know what I'm talking about, [please read the prior posts]({{ site.baseurl }}{% post_url 2019-06-23-my-infinity-throat-plate-plus-a-cross-cut-sled-triggers-sawstop's-warning-light %}).

> **NOTE:** Although this is article is fairly detailed, I'm not trying to cover every possible scenario.

<br/>

<hr class="thick">

<p></p>

## ![](/staging/2019-06-30.1.05.jpg) <span style="color:black">The Basics</span>

![](/staging/2019-06-30.1.03.jpg){: .align-left}

When the power to a SawStop saw is turned on, the saw sends a small electrical signal through the arbor into the blade (yellow circles). It does this *even when the motor isn't running*.

A <span style="color:blue">**digital signal processor (DSP)**</span> inside the brake cartridge is monitoring the signal for change.

It monitors the signal from ***across the gap*** between the brake and the blade (red circle) [^2].

{:style="clear: left"}

<br/>

<hr class="thick">

<p></p>

## ![](/staging/2019-06-30.1.06.jpg){: width="150px"}{: .image-border} <span style="color:black">Modes</span>

You probably already know this, but bear with me. The saw can be in one of three different modes:

1. **Standby Mode**. The power is turned on, but the blade isn't spinning.

1. **Bypass Mode**. The motor is running, the blade is spinning, but the brake won't fire. The status lights will tell you if the brake *would have* fired, though.

1. **Normal Operation**. The motor is running, the blade is spinning, and the brake will actually fire if the **DSP** thinks it should.

In addition to those, there's a sub-mode for #2 and #3:

* **Spinning Down**. The motor has been turned off, the blade is slowing down, but it hasn't stopped yet. The green indicator light flashes until the blade stops spinning.

<br/>

<hr class="thick">

<p></p>

## ![](/staging/2019-06-30.1.04.jpg){: width="150px"}{: .image-border} <span style="color:black">Signal Changes</span>

So we know that the **DSP** monitors the electrical signal for changes, but be aware:

> The **amount** the signal changes can vary **significantly**. <span style="color:red">**This is an extremely important concept**</span>, and I'll discuss it in the next section.

Here's some things that can affect the electrical signal:

### Us

Obviously the main purpose for the signal is to help detect if the blade touches flesh, like a finger. And since our bodies are basically large capacitors [^3], contact with them will certainly have an affect. To both us and the signal!

### Metal

If the blade makes contact with metal, it will change the signal. If we're touching the metal, the change will be much greater.

![](/staging/2019-06-30.1.07.jpg){: .align-left}{: style="transform: translateY(10px);"}
But what a lot of people don't realize is that <span style="color:red">***even close proximity to metal***</span> can change the signal to some degree. This "proximity effect" will become very important later on.

{:style="clear: left"}

### ~~Hot Dogs~~ Other Conductors

Any other kind of conductive material can also cause the signal to change.

<br/>

<hr class="thick">

<p></p>

## ![](/staging/2019-06-30.1.12.jpg){: width="150px"}{: .image-border} <span style="color:black">Taking Action</span>

<p></p>

I'll discuss how the **DSP** decides *whether* to take action or not, in a moment. But I want to quickly cover some of the actions it might take.

* **The DSP will only fire the brake if the blade is spinning (but see the next point).** Well, technically, I think there's a split second between when the blade stops spinning and the light actually stops flashing, so I suppose it *might* fire if you touched the blade in that split second.

* **If the saw is running in Bypass Mode, the brake won't fire.**

* **The indicator lights will tell you what action the DSP took**, or the action it would have taken if the saw is in bypass mode.

<span style="color:blue">So, when I use a phrase like "take action", this is what I'm referring to.</span>

<br/>

<hr class="thick">

<p></p>

## ![](/staging/2019-06-30.1.08.jpg){: width="150px"}{: .image-border} <span style="color:black">Decisions, Decisions</span>

OK, something has caused the signal to change. Now what?

This is where SawStop makes its money, so to speak. I'm sure the logic and signal processing they do is a closely guarded secret.

### Let's pretend it's simple

For the purposes of this article, let's pretend that the **DSP**'s' logic is based solely on the *strength* of the electrical signal. Specifically, if something affects the signal, the signal strength drops. And if that something stops affecting the signal, the signal strength goes back up.

As I said before, I'm sure it's more complicated than this. But this will do for now.

Here's some common scenarios:

### Nails

![](/staging/2019-06-30.1.09.jpg){: .align-left}
What happens if you hit one nail?

Let's say that the signal drops a little, but the **DSP** decides it isn't enough to be a person, so it doesn't do anything. [^4]

But it remembers. And if you hit some *more* nails right after that, the **DSP** may decide "I don't want to take any chances, this might be a person, so <span style="color:red">***take action***</span>".

{:style="clear: left"}

<p></p>

### Fingers (or hot-dogs)

![](/staging/2019-06-30.1.10.jpg){: .align-left}
What happens if you touch the blade?

Let's say that the signal drops a lot, because your body can conduct a lot of electricity.

So the **DSP** says "**HOLY CRAP!**" [^5] and it <span style="color:red">***takes action***</span>.

{:style="clear: left"}

<p></p>

### Proximity

![](/staging/2019-06-30.1.13.jpg){: .image-border}{: .align-left}
As I mentioned earlier, believe it or not, if metal is just within *close proximity* to the blade, it can affect the signal [^6].

If that's hard for you to believe, don't forget that the **DSP** monitors the signal *across* the gap between the blade and the brake.

And if you've ever been zapped with static electricity by a door knob, then you've probably already experienced the proximity effect.

But neither of those explanations matter, because <span style="color:blue">we can demonstrate the effect</span>, which you'll see in the next section.

<br/>

<hr class="thick">

<p></p>

## ![](/staging/2019-06-30.1.15.jpg){: .image-border}{: width="150px"} <span style="color:blue">Infinity Throat Plate</span>

![](/staging/2019-06-30.1.11.jpg)

**And now, finally, we get to the main purpose of this post.**

> **NOTE:** When I talk about how long the red light flashes, understand that it can vary, and it doesn't always work the same way every time.

On the advice of many people on the [SawStop Users' Group on Facebook](https://www.facebook.com/groups/sawstopusersgroup/){:target="_blank"}, I bought the above [Infinity Throat Plate](https://www.infinitytools.com/sawstop-zero-clearance-throat-plate-with-two-inserts-4750){:target="_blank"}. And something happened right away that had me wondering.

### The Issue

It didn't take long for me to discover an extremely odd problem that started me on a more than week-long journey.

Depending on a lot of different circumstances, sometimes when I was using the Infinity plate and I raised the blade, it would trigger the "Contact Detected During Standby" warning light pattern, which I'll refer to as the <span style="color:red">**flashing light**</span> from here on out.

<span style="color:blue">**It never triggered the brake**</span>, because I never got this while running the motor. But that doesn't mean it couldn't, although let's leave that discussion for a little later.

Here's some things to note, so I don't have to spend a lot of time on them. This article is not a proof, so just take my word for these things. Or not.

1. At first I thought the problem was my cross-cut sled. But after some testing, I discovered that I could get the problem to occur *without* using a sled (more on this in a moment).

2. I verified that the blade is NOT touching the insert plate. I believe this problem is an example of the "proximity effect", which I didn't even know was possible at the time.

3. Other people on the SawStop forum can duplicate this problem. Whether you can or not probably depends on all sorts of things, including type of blade and whether the moon is in the seventh house or not (just kidding. Sort of).

<span style="color:blue">**So, here's some of the ways the issue manifests itself, and then I'll discuss what I think is happening.**</span>

### Case #1: Raising the Blade Fast, with a Sled

When I use one of my cross-cut sleds with the Infinity insert, and I raise the blade up quickly, I get the **flashing light** [^7]. In this case, it usually flashes for 20-25 seconds, but if you're not looking for it, you may not notice.

I first noticed this when I tried to start the motor pretty soon after I raised the blade. I didn't see the flashing light at first, but when I turned on the motor and it didn't start running, that's when I noticed the flashing light.

{% include youtube-player.html id="Y6a1YTZ7hTI" width="770" %}

<p></p>

### Case #2: Raising the Blade Fast, *without* a Sled

As I mentioned before, at first I thought I could only duplicate the problem when I used my cross-cut sled, so I spent some time down the rabbit hole of trying to figure out what was wrong with my sled.

But it turns out it's just *easier* to duplicate with the sled. Without the sled, I have to raise the blade quickly and usually almost all the way up before I get the flashing light.

{% include youtube-player.html id="teFxWPjpCvk" width="770" %}

So I'll use a sled for the rest of the examples, but as I said, you *can* duplicate them without a sled. It's just a little more finicky.

<p></p>

### Case #3: Raising the Blade Slowly

If I raise the blade slowly, and stop as soon as the I get the flashing light, the light stops flashing much more quickly. I can keep repeating it if I'm slow enough.

{% include youtube-player.html id="RvyV0XLbBF8" width="770" %}

<p></p>

## Case #4: Touching the Sled

This last case happened while I was creating these short videos. In this clip, it took WAY longer than 20-25 seconds for the light to stop flashing. I had no idea why. But as I was typing this section of this article, I had a brainstorm.

I wonder if, when I touched the sled, it restarted the **DSP**'s internal timer. So I started my timer after I released the sled:

{% include youtube-player.html id="7j2flLVxncs" width="770" %}

And yep, that's exactly what happened.

<br/>

<style>
hr.thick {
  height: 5px;
  border-color: teal;
  background-color: teal;
}
</style>

<hr class="thick">

<p></p>

## ![](/staging/2019-06-30.1.14.jpg){: width="150px"}{: .image-border} <span style="color:black">Drawing Conclusions</span>

1. It appears to be OK to use the Infinity plate, as long as you raise the blade *before* you start the motor. But I can't promise anything.

1. It appears to be OK to run the motor and raise the blade ***slowly***, like you do when you first cut the kerf in the insert. But if you want to be safe (brake-wise), I'd consider using bypass mode anytime you want to raise the blade while it's running.

1. If you use a cross-cut sled and want to raise the blade while the motor is running, then I'd definitely make sure to use bypass mode.

1. I feel like I should have more conclusions, so I'd like to hear if you have any other takeaways.

That's it for now!

[^1]: "Notting Hill" reference to the scene where Spike comes into the flat, talking, and doesn't even notice Julia Roberts right there.
[^2]: Source: a SawStop employee.
[^3]: I think.
[^4]: It *might* flash lights, I'm not sure.
[^5]: Actually, it uses harsher words than that, but this is a family blog.
[^6]: The proximity effect probably applies to other conductors as well, and I don't know the minimum distance.
[^7]: The "Contact Detected During Standby" warning light pattern.