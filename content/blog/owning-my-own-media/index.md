+++
title = "Owning My Own Media"
description = "The Real Cost of Physical Media"
date = 2024-05-23
draft = true
[taxonomies]
tags=["media", "homelab"]
+++

The idea of owning and having the rights to my own media collection has been alluring to me lately. Maybe I've been watching too much Louis Rossman and Jeff Geerling, but lately I've been having the urge to drop the streaming services and switch to a media collection that I've intentionally chosen and curated, and one that I have all the rights to, where items can't be removed from my collection without my consent.

[Skip to TLDR](@#TLDR)

## Goals for this project

Going in to this project, I had the following goals in mind:

🎥 Be able to watch content in the same quality I would get from a streaming service (4K HDR with Dolby Vision and Dolby Atmos).  
🍿 Make it as easy for the rest of my family to use as software like Netflix.  
📀 Be able to keep my media even if a company decides to no longer offer it.  
🕵️ Keep my data private and out of the hands of Big Tech.  
📖 Use free and (ideally) open source software.  
💸 Hopefully save some money!

## The Setup

### Hardware

To run this operation, I'm storing all my data on my homelab server (blog post coming soon). It's an Intel n305 CPU which is an excellent CPU for a media collection, because it provides hardware transcoding to a lot of formats with Intel QuickSync, with a low TDP. In my homelab, I have five 16TB drives in RaidZ2, for a total of around 44TB of usable storage. This is probably incredibly overkill, but I wanted to be sure I had enough storage for the time being for whatever life throws at me.

My [rack mounted server case](https://www.amazon.com/dp/B0BN1XBL2R) came with two 5.25" drive bays, which is awesome. That means I can directly rip my DVDs onto my NAS, and don't need to plug in some kind of external DVD drive into my network rack, or rip them on another computer and upload them over the network. [Here's the internal DVD drive](https://www.amazon.com/dp/B007VPGL5U) I'm using.

### Software

On the software side, I'm running proxmox as my main OS. I have an LXC container with Docker, and it's running Jellyfin to serve my media collection to clients. Jellyfin is great, but unfortunately, the Apple TV client is not. However, I'm not willing to pay for a Plex Pass to get hardware transcoding, live TV, and other great features that Jellyfin offers for free, so I'm sticking with Jellyfin.

I also have a docker container running MakeMKV. This is the softwate that allows me to pop DVDs into the drive in my network rack and rip them directly onto the server.

## Cost Analysis

It's hard to compare the cost of owning your own media to that of subscribing to streaming services. Owning your own media leaves you with a very finite selection, while streaming services offer a seemingly infinite collection of movies, albeit a collection that you'd unlikely ever be able to finish within a lifetime. However, I will do my best to compare the costs as accurately as I can.

### Media Costs

The cost of both physical media and streaming services varies widely depending on quality, number of viewers, etc. Because of this, I'm going to attempt to analyze the cost in a "tiered" manner that attempts to emulate the tiered models of streaming services, to hopefully help you get a more accurate picture of what you might expect to pay if you wanted to own your own media like I've done.

Here's the cost of several popular streaming services. I tried not to include ad supported plans if possible, since ads do not exist in the physical media realm.

|Streaming Service  |Monthly Cost (HD)  |Monthly Cost (UHD) |
|---                |---                |---                |
|Netflix            |$15.49             |$22.99             |
|Hulu               |$17.99             |$17.99             |
|Disney+            |$7.99(Ads)         |$13.99             |
|Prime Video        |$11.99             |$11.99             |
|HBO                |$15.99             |$19.99             |

*Note: These prices are accurate as of May 2024.*

For a cost comparison of physical media, I sourced a lot of my prices from eBay. Obviously it's possible to buy a lot of movies brand new, but I think the cost of new physical media is just too high for you to have any hope of spending an amount comparable to streaming services.

|Media Type         |HD (1080p) |UHD (4k)   |
|---                |---        |---        |
|Movie              |$6         |$13        |
|TV Show (1 Season) |$12        |$40        |

As you can see, buying TV shows in 4k is not very economical at an average price of around $40/season. But the 1080p price is pretty affordable!

I didn't include the cost of regular 480p DVDs, but if you're willing to sacrifice quality, they can be had abundantly for very little money, just a couple of dollars. Some great places to find DVDs are used book sales like from libraries, and thrift stores like Goodwill and Half Price Books. I went to a used book sale with my wife that was being hosted by our local library, and we were able to purchase as many DVDs (and even some Blu Rays) that would fit in a bag for $20.

### Hardware Costs

I'm going to make some assumptions in my hardware cost for this setup, mainly that you already have a computer that's capable of running software like Plex or Jellyfin. However, I will also compare the price of buying an off the shelf NAS. If you have a home server or DIY NAS, then I'm assuming you don't need me to tell you how much you spent on it, and if you're thinking of building one, you can calculate the cost yourself.

For my current collection of 37 DVDs/Blu Rays, the average size of each movie came out to around 31GB. This includes a mix of standard 480p DVDs, as well as 1080p and 4k Blu Rays. The total for me right now is 1.15TB of storage. If you were to watch one movie a week with no repeats, you would need about 1.6TB to store all those movie files. I don't have any TV shows for reference, but based on the DVD's, I'm going to assume that it's about 15GB/hour, but likely less if you're not purchasing outrageously priced 4k TV Shows. If you were to watch 3 hours of TV in addition to that one movie/week, you would need about 2.3TB to store all your TV shows.

## TLDR

For most people, it's unfortunately pretty hard to recommend owning your own media. The upfront cost is just so large. Thankfully, off the shelf NAS solutions make it pretty easy to spin up a Jellyfin server for your media, and there's a ton of tutorials on YouTube on setting up Jellyfin and using MakeMKV. But with the cost of the NAS, drives, and DVDs, you're much better off paying for a streaming service.
