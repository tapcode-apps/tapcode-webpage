---
layout: post
title:  Behind the Scenes: Shipping Thirstic
categories: [Apps]
excerpt: It was a hot and sunny weekend in Kelowna, British Columbia in July 2015. I've just moved to Canada with my girlfriend, after we both finally received our visas for the International Experience Canada program. I bought a used city bike, mainly for commuting to work, but on this weekend I wanted to explore the surrounding area of this beautiful small city.
permalink: /2019/09/09/behind-the-scenes-shipping-thirstic-to-the-app-store/
---

<a href="https://tapcode.co/images/kelowna_thumb.jpg"><img src="https://tapcode.co/images/kelowna.jpg" style="width:100%;" alt="Kelowna Lakeview"></a>

It was a hot and sunny weekend in [Kelowna,](https://en.wikipedia.org/wiki/Kelowna) British Columbia in July 2015. I've just moved to Canada with my girlfriend, after we both finally received our visas for the [International Experience Canada](https://www.canada.ca/en/immigration-refugees-citizenship/services/work-canada/iec.html) program. I bought a used city bike, mainly for commuting to work, but on this weekend I wanted to explore the surrounding area of this beautiful small city. Most people don't think at hot, sunny lakeside towns when they think about Canada. Kelowna, and the other cities in the Okanagan Valley, are just that! In the summer, daytime temperatures often exceed 32 °C (90 °F) and on extreme days they go up to 40 °C (104 °F). Turns out that, even smaller cities can be quite large (in terms of area) in Canada. 😆

I pushed my city bike through streets and over hills. After a couple of hours I found myself on a path through a forest. My crappy bike was obviously not made for a track like this and the sun was merciless burning on my back. What made things worse, was that I only had one bottle of water with me, which was already almost empty when I arrived in the forest.

<div class="row">
  <div class="column">
    <a href="https://tapcode.co/images/kelowna_biking_1.jpg"><img src="https://tapcode.co/images/kelowna_biking_1_thumb.jpg" style="width:100%" alt="Kelowna Biking 1"></a>
  </div>
  <div class="column">
    <a href="https://tapcode.co/images/kelowna_biking_2.jpg"><img src="https://tapcode.co/images/kelowna_biking_2_thumb.jpg" style="width:100%" alt="Kelowna Biking 2"></a>
  </div>
</div>

## I was wondering...

So, I was taking another break and I was looking at my burned calories on my Apple Watch (Series 0 at that time! 😅). I definitely closed all of my rings on that day, I can tell you! While I was rationing my last water reserves, I was staring at the trees and thought:  

_**"For a very hot and active day like this, I definitely do not drink enough. What would be my recommended water intake in circumstances like this?"**_  

<div class="row">
  <div class="column">
    <a href="https://tapcode.co/images/kelowna_biking_3.jpg"><img src="https://tapcode.co/images/kelowna_biking_3_thumb.jpg" style="width:100%" alt="Kelowna Biking 3"></a>
  </div>
  <div class="column">
    <a href="https://tapcode.co/images/kelowna_biking_4.jpg"><img src="https://tapcode.co/images/kelowna_biking_4_thumb.jpg" style="width:100%" alt="Kelowna Biking 4"></a>
  </div>
</div>

The core idea of [Thirstic](https://thirstic.app) was born. In the following months I did some research around that topic. Actually, the answer to this question is complicated (as many answers 😉). Quite a few studies engaged with that question in the last decades, with contradicting results on the recommended daily water intake for an adult. However, all of them suggested higher water intakes with increasing activity and/or higher temperatures in the environment. I got obsessed with finding an answer to this problem. Based on all I've read, I developed my own formula for estimating water needs. The two main ingredients are burned calories and the environment temperature.

## Fire up Xcode

In October 2015, I finally fired up Xcode and did that magical "File -> New Project" thing. Back then, I did not have much experience with Swift (version 2.0 was just released). So, I also saw this new side project as a good opportunity to finally learn Swift in more detail. Way too soon, our Canadian visas expired and we decided to move to New Zealand and continue our work and travel experience there.

Arrived in [Wellington](https://en.wikipedia.org/wiki/Wellington), for a couple of months, I was working quite consistently on the main logic part of the app. Since I already knew that estimating water needs isn't an easy task, I created my own internal framework for it (WaterKit). It was especially difficult coming up with a concept that interacts with HealthKit, works with various data sources and at the same time delivers results in a reasonable time. Moreover, I quickly realized that the outside temperature from weather services cannot be used as single parameter for estimating environment conditions. We might not realize it, but in the western world, we spend on average [~90% of our time indoors](https://indoor.lbl.gov/sites/all/files/lbnl-47713.pdf)! Therefore, I needed to create my own indoor/outdoor estimator, that uses a bunch of data to evaluate if your currently in a building/vehicle or out in the open.

Since Thirstic needs to read the users activity data, I always knew that I do not want a server component for this app. Everything should be processed on the device, mainly for privacy reasons but also because I wanted that the app works offline.

## The void

In August 2016, we moved back to Italy. I was busy starting my own small company Tapcode and soon after I accepted projects from various clients. That was bad news for Thirstic. Almost 2 years long I shelved the project, doing the yearly Swift migration, some refactoring but not much more. As it often goes with side projects, starting them is easy, but **shipping is hard**! 🚢 End of 2018, I was almost certain that I will not ship this app. I felt too much time has passed, and many features that I wanted to have in the first version were still missing.

## Let's ship this

I showed the prototype to a couple of friends at that time (special shoutouts to [Frederik](https://twitter.com/frederikRiedel), [Maximilian](https://www.facebook.com/maximilian.perkmann) and [Philip](https://twitter.com/PhilipGiuliani) 🙌). All of them, in addition to my girlfriend (that became my wife in the meantime ❤️), encouraged me to continue working on the app. So, I decided to restart that motivation engine and finish what I've started. In 2019, I mainly worked on the UI of the app. I've created all the necessary logic in the years before, but there was still a considerable effort left to call the app an [MVP](https://en.wikipedia.org/wiki/Minimum_viable_product) (just to sparkle in some buzzwords 😉). The full story of this journey in terms of git commits looks like this: 

<a href="https://tapcode.co/images/thirstic_commits.png"><img src="https://tapcode.co/images/thirstic_commits_thumb.png" style="width:100%;" alt="Thirstic Commits History"></a>

## Release 🎉

After almost 4 years, today I'm very happy to announce that [Thirstic](https://thirstic.app) will finally be available on the App Store on **Thursday, September 12 2019**! If you would like to have early access, drop me an email and I'll add you to the TestFlight beta! 😊 You can also follow the future development and latest news on [Twitter](https://twitter.com/thirstic). Once again I'd like to thank my wife and friends that helped me bringing Thirstic to the App Store. Special thanks to [Ivan](https://www.linkedin.com/in/ivan-ladurner-086413b8/), who not only designed all the icons (including the app icon), but also helped improving the user experience with his valuable advice.  

**Update September 12, 2019**: Thirstic is now available on the [App Store](https://itunes.apple.com/app/id1471500028?&mt=8)! You can read more about all the features in my [dedicated blog post](https://tapcode.co/2019/09/12/thirstic-the-first-smart-water-drink-reminder/).