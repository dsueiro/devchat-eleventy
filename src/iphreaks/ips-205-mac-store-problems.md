---
layout: layouts/post.njk
title: >
      205 iPS Mac Store Problems
date: 2017-07-06 04:00:26
episode_number: 205
duration: 49:26
audio_url: https://devchat.cachefly.net/iphreaks/iPS_206_Mac_Store_Problems.mp3
podcast: iphreaks
tags: 
  - iphreaks
  - podcast
---

* * *

#### Mac Store Problems.
On this episode of iPhreaks we have panelists Gui Rambo, Erica Sadun, Andrew Madsen, and Jaim Zuber. Check in to hear the crew talk about Mac store problems and a bit about the differences in developing Mac OS apps vs iOS apps. Gui Rambo gives us some insight about writing Mac OS apps from iOS apps and the panel digs into the potentials of Apple TV. Don’t miss this one.
* * *

##### Gui How did you get started converting iOS apps to Mac?
Gui talks about being a fan of Mac and being a Mac user and when the iPhone started having apps he didn’t have an iPhone so he started developing for Mac. Soon after he started developing for iOS as well.
##### What are some examples of apps you’ve converted?
He talks about the most famous being the WWDC app. He is in the process of working on it now. He talks about how the code is old and clunky, being that he wrote it on Swift 1. It was inspired by Apple’s WWDC app. Gui reversed engineered it and brought it to the mac. Instead of looking at source code Gui reversed engineered the application using HTTP proxies and looking at what API they were using. He found that it was mainly JSON hosted on AWS storage, and the app downloads them and parses them and that’s about it. Erica adds that the application has been a huge contribution to the development community and for WWDC attendees.
##### Can you tell us about your design philosophy?
Gui mentions that it depends on the app itself. Sometimes the iOS app is a companion to the main Mac application while other times it’s the opposite. In some cases apps are independent of each other. In most cases the iOS is just a remote version of the main Mac OS app. Sometimes the Mac OS app lacks. Gui likes to see both apps to be full of functionality.
##### What apps are less featured on the Mac vs iOS?
It’s most common that there is no Mac app at all. Using features of the iOS app in many cases will only have a web browser version for the Mac. In many cases this is happening because it’s harder to develop apps for the Mac OS. The frameworks are older, the foundation is the same, but taking a Mac OS app and making an iOS app isn’t easy or simple.
##### What are your thoughts about developers and the decision of publishing outside the app store?
Gui mentions that he sells an app called Browser Freedom that he sells online as well as in the app store. The application uses a set of rules to decide which browser it should open, along with other features. He decided to do both to find which would sell more. Despite that Apple takes 30% of sales from the app store, he is selling much more from the app store. Another consideration is if the application was made before sandboxing it may not work and may restrict some features you may want to add that won’t work. Applications for Mac OS must be sandboxed, making it so they are not allowed to write on the disk. A common issue that comes up for apps would be any application that has a built in file browser. In many ways Mac OS apps are more restrictive than iOS apps
##### Is it fair that Mac developers are moving away from the Mac App Store?
Gui talks about it being fair. If the Mac App Store is lacking features then it make sense for developers to move away. One thing that is missing is the Test Light system. The Test Light System is something that Apple provides for the iOS store that allows the developer to create a beta of applications via invites before the full release. The Mac App Store still does not have this feature. The app store lacks features more for the developer than it does for the user.
##### Can you tell us more about upgrade pricing?
Upgrade pricing has been an important price model since software exists. You pay for the application initially and then over time if you want to upgrade or add feature you pay some small price for that. Allowing for cashflow from existing customers. Some developers found ways around it by making new versions a completely new app on the store but it’s still very messy.
##### Whats the theory behind Apple pushing subscriptions?
Gui talks about how subscriptions have a different psychological effect on people. Having to pay for something monthly or annually is different from thinking about a single purchase. Many people are not willing to go through that sort of commitment. Apple isn’t in the business of selling software. Subscription as a pricing model isn’t necessarily part of the future that Apple intends to have. Their focus is to sell the hardware and would be just as happy to see applications for free.
##### Is Apple not supporting upgrades part of Apple philosophy?
Gui says that if you think about Apple’s philosophy, they always have thought of the users first. Apple would like to have their customers pay once for software but, Gui states that he thinks that there may be some technical issues that involves upgrade pricing to make that it available. Erica adds that it’s on the record that Apple has said that adding upgrades to the App Store would take major engineering. Gui adds that the Apple App Store is an old system that was designed based off of an older iTunes system and would be hard to implement changes on.
##### What about discoverability.
Gui talks about developers deciding to develop for iOS just due to the greater number of people using iOS and mobile being the future. He adds that you can make plenty of money making Mac OS apps as long as it’s well done and polish and if you’re giving a niche market something it really needs. Apps don’t get famous like they do for iOS. You have to find your market and make sure it’s niche enough. There are often too many apps of the same category that do similar things.
##### Ugly apps that make it and word of mouth marketing.
Gui talks about how the icon can be a game changer if it’s not good. Apple users tend to find how polished an app is to be vital to if they use that. Erica adds that there are some cases where ugly apps make it, but generally because they have great features and tend to get traction by word of mouth, specifically for Mac applications. iOS tends to push apps in places like spotlight, while on Mac OS, applications aren’t pushed nearly as much, needing word of mouth to get traction. There are many tools that become very popular despite lacking a polished graphic UI, some being command line tools. These tools make it because they actually solve a problem.
##### If someone is trying to sell something in the Mac App Store, what else is there to consider?
Erica adds that integration between the hardware for application becoming something that people expect. The Mac application has become almost a bonus to the iOS app, and people tend to look for their iOS apps to have versions on the other platforms. Gui adds that he would like to have applications on the Mac like Youtube. He wishes that Apple would make it easier to make iOS counterpart Mac applications. There are many apps that could be imported without that much work. The underlining framework can sometimes be very similar.
##### What about the Apple TV?
The exception may be Apple TV. It tends to mainly work for content consumption but allows for things like games. Gui adds that he tried coming up with an Apple TV app but couldn’t manage to think of one that would work. Eric mentions that Apple TV could work really well with applications revolved around parties, where it doesn’t necessarily need interaction but has some sort of features that work well while the owner has company. She also mentions that Apple TV could use a check ins feature, where the TV connects more with the Health Kit or todo reminders or personal coaching features. She suggests it could be a great win for Apple. Gui adds that the Apple TV would also do well with multiple user support where people in the room can all use it together in ways at once. Everyone bounces ideas back and forth about ways to use Apple TV for things like biometrics and other ways Apple TV could tap into integration with other Apple platforms. Apple TV adds a potential to get users away from the computer.
* * *

#### Picks

##### Gui
[Watch WWDC sessions on WWDC App](https://itunes.apple.com/us/app/wwdc/id640199958?mt=8)[Simpholders](https://simpholders.com/)
##### Erica
[The Rithmatist Brandon Sanderson](https://www.amazon.com/Rithmatist-Brandon-Sanderson/dp/0765338440)
##### Andrew
[The Living Computer Museum in Seattle](http://www.livingcomputers.org/)
##### Jaim
[Blog post on the four major frameworks of Swift](https://medium.com/@rymcol/current-features-benefits-of-the-top-server-side-swift-frameworks-b15b4f2d7bc3)

### Transcript


