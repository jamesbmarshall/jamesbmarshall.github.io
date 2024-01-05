---
layout: post
title: Saving Money on IaaS Services
subtitle: Interesting Stuff Newsletter &num;013
share-img: /img/saving.png
summary: "Sell Azure solutions effectively in competitive markets by emphasizing business outcomes & partner value, offering unique propositions as a Microsoft CSP partner."
image: /img/dollars_square.png
tags: [interesting stuff, azure, partner success, microsoft partners]
comments: true
---

👋🏻 Happy New Year, and welcome to this edition of Interesting Stuff, your fortnightly dose of things I think you'll find interesting if you're in the world of Azure, partners, small businesses, and Microsoft. 
I'm James Marshall, an Azure Success Manager at Microsoft, and if you find this content useful, please remember to subscribe and share this with your network. Thank you! 😎

## Some Thoughts

I don't know about you, but I tend to start my working days with a coffee and a browse of the news. "*[UK economy will enter 'grey gloom' until polling day, economists say](https://on.ft.com/3ScxFYR)*", read the headline of the Financial Times yesterday. Happy New Year, my arse! 😒

Still, it served as a reminder that things remain tough and cost management is just as important as ever. It got me thinking about Reserved Instances. They can be an attractive way to achieve some good savings in exchange for a one or three year commitment. But are they always the best way to save money on things like virtual machines? I fired up Excel to find out.

### Using a Sledgehammer to Crack a Nut

In smaller businesses, particularly ones of a more traditional nature, it's pretty common for IT services to remain on all the time, even though they're not necessarily being used. Sometimes it's down to lack of awareness, or technical capability, but whatever the reason: under-used resources contribute to inefficiencies that increase costs.

When these customers do their first migrations into the cloud, they tend to be a lift and shift approach mirroring their existing set up, just on Azure. If the cost topic comes up, many partners first response is "*you can save money on the VMs by buying an RI*", and that's as far as it goes. 

I think that slapping a Reserved Instance on a subscription is like using a sledgehammer to crack a nut. Sure, you'll save some money, but you're paying for the VM to be on 100% of the time, and you're committing for 1 or 3 years. Yes, you can terminate early, but are they really the best way to save money?

### Excel Time

Let's take a fictional simple single server scenario (I wish it was this simple in real life! 😂), using a DS3v2 general purpose VM. According to the [Azure Pricing Calculator](https://aka.ms/azurepricingcalc), deploying this in UK South without any adjustments like RIs, Azure Hybrid Use Benefit, managed disks, etc. it would cost approximately $430 per month*. That's based on it being allocated for 730 hours, or around 30.5 days.

If you took out a one year Reserved Instance, you could bring that down to around $250 per month. Great! *But can we do better*?

Well, let's assume that the services provided by this VM are required 24x7, but outside of working hours and at weekends, the amount of compute provisioned could be scaled down. We could [resize the VM](https://learn.microsoft.com/en-us/azure/virtual-machines/resize-vm?tabs=portal) from a DS3v2 to a DS1v2 using Azure Automation**.

In this example, we'll say that between 7pm and 7am weekdays, and all weekend are 'off peak' where the DS1v2 would be sufficient to cover the needs of users. That's around 462 hours per month off peak, and 268 peak.
Running the DS3v2 VM for 268 hours comes to $157.58 per month, and the DS1v2 for 462 hours would be $67.91 per month. That's $225.50 per month combined - or a saving of around $24.40 per month vs. simply putting the DS3v2 into a one year RI.

Across a year, that could amount to an approximate $293 saving! If you can do this to multiple VMs, the savings grow accordingly. 

The savviest partners recognise that those savings could be put towards tackling the next business challenge that customer is facing, bringing forward projects and creating opportunities to land more professional services sooner.

### Doing in For Real

Obviously, there'll be more to consider in a real world scenario. More servers, complex applications, different peaks and troughs in use, storage and resilience requirements, security considerations, even customer perceptions to adjust for. It just might not be possible to change the size of a virtual machine. There are always [trade-offs](https://learn.microsoft.com/en-us/azure/well-architected/cost-optimization/tradeoffs).

If you want to know more about the best way to think about a cost saving initiative, check out the video in the next section!

The point is that by moving beyond the lift-and-shift migration into a little bit of optimisation *before* implementing Reserved Instances you can potentially achieve considerable savings that retain the flexibility of the cloud but without needing to make a one or three year commitment.

Those savings can open up new opportunities, might mean the difference between the customer staying in the cloud or reverting back to an on-premises deployment, or even switching to a more innovative partner.

### In Summary

Reserved Instances are a great way to control costs for workloads that need to be on 24x7, but they're not the only way to approach the challenge. Using automation and some basic scripting, it's possible to resize virtual machines to provide the right amount of resource at the right time. 

In this article we looked at a scheduled approach, but the same theory could be applied to resource usage, triggering up/down sizing based on real-time use, or triggered by other events.

Every customer will have slightly differing requirements, but a little creativity in solution design can result in even better cost savings and flexibility than an RI alone.

-
_*Your costs may vary, based on your licensing with Microsoft, whether you buy directly or on CSP, etc._
_**I'm not covering the technical details of how you might do this since this is just a high level 'thought exercise', but there is lots of good documentation and lots of blogs out there on how to script this type of resizing using PowerShell, Logic Apps, etc. Like this one!_

## Interesting Stuff from Others

Like a lot of people, I'm a big fan of John Savill and his Azure content. Before Christmas he posted a video that I wish I could sum up and wear as a t-shirt, all about the right way to think about cost savings and what NOT to do. Check it out!

{% include youtubeplayer.html id="a1txqsKSafk" %}

## Until next time...

If you found this newsletter interesting, why share it with your network? I'd love to know your thoughts or suggestions for future topics in the comments below.