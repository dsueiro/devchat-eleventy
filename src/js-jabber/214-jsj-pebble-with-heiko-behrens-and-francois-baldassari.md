---
layout: layouts/post.njk
title: >
      214 JSJ Pebble with Heiko Behrens and François Baldassari
date: 2016-06-01 07:00:38
episode_number: 214
duration: 58:15
audio_url: https://media.devchat.tv/js-jabber/JSJ214Pebble.mp3?rss=true
podcast: js-jabber
tags: 
  - js_jabber
  - podcast
---

### Check out [Newbie Remote Conf](https://allremoteconfs.com/newbie-2016)!
&nbsp;02:11 - Heiko Behrens Introduction
- [Twitter](https://twitter.com/HBehrens)
- [GitHub](https://github.com/HBehrens)
- [Blog](http://heikobehrens.net/)
02:42 - François Baldassari Introduction
- [Twitter](https://twitter.com/baldassarifr)
- [GitHub](https://github.com/franc0is)
03:04 - JavaScript and [Pebble](https://www.pebble.com/)
- [Espruino](http://www.espruino.com/)
- [jerryscript](https://github.com/Samsung/jerryscript)
06:40 - Watch vs Phone
- [Pebble.js](https://pebble.github.io/pebblejs/)
09:32 - Memory Constraints and Code Size Limitations
- APIs
- [rockyjs](https://github.com/pebble/rockyjs)
- [tween.js](https://github.com/tweenjs/tween.js/)
26:24 - Advantages of Writing in JavaScript32:09 - Capabilities of the Watch
- [iPhreaks Episode #153: Using Mobile Devices to Manage Diabetes with Scott Hanselman](https://devchat.tv/iphreaks/153-ips-using-mobile-devices-to-manage-diabetes-with-scott-hanselman)
37:08 - Running Web Servers39:29 - Resources 
- [rockyjs](https://github.com/pebble/rockyjs)
- [Newsletter](http://pbl.io/jsapps)
- [Pebble Slack Channel](http://slack.pbldev.io/)
- [Pebble Developer Page](http://developer.pebble.com)
- [@PebbleDev](https://twitter.com/PebbleDev)
- [Pebble TicToc Source](https://gist.github.com/HBehrens/1a91b97e1e98a6a09c5f)
41:58 - Voice Capabilities43:06 - UI For the Round Face vs Square Face46:18 - Future Pebble Milestones&nbsp;Picks
- [Vortex Poker 3](https://corus-kb.com/en/27-pok3r) (Jamison)
- [Thao & The Get Down Stay Down](http://www.thaoandthegetdownstaydown.com/) (Jamison)
- [Maciej Ceglowski: Barely succeed! It's easier!](https://www.youtube.com/watch?v=5Vt8zqhHe_c&index=2&list=PL2NPrRGOCxjPvTFrAiVWlHEtcroBtlqqX) (Jamison) 
- [The Way of Kings Trilogy by Brandon Sanderson](http://brandonsanderson.com/books/the-stormlight-archive/the-way-of-kings/) (Joe)
- [Juniors Are Awesome](http://juniorsareawesome.org/) (Aimee)
- [octotree](https://github.com/buunguyen/octotree) (Aimee)
- [Fully Alive by Ken Davis](http://www.amazon.com/Fully-Alive-Ken-Davis/dp/B008MTDZ12) (Chuck)
- [Sara Soueidan](https://sarasoueidan.com) (Heiko)
- [Jake Archibald: Using the service worker](https://www.youtube.com/watch?v=SdMxGNkZqnU) (Heiko)
- [beyond tellerrand’s Videos](https://vimeo.com/beyondtellerrand/videos) (Heiko)
- [Fabien Chouteau: Make with Ada: Formal proof on my wrist](http://blog.adacore.com/make-with-ada-formal-proof-on-my-wrist) (François)
- [pebble.rs](https://github.com/andars/pebble.rs) (François)
- [The World of Yesterday by Stefan Zweig](http://www.goodreads.com/book/show/629429.The_World_of_Yesterday) (François)
&nbsp;See Also
- [iPhreaks Show Episode #146: Pebble with Heiko Behrens and Daniel Rodríguez Troitiño](https://devchat.tv/iphreaks/146-ips-pebble-with-heiko-behrens-and-daniel-rodr-guez-troiti-o/)


### Transcript

**_[This episode is sponsored by Frontend Masters. They have a terrific lineup of live courses you can attend either online or in person. They also have a terrific backlog of courses you can watch including JavaScript the Good Parts, Build Web Applications with Node.js, AngularJS In-Depth, and Advanced JavaScript. You can go check them out at FrontEndMasters.com.]_**

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on JavaScript developers, providing them with salary and equity upfront. The average JavaScript developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with the company or deny them without any continuing obligations. It’s totally free for users. And when you’re hired, they also give you a $1,000 bonus as a thank you for using them. But if you use the JavaScript Jabber link, you’ll get a $2,000 bonus instead. Finally, if you’re not looking for a job and know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept a job. Go sign up at Hired.com/JavaScriptJabber.]_**

**_[Let's face it. Bookkeeping is hard and it's not really what you're good at anyway. Bench.co is the online bookkeeping service that pairs you with a team of dedicated bookkeepers who use simple, elegant software to do your bookkeeping for you. Check it out and get your free trial today at Bench.co/JavaScriptJabber for 20% off today. They focus on what matters most and that's why they're there. Once again that's Bench.co/JavaScriptJabber.]_**

**CHUCK:&nbsp;** Hey everybody and welcome to episode 214 of The JavaScript Jabber Show. This week on our panel we have Aimee Knight.

**AIMEE:&nbsp;** Hello.

**CHUCK:&nbsp;** Jamison Dance.

**JAMISON:&nbsp;** Hello, friends.

**CHUCK:&nbsp;** Joe Eames.

**JOE:&nbsp;** Hey, everybody.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. Just a quick shout-out, we're doing Newbie Remote Conf in July. So, if you're a new programmer we have some awesome speakers coming up for you. We have two special guests this week. We have Heiko Behrens.

**HEIKO:&nbsp;** Hi.

**CHUCK:&nbsp;** And François Baldassari.

**FRANÇOIS:&nbsp;** Hi everyone.

**CHUCK:&nbsp;** Do you two want to introduce yourselves?

**HEIKO:&nbsp;** Yeah, sure. So, I'm Heiko. Working with Pebble for, I don't know, more than two years I think now. And I'm mostly involved with firmware work, so software that works on Pebble Smartwatches itself. Most of the work is UI related so everything that moves and is visual on the actual watch. And then I'm also dealing with developer-related tasks. Mostly API design, application model, that kind of stuff. And then as we talk about JavaScript here today, I'm leading the JavaScript efforts to bring JavaScript onto our tiny smartwatches.

**FRANÇOIS:&nbsp;** And I'm François. I'm also with Pebble. And also mostly a firmware engineer, although I try to stay as far away from the frontend graphics, UI stuff as possible. And also on topic, I've been tinkering with JavaScript with Heiko for quite a bit. And I think the two of us have been working on bringing JavaScript to the watch for the past six months perhaps.

**CHUCK:&nbsp;** That's really cool. So, what you're talking about is actually writing apps for the watch in JavaScript? Or are we talking about writing stuff that interfaces with the watch on the device in JavaScript, like on the phone?

**HEIKO:&nbsp;** No actually. JavaScript on Pebble isn't anything that's particularly new. Actually, that has been around for more than one and a half, two and a half…

**FRANÇOIS:&nbsp;** I think maybe two and a half years. I think we shipped the first PebbleKit JS SDK in September 2013 perhaps.

**HEIKO:&nbsp;** Back then it was still under NDA. But the SDK 2.0 which was released a bit longer than 2 years ago opened up JavaScript to the world of developers. But you're right. The concept there is still a bit different. The idea is that you run JavaScript on the phone and can access the internet from there and do anything that's accessible from the phone, say your location, or I think even the accelerometer of the phone although I'm not sure about that. And then you talk via Bluetooth Low Energy, BLE, to the watch. And on the watch you have to have a counterpart written in C. Now with the work François and I and a couple of other engineers are involved with, we fundamentally change this because we bring a JavaScript engine right onto the watch. And that allows you to run JavaScript code directly on the device without being connected to the phone and use all the sensors and everything on the watch itself.

**JAMISON:&nbsp;** So, you say that the watch itself is running JavaScript. But I'm looking at some specs and it's relatively low-powered. So, I assume this isn't just like V8 or something like that. Is it a custom engine that you've written? Or how does it work?

**FRANÇOIS:&nbsp;** So, it's most certainly not V8. Just to remind everybody, the Pebble Time watches have roughly speaking 256K of RAM although much less is available for applications. And about a megabyte of flash storage for software to, for all of the software that we write. So, there was no way that we could get V8 to run in that. And perhaps it's a good place to actually tell you how we got to that.

About two years ago there was a Kickstarter project by a guy Gordon in England who wrote an embedded JavaScript engine called Espruino. I don't know if you've heard of it. But it actually targets devices such as Pebble. I think the dev board that he made for his Kickstarter was STM32 based which is the processor or microcontroller that we use in Pebble. And so, while we don't exactly use Espruino today it showed us that it was possible to actually run JavaScript in an embedded systems with roughly the characteristics of ours. And it got us dreaming about that possibility. So, over maybe last year roughly speaking we evaluated a number of engines and eventually landed on this phenomenal project by Samsung called JerryScript. And that's the engine that's running on Pebble today. And we evaluated for code size and RAM usage, stack usage, performance, and the support that the community could bring to us. And JerryScript ticked all those boxes.

**HEIKO:&nbsp;** So, I don't have you on video chat but do you wear your Pebble Time?

**CHUCK:&nbsp;** Yep.

**FRANÇOIS:&nbsp;** He has to see us.

**HEIKO:&nbsp;** Oh, there. There we go.

[Chuckles]

**HEIKO:&nbsp;** Okay, so he just turned on video. So, if you go to the default watch face there, if you go to the watch face selector and select the built-in watch face Tick-Tock, although it's not noticeable to you or any other end user, that is actually written in JavaScript and it runs directly on the watch. I put it up here for the other people. So, that is running JavaScript directly on the watch.

**FRANÇOIS:&nbsp;** Everybody who's updated to the latest firmware has it on their wrist today.

**HEIKO:&nbsp;** Yeah.

**FRANÇOIS:&nbsp;** That JavaScript engine.

**CHUCK:&nbsp;** Cool. I'm wearing JavaScript on my wrist, guys.

**AIMEE:&nbsp;** [Chuckles] So, I kind of have a naive question. Can you go into explaining why it's preferable to have it actually running on the watch versus the phone?

**HEIKO:&nbsp;** Sure. So, I said before that you could run JavaScript on the phone. So, that would still require you to write embedded C, low-level C code that runs on the watch. And that is quite difficult because of all the pointers you have to deal with, lifespan of data buffers. So, you cannot easily concatenate strings or anything. So, it is really preferable to have a higher-level language, say JavaScript. Now, JavaScript only runs on the phone whereas many of the API calls such as present me something on the screen, show my this bitmap, [order] that label so it shows say the current time, would require you to run C on the watch.

Now, there is another project called Pebble.js and it now happened that we actually employ that engineer, [inaudible], who built something on top of this infrastructure. What he did is he runs JavaScript on the phone and yes, there's still C on the watch but that's totally hidden to the application developer. Instead you remote control the Pebble. You say, “You know, I want to have a label at the top of the screen and it should present this string.” Or, “I want to have a bitmap and put it on the lower half of the screen.” The problem is whenever you want to change something you need to talk from the phone to the watch. And even worse, if you want to interact with the watch, say you press a button, that event needs to be passed via Bluetooth LE to the phone. There you have a JavaScript callback. You say, “Oh, the button was pressed. Please update label to button was pressed.” That information needs to be transferred back to the watch where this tiny C thing would then update the screen. And that adds up to latency. It also means that the BLE, the Bluetooth Low Energy radio needs to be powered all the time, which drains the battery. And it basically also means that you can never use your watch without a phone very much like the very first Apple Watch where everything was belayed].

**AIMEE:&nbsp;** I think it might have been on iPhreaks too, you explained one of the problems with how you had to get SMS to work. Is that also part of the problem that having JavaScript on the watch would solve?

**HEIKO:&nbsp;** No, not really. So at iPhreaks, I was describing that Apple only has so many open APIs to interact with their system. The concept I'm describing here equally applies also to Android where the phone runs traditionally, [run] the JavaScript and have to communicate back and forth with the watch in order to update the screen or interact with the thing. And you can imagine that live things such as updating the time every second or reading accelerometer or compass data from the watch, feeding that back to the phone, processing it and then updating the screen accordingly, is not really something that will work out.

**AIMEE:&nbsp;** Okay. Now that you say that, now I remember that. I forgot. Thank you. [Chuckles]

**JAMISON:&nbsp;** So, I'm still just having my mind blown by this JerryScript thing where the whole JavaScript engine runs in a few kilobytes of RAM. That's like, what is it, React is probably 300 kilobytes or something like that. So, it seems like a different [world] from the way I normally write JavaScript. Do you write JavaScript in a different way because you have to be aware of these memory constraints? Or does it feel fairly platform agnostic? Does that question make sense?

**HEIKO:&nbsp;** Absolutely, yeah. If you just look at say jQuery for example you can easily go beyond 100 kilobytes. And…

**JAMISON:&nbsp;** [Inaudible] just, I mean even just the code.

**FRANÇOIS:&nbsp;** Just minified code, minified code.

**HEIKO:&nbsp;** Minified JavaScript code, yeah. If it's just the library…

**JAMISON:&nbsp;** [Inaudible] even make a single object or anything.

**HEIKO:&nbsp;** Exactly. So yes, code size is definitely a challenge. And then it's also a bit different because a JavaScript developer usually thinks in number of bytes it requires to express, to store the source code. And when you talk about compressing JavaScript you actually try to reduce the number of ASCII characters in your source file so that a browser could download it faster. That is what you usually think about when you do JavaScript. When we run in such a limited environment we are actually more concerned about memory in general. So, can you tell me how expensive it is to create just a naked object? So, curly brace open and close, that's a new object. How much RAM does it consume? A JavaScript developer usually doesn't care. And yes, code size is one question. The second is actually RAM as you are dealing with it. And generally a JavaScript developer doesn't care so much.

And then there's also stack. Whenever you call a function, yes every now and then but only if you do an algorithmic problem, you will hit a stack overflow on a browser. But that is really a depth of say 20, maybe even a hundred calls. And we have another limitation which is bandwidth. So, you think that the internet is slow when you download something? Well, the communication between the phone and the watch runs a Bluetooth Low Energy and we can in the best case scenario transmit 2 kilobytes per second. So yes, we have all these limitations. And that of course affects how you write applications. So, where should we start?

[Chuckles]

**FRANÇOIS:&nbsp;** Well, to answer your questions very directly in the first place, you're not going to take React and run it on your watch. It's just 300 kilobytes of code is just completely out of reach for us. However…

**JAMISON:&nbsp;** Oh yeah, yeah.

**FRANÇOIS:&nbsp;** I think from the very beginning…

**JAMISON:&nbsp;** I was using the…

**CHUCK:&nbsp;** Angular's better anyway, right?

[Laughter]

**JAMISON:&nbsp;** No, I was just using that as an example of these are like the sizes of things that we're used to dealing with as browser developers or Node.

**CHUCK:&nbsp;** Yeah.

**FRANÇOIS:&nbsp;** Oh, and I think your question is tremendous because at the end of the day there has to be trade-offs. But for us from the very beginning of the project we said that we wanted this JavaScript environment to be Stack Overflow compatible. That's the sentence that we used. And that's still our goal today. And by Stack Overflow compatible we meant that we wanted a JavaScript developer who's familiar with JavaScript to be able to go and type, how do I convert a string to an int in JavaScript and get a Stack Overflow answer and paste it in their code and have it work off the bat.

I think that one of the very first demos that we built is we looked up how to convert from normal decimal numerals to Roman numerals in JavaScript. And we built a little watch based in JavaScript that would show the time in Roman numerals using that snippet from Stack Overflow that we had gotten. Our goal to be as close to the experience of developing web applications but on the Pebble. And of course in some cases like trying to import React or trying to allocate a ton of objects in a tight loop or trying to create an infinite scrolling page where you allocate all of the images head of time, of course you won't be able to do that. And so then, our next job will be to make the limitations as explicit and as easy to understand as possible. And so…

**CHUCK:&nbsp;** I have to ask though, with all of these limitations it feels like you're going to get a whole lot closer to the metal so to speak with your JavaScript. I know a lot of JavaScript developers actually write within the confines of these frameworks. So, they have the jQuery… they write jQuery. They don't write JavaScript or they write Angular. They don't write JavaScript. Or they write Ember. They don't really write vanilla JavaScript that says do these particular tasks because we have frameworks that abstract away a lot of the messy parts of that. So, to that sense are people going to have to learn a new way of writing JavaScript in order to write these apps?

**HEIKO:&nbsp;** We hope not. So, we had a long debate here internally how we should embrace these limitations. And yes, language is one thing that François was talking about. But the next one is APIs for example. So, with APIs we could totally tell people to rethink their model by having a different set of APIs than those they are used to. So, we call this whole project Rocky.js, Rocky after the name of a stone, like Pebble. And there you can see how a JavaScript API could look like. And there are actually two different versions out there. One is very close to our C API where you pass in all the arguments in a C-ish way. And the other one is reassembling the web APIs so that particular example is used rendering content onto the screen.

We eventually made the decision that we want to stick to web APIs so that people don't need to relearn, can use their existing tooling, and can put additional libraries on top of that. There's no DOM because we have no… so, there's no HTML. There's no DOM. There's no CSS. That makes jQuery and at least React if you don't think React Native but React with the virtual DOM and all of that maybe a bit less applicable to our platform. But certainly we want people to reuse libraries. So, we do want them to use npm modules for different aspects. As a matter of fact, we have some animation on this Tick-Tock watch in the beginning before our design team removed it, actually before we converted it to JavaScript they removed the animations already. So, we had to remove them as well. But what we did there is we implemented the animations in JavaScript using TweenJS which is a commonly known animation library written in JavaScript. And the idea is that people can still use those.

We overcome these technical limitations by pulling out a few tricks here. So for example, the code the string, the JavaScript code, doesn't even exist on the watch. What we do is, and many JavaScript engines do that, we transform the JavaScript code to bytecode. And that is for the code you are writing as an application. And we don't do that on the watch itself. We do that actually during the build process. And if we find time in the end, there's actually more anecdotes around that. But you build that and we have this bytecode which is A, a bit smaller than the actual source code, and B, as we are running a virtual environment here we don't even need to load that into RAM. As firmware developers we have some tricks here. We can do memory map flash and different other things. That means the 64K an application has today is not even touched by the size of your code. In fact, today applications can have up to 256K worth of resources. That means your code could actually be 265K worth of bytecode which is smaller than your source code. And on top of that you have the RAM. So, that is one trick where we give you more than you actually have.

And then the next thing is… and that still means you have eval. So, you can create a string on the fly and you can eval it and all of that. But then you have to pay for the code in RAM. And the other one is that JerryScript has been designed with these limitations in their mind. So, that means not only is the bytecode super efficient but also how they represent things. They use concepts that are not new but still efficient such as tagged pointers. So, if you have a string that is short enough it's not even stored as a byte array or something. The pointer itself carries the string, if it's just short enough. And if it's a string that existed at compile time they refer to it into the bytecode. And only if it's really a dynamically created string it exists in RAM. And we even have ideas how we could compress that even further. So, we try to make it as memory-efficient when you just look at memory here, as possible.

**JAMISON:&nbsp;** So, I want to ask a little bit more about that topic. I feel like I'm harping on the same thing. It's fascinating to me. JavaScript is a dynamic language. It's garbage collected. And a lot of the characteristics of how we write JavaScript in the browser are because we're generally working on powerful phones or powerful computers where we don't care if we're allocating a bajillion objects, right? It's fine for a web page to use 20 megabytes of memory. So, there are all these features in the language geared around that. But then it almost seems like if you're writing in such a resource-constrained environment you kind of want to think like a garbage collector in a way. You want to try and reuse objects and I don't know. Do you feel like… the motivation for using JavaScript I assume is to enable people to build apps easier. But are you in some ways fighting against the language because it was designed for an environment that doesn't really apply anymore on the watch? Does that make sense?

**HEIKO:&nbsp;** Absolutely, yeah. So, we don't have as much experience as we have today with respect to external developers and how they deal with it. But we have quite a lot of experience when it comes to watch spaces and apps written for our platform. And we understand that a large portion of today's applications, C applications are taking up RAM for code. That doesn't apply to us. And then the second half is actually resources, like assets. They have bitmaps. They have custom fonts. And they want to visualize that. Little is actually going into state of the application.

**JAMISON:&nbsp;** You're talking about the existing C applications on the watch?

**HEIKO:&nbsp;** Yeah. We don't think that JavaScript fundamentally changes the kind of applications people are writing. We hope that we get more developers onto the platform. We also hope that with JavaScript developers oftentimes coming from a frontend perspective we will see more beautiful applications and also more internet-connected things. And I'm happy to talk about that also. We connect that to the internet. But fundamentally it doesn't really change how these applications will look like. That's at least our thinking. Maybe we are wrong here.

If you look at the characteristics of those apps it's mostly the assets. And there again, we have a few tricks here. Because what we do is as we are packaging these, say an image, just think about it. A full screen image that has one byte per pixel on the Pebble Time Chuck is wearing is already worth 24K of uncompressed data. At one point you have to have it uncompressed. Again that's something you usually don't think about. You think about the compressed format such as a PNG or a JPG. But for us it's more critical how large is it in RAM in the end? And we have that problem already. And if you think about that, two full screen images are already almost your entire amount of RAM.

And these are the challenges today's developers have to cope with. Plus their code size. And in our JavaScript world this code size doesn't matter because we actually store it in flash and it's not even loaded. To some respect you could argue that we have a better scenario than our C apps have today. And then yes, you cannot easily load say an array worth 10,000 elements into RAM. But our thinking is that there's no need for it anyway.

**FRANÇOIS:&nbsp;** I think when you were talking about the full screen images there's a very important point there which is that yes, you have two, maybe three orders of magnitude. Your apps will be able to consume two, maybe three, maybe more orders of magnitude less RAM than they do in the browser. But also, your apps will probably do quite a bit less. For example, the displays on the current Pebble, 144 by 168 pixels. That's a lot less pixels than you have to deal with in your browser today for a modern web app. Similarly there's only four buttons. The complexity of the interactions that you're going to be developing for is going to be… all your applications will end up being a lot shallower because of the simplicity of the input and outputs that you have on the display. And so, I think that given the constraints of the device, 64K of RAM in JavaScript is actually plenty to play with to build experiences that are equivalent or even hopefully better than the ones that currently exist for Pebble in C. Does that make sense to you?

**JAMISON:&nbsp;** Yeah.

**FRANÇOIS:&nbsp;** The correlation between the complexity of the platforms and the RAM available?

**JAMISON:&nbsp;** It does. Sure. So, I was imagining having to do all kinds of arcane performance tricks in code to keep memory usage down. And you're saying you don't have to worry about those things that much because you're not going to do complex things in the app itself, really.

**HEIKO:&nbsp;** I wouldn't take it that far. You will certainly run out of RAM. And the problem there is that in JavaScript there is no concept of an out of memory situation, really.

**JAMISON:&nbsp;** Yeah. I was going to ask about that next. [Inaudible] stuff.

**HEIKO:&nbsp;** So [chuckles] yeah. If you think about it in other environments you could totally run out of RAM when you try to allocate a new object. It might not give you an object but null instead. There is never a situation like that in JavaScript. There are a few ideas and proposals around callbacks of high-memory pressure scenario. I can put the link in the show notes. And then there are also… Chrome has…

**JAMISON:&nbsp;** These are platform APIs you mean where there's some event you can listen on when there's memory pressure. Is that what you mean?

**HEIKO:&nbsp;** Yeah. That is, on native platforms they exist. But in JavaScript there is no standardized way yet to communicate that to the application developer. So, if you think about infinite scrolling, François was mentioning that earlier, in infinite scrolling on the browser you could if you want it to be memory efficient, unload images of rows in your long list that are far off the screen and only reload them when you scroll back to the top. But usually you don't do that as a JavaScript developer. And even so, you don't know if it's necessary because you don't know how short you are on RAM.

So, some browsers have proprietary additional extensions to their API. So, you could get a ballpark number how much RAM will I have. And then there are debuggers, like developer tools, APIs to get a better picture. But this is not how you usually write JavaScript applications. I think that we will be faced with that scenario or that event. So, developers may have to care about that a bit. JerryScript already does that. So, for performance reasons they have different lookup tables and caches to find properties in RAM and everything. Every JavaScript engine does that. But they are particularly optimized for that scenario. So, if it happened that the environment doesn't have enough RAM anymore these performance optimizations will be dropped so you free up some RAM. And I think we will do something similar as well.

So, if you for example… so yes, you could load images upfront to speed up something. But if you receive an event, you're short on RAM, please free any RAM that is not critical for your current screen for example. You as a developer will have a chance to free up images and load them again as needed. So yes, that is something that is new. It comes on top of your existing JavaScript thinking though. And then you're right.

**JAMISON:&nbsp;** Sure.

**HEIKO:&nbsp;** We need tooling. So, how do we visualize that? So, Chrome has great tools for example to profile your heap, the application. You can find memory leaks that way easily. Then again, that is V8. So…

**JAMISON:&nbsp;** Yeah.

**HEIKO:&nbsp;** V8 behaves totally different than say SpiderMonkey or Chakra. So, each engine has different characteristics. And optimization practices that apply to one engine may not apply to another one. And we already learned that. So, in-house here when we were iterating on APIs and everything our JavaScript developers told us for example, “Oh, never create a local function within a function and call that. Instead only create naked functions and call it, create that once and call it on the global namespace for example.” because that is more efficient. And that is not JavaScript. That is runtime behavior of a specific engine where [inaudible] this experience. My personal guess is that there was some conference talk or paper somewhere published by some V8 engineer telling JavaScript…

**JAMISON:&nbsp;** I've anecdotally heard that advice, yeah.

**HEIKO:&nbsp;** So yeah, so we recently wrote a bytecode visualizer that shows what the engine will actually do in a scenario A and B. And it turns out that in our engine the nested function is actually cheaper if you don't return the function but call it immediately. Of course if you return it, it needs to capture as a closure. It needs to capture the scope and everything. But if you just call it inline, and not pass all these arguments again and again, it is actually more efficient on our engine. And that might not be true on V8 but it is on ours. Now, the problem is how do we educate developers that are really keen on optimizing their application? And how do we teach that? My hope is that everything runs good enough so that they don't need to care. But at one point yeah, you're right, tooling needs to support developers and educate them.

**CHUCK:&nbsp;** So, I'm curious because I feel like JavaScript opens up the capabilities of doing this kind of development to more developers. But why not just stay with C? Besides the accessibility to programmers what do you gain from being able to write these apps in JavaScript? Are you hoping to get different functionality or better functionality or better apps or something else?

**FRANÇOIS:&nbsp;** So, I think people have been asking of us to make a JavaScript environment available to them that's faster and better and more performant than Pebble.js which was the existing experience when the JavaScript runs on the phone and you pass messages back and forth.

Heiko and I have both spent a bunch of time going to hackathons on behalf of Pebble. And again and again what we find is some very, very eager developers who sit down with their Pebble, google Pebble development, and see our C SDK and get very discouraged because they don't have tool chains installed. Or they use a web IDE and build their first app and it just crashes repeatedly. C is extremely powerful and very high performance. It has all of these quirky behaviors and it requires you understand quite a bit about what goes on under the hood for you not to shoot yourself in the foot with it.

And so, we saw that these people would eventually stumble upon Pebble.js, see developing Pebble apps in JavaScript, wonderful, and start building something. And halfway through the hackathon they'd get stuck because they want to do something more than what Pebble.js offers. And they'd come running to us and then we'd explain to them that this is just an inherent limitation of Pebble.js. And eventually we'd steer them back towards the C SDK and sit with them and just we'd get to see how difficult it is for people who are used to all these high-level programming languages to build applications in C.

So in a way, first and foremost we're responding to customer feedback and developer feedback and trying to build an environment that feels better to the developers who already are trying to build Pebble apps. Additionally by embracing web APIs and building JavaScript support into the watch we're hopefully going to appeal to web developers and get a new crop of developers who have perhaps a new vantage point to bring or new experiences to bring to the Pebble platform. So, it's both responding to existing feedback but also trying to appeal to the broader community of JavaScript developers which today is I think the number one language on Stack Overflow. Most certainly one of the most popular programming languages today.

**HEIKO:&nbsp;** So to me, it boils down to productivity. So, if you do C and it sounds very Microsoft-y but if you think about it just as like a visual developer, how would you do web development today? You would create a web page and then you use the DOM inspector, hit on your element, and then you tweak CSS styles on that particular element until it really fits your needs. Now, in our traditional world, you had to write C code to express whatever you want, like moving things two pixels to the right maybe. And then you need to compile and deploy on the watch. And then you look at the watch. 20 seconds later roughly you will see a result. And then you say, “You know what? Maybe it was just one pixel.” And then 20 seconds later you see that result. Our system is highly visual and highly interactive but our tools are last century. And we really want to close that gap. We want to make it super, super fast and quickly.

Now, let me tell you how we did that. And it sounds strange and it's a slight detour so bear with me. But what we did as the first step when we did this whole JavaScript endeavor is actually quite counterintuitive. Instead of bringing JavaScript into the watch we actually brought the watch into the browser. So, what we did is we cross-compiled the application layer of our operating system using Emscripten to run pixel perfectly and with the same runtime behavior, same RAM limitations, everything, inside of a browser or any JavaScript engine actually. And then we created a JavaScript API on top of that. That was actually our first exploration phase where we would learn which API [inaudible]. Does JavaScript actually do the job? Can we accomplish everything we want to do? And that was all in the browser with all the tools and bells and whistles of a browser. So, you have a real debugger looking into things. Rendering that output the as a canvas element in the browser again. And we've been [there then]. You could quickly iterate.

I think at JSConf last [inaudible] I gave a presentation where I was altering code on the left and you saw the result immediately on the right. And that is the developer experience we foresee for our platform. So, you poke with the code until you have the result you want to see. And we created JS Bins from that. People in the community shared code. We have crazy people who built a wall clock based on that. So, you have a thing that sits on the wall with a larger display. I think he used a tablet or something. And then you can flick through different watch faces and use watch faces the community already built off this browser-based thing just because the JavaScript community being awesome and sharing code. That didn't happen before. People could have totally written an adaption layer to run C applications, Pebble C applications somewhere on another embedded device. But it just did not happen. This whole sharing community and productivity approach thing in the JavaScript community always blows me away. And we wanted to have that.

And now that we have this it will be in the first phase at least our predominant development environment. So, you basically in your browser or your preferred web development tool, have short turnaround times and instant feedback, and then eventually you take that code and run it also on the watch.

**CHUCK:&nbsp;** So, let's talk for a minute about the capabilities of the watch. There are a few things that it does that I really like and as a watch owner and Kickstarter backer, there are definite things that I get excited about. One of them is just that if my phone rings I can look at my watch and see who's calling and stuff like that. The notifications are also really nice to have. But I think you kind of expect that from any watch that has, that is I guess deemed as smartwatch these days. What are the capabilities of the Pebble though beyond that and some of the other basic functions that it already has? Like alarms and we can dig into health tracking in a minute.

**HEIKO:&nbsp;** So, you're asking for the whole experience to an end user or what developers can do with it?

CHUCK:&nbsp; What kinds of things do you expect developers to be able to do with it?

**HEIKO:&nbsp;** Okay. So, first and foremost it has always been the platform where developers can do more or less everything on the watch. So, they literally can access every pixel freely. They have access to all the built-in sensors. So, François mentioned buttons but there's also an accelerometer. There is a compass built into the Pebble Time. We have, I don't know actually. I need to bring up a sheet here I think. But you can create watch faces, applications. Those can talk to your existing either native applications on both iOS and Android or you can create something in JavaScript that runs on the phone. And then with that you can talk to the internet to talk to any other web servers like weather services or sports results or anything. That is optional though. So, all the applications you write for the watch are independently from the phone if you write them that way. And that is great.

So, this weekend for example I was sailing and I could use my watch which wasn't connected to the phone back then because it was down in the cabin. And that watch was just great in that case to show me time. But that is at least something when you're out in the sun. So, it's an always on display. It is water-resistant to what is it, 30 meters or something. And with that you really have a small computer and can write applications of any means actually for the watch. Then recently we introduced something also more web oriented. It's called timeline.

So, from any backend or from your JavaScript that runs on the phone you can talk to a REST backend and personalized information in a chronological dimension onto your own [person's] wrist or your customers or users' wrists. And that can be sports result that change over time, your email, eBay bids. People use it for horoscopes or calendar and sunrise/sunset, all kinds of stuff, weather forecast. But it can be as easy and we actually encourage developers to do that, to do easy, short interactions. So, a typical application is you can configure them to act on a long press when you are on the watch face. You press it. It knows where you are. It calls an Uber. Tells you, “Okay, Uber is on the way. It will be there in five minutes,” and that's it. Or you have a garage door opener and you just press that button and it tells you, “Okay, the garage is now open,” without pulling out the phone, unlocking it, finding the proper app interacting with that application.

So, we encourage developers to do that. But people did all kinds of crazy other things such as full-fledged games or I don't know, browsing through catalogs of products actually, which is ridiculous. But they did that.

**FRANÇOIS:&nbsp;** There's this whole community of people now, I wish I had the link but I will maybe dig it up later, who use Pebble as an on-wrist display to monitor the blood sugar level of their diabetic children because there are a number of Bluetooth-enabled blood sugar monitors. And there are no easy ways to always have on you those readings which can be quite vital. I think that. I was blown away. I think that led to an article on the Wall Street Journal. People have been building incredible things.

**CHUCK:&nbsp;** I'm going to pile on that real quick. We did an episode of the iPhreaks show about that sort of thing with Scott Hanselman. So, he's a type 1 diabetic. I'm actually a type 2 diabetic. But yeah, he talked about how he has connected up all of the monitoring and things to your phone. And I don't see why you couldn't then extend that to your watch.

**FRANÇOIS:&nbsp;** It makes so much sense. Why would you want the time on your wrist if you can have your kids' blood sugar level? That's such important information for you. And it's such a prime real estate.

**CHUCK:&nbsp;** Especially to the extent that with type 1 diabetes you absolutely have to manage it. With type 2 diabetes you can get away with diet and exercise and a few other things. You don't have to be on top of it. But because of the nature of type 1 diabetes where the patient's body doesn't make insulin you have to know what the blood sugar is all the time. And you have to be reacting to it all the time. And so, that's why it's so critical and why it's so nice to be able to just have it readily available for those parents.

**JOE:&nbsp;** I just wanted to talk about, you talked about some really awesome looking apps. But I think one of the questions that's probably been on everybody's minds since the beginning of this is, “Can I run a web server on it?”

[Laughter]

**FRANÇOIS:&nbsp;** What's the smallest web server today? You know, people ran…

**JOE:&nbsp;** Well, I ran one off my Commodore 64.

**FRANÇOIS:&nbsp;** Yeah, people ran web servers on their 1980s computers. And the original Pebble is roughly a Macintosh 128 in terms of performance. I don't see why you couldn't find a web server for it.

**HEIKO:&nbsp;** But you would need to run IP over BLE.

**FRANÇOIS:&nbsp;** Which exists.

**HEIKO:&nbsp;** Yeah. But…

**JOE:&nbsp;** The wheels are spinning already.

[Laughter]

**JOE:&nbsp;** Next release.

**FRANÇOIS:&nbsp;** Somebody's going to build a cloud backend running on Pebbles, like with [inaudible]

[Laughter]

**JAMISON:&nbsp;** Pebble cluster.

**JOE:&nbsp;** Uhuh. Can I hook it up to Firebase? [Laughs]

**HEIKO:&nbsp;** Yeah, people do that actually but as a client of course. The APIs we will expose on the JavaScript level won't allow you to do that. So, it's not… so, the watch will not even grant access to the request API or XHRs because a common JSON response will be too large and will not fit into RAM. So, what we do instead is we separate the two pieces. The heavy, computational heavy part is actually running on the phone. If you do internet you have to have your phone with you anyway. And the actual presentation or a logic maybe even runs on the watch. And again we use standard APIs. So, we do something similar to web workers where you say post message. And it receives on the phone and then you have an event. Oh, I got a new message from the watch. I should do something. Oh, that looks like a URL maybe. I fetch this now and then once I have the image or the JSON response I pick the relevant pieces. And then as I post message again not to your other window, your foreground window [inaudible] the watch. And the watch receives it to present it on the screen.

So, it should actually feel very natural to JavaScript developers. And again you can do literally the same in the browser to get your feet wet and start structuring your application that way. But yeah, a web server on the Pebble itself with that API would not be possible. But people hacked all kinds of things on our operating system already. So, I know that somebody did a Game Boy running, like a Game Boy emulator on top of Pebble, which is…

JOE:&nbsp; Oh wow.

**HEIKO:&nbsp;** Crazy I think, yeah.

**JOE:&nbsp;** That is pretty crazy. So, what about getting into all this and learning it? What resources are out there for tutorials and help and communities?

**HEIKO:&nbsp;** So, people who listen to this show might [inaudible] get a bit disappointed here because what we're talking about is running JavaScript on the watch which is right now not possible to third-party developers. But it's very, very soon. I apologize already here because we never announced it until we finally shipped. But there is already this Rocky project. They can go on GitHub for that. It's GitHub.com/Pebble/RockyJS. And I think we posted the links already. There's also if you're interested in JavaScript in general a newsletter. It's PBL.io/jsapps. But in general they should go to our developer page which is developer.pebble.com. And we constantly update that and they can learn everything around our current possibilities with JavaScript and our future plans. And it's very, very close, I assure you.

**CHUCK:&nbsp;** Yeah, keep…

**HEIKO:&nbsp;** We have a…

**CHUCK:&nbsp;** Keep in mind this will be released in about two or three weeks.

**HEIKO:&nbsp;** So, in two or three weeks you might have some interesting additional content as well that is related to JavaScript. Maybe not necessarily exactly what we were talking about here but it's super, super great. We always… we haven't even talked about health. So, this watch gives you access to steps and all of this. It's crazy. And there's more to come. Then we have the Slack channel. I think 2,000 people or something, at least more than 1,500. We have a Twitter account, PebbleDev I think. And all these links will be shared with the notes, I think.

**FRANÇOIS:&nbsp;** And if you go in the Rocky.js repository on GitHub you will find a number of examples, some written by us, some contributed by the community. Of course the APIs are still in flux. In fact we'd love it if people built applications using the APIs we currently have and propose some changes and give us some feedback on how those things work for them. And hopefully and in the future, certainly in the future, some versions of those APIs will run on the watch and you'll be able to copy paste the app that you wrote for Rocky.js in the browser and run it on your watch.

**HEIKO:&nbsp;** Yeah. As a matter of fact, the source code for Tick-Tock that is running on your watch Chuck is open source. And you can look at it already today. And literally the same code runs in our cross-compiled framework in the browser. And the very same code also runs on the watch today. Not yet for third-party developers because we have to figure out a few minor details. But it's happening.

**CHUCK:&nbsp;** I have one more question about the capabilities on the watch. And that is the voice capabilities on the watch. I know that it came out available for Android at some point and then I think it came out for iOS but I don't remember for sure.

**FRANÇOIS:&nbsp;** It did.

**CHUCK:&nbsp;** It did?

**HEIKO:&nbsp;** Yeah. So developers can similar to the browser's voice API ask for a string that is then dictated by the user. So, C developers already have access to this. And so will JavaScript developers.

**CHUCK:&nbsp;** So effectively, what it is, is there's a microphone on your watch and you can dictate to your watch?

**HEIKO:&nbsp;** Yeah. So, technically on an API level you're asking for a string. You say, “Please let the user talk to the watch.”

**CHUCK:&nbsp;** Right.

**HEIKO:&nbsp;** And then the audio is captured. We inform the end user that this is happening so you cannot spy on them by showing a system dialog. You are talking to your wrist. This is compressed on the watch, sent over BLE to the phone, the phone talks to a rep service to create that string from the audio input, and the string will then be sent back via BLE to the watch where you as an API user will receive the string. And that just happens as the user talks to it.

**AIMEE:&nbsp;** One other thing I was so going to ask about to you that I thought was pretty interesting was the fact that you have the option to develop as far as the UI goes for a round face versus a square face. And I thought the challenges around that were probably pretty interesting.

**HEIKO:&nbsp;** Oh yeah, that's true. Actually, when we developed that we looked at different other standards. And I was hoping so much that the web world would provide an answer to this. And in fact there is a CSS proposal coming from actually the guy who's running around his company, LG. [Chuckles] They were involved [into] that standard. It doesn't really cover much of what we wanted to partly because we don't have a DOM. But also because it doesn't account for scrolling content. And then I was also hoping so much that Apple would release a round watch so they would do the work for us. But unfortunately they didn't. What we ended up with is a lot of convenience and helpers for developers.

So for example, if you logically still operate in a Cartesian coordinate system like a large square and our round watches but as you place a label somewhere you could ask it to follow the curve of display. So, we do the word wrapping in proper positions. And that goes that far that as you are scrolling which doesn't really work if you think about it because you would need to re-flow the text all the time. We actually accommodate for that. So, we do paging instead. We look for orphans which can happen now that you have paging. If your label isn't full screen but let's say it starts halfway of the screen and ends two-thirds later. We make sure that it doesn't… that lines are fully visible in all of this.

So for text for example we have this. And then for other UI elements you would need to position them. So, think of that as you are basically drawing canvas and instead of drawing text you will say “Draw that in a rectangle and do the flow for me. And when you need to calculate the coordinates, it's sometimes hard to transfer your polar coordinate system. I want to have something at a specific angle and give my X, Y, but make it so that the image, the rectangle of the image, is fully visible. Give me that rectangle please, on the top left corner. We have convenience functions for that.

**FRANÇOIS:&nbsp;** We also have a number of canned UI elements which you can push directly to the screen. For example one of them I think is called the action menu. It's a full screen UI element which shows a number of options and lets you, it will highlight the one that's currently selected, let's you click a button and go deeper and deeper into the menu. All those UI elements are available as a single API and will push a UI that's adapted to the display that the user is on.

**HEIKO:&nbsp;** So, on the JavaScript side our plan is to make those micro-frameworks that you can use. I mean, the concept of for example transferring polar to Cartesian so that it's not clipped or to calculate other rectangles like flow of text is not inherent to Pebble as a platform. So, why not make that an npm module and you can use it anywhere including our applications. And then you can already tinker with that in the browser or anywhere. You can share it. You can modify it. But you can also make it part of your application as you are building for Pebble. That's the general notion we have.

**CHUCK:&nbsp;** So, what can we expect in future versions of the Pebble firmware and in future versions of the Pebble watch?

**HEIKO:&nbsp;** So, the next milestone for us is to open this up to third-party developers. Right now we have this one default watch face. That means we can do it. Now we need to open it up. And the first iteration of the JavaScript on the watch will be limited to watch faces. That's our current thinking because it's well understood, simpler application model. So, you won't have button presses for now. But you have all the screen estate at your hand. You can read your current health goals, the steps you made, your location, and all of it. So, you can create beautiful things. And we have tens of thousands of watch faces right now and we expect that to be a great match for a JavaScript frontend developer.

And the other half of that is to improve tooling. Right now we will do the development in this cross-compiled firmware thing, Rocky, inside of the browser. And although it's pretty close to the actual watch there are a few differences. First and foremost RAM. So, the browser will not tell you when the watch will run out of RAM or it cannot tell you how much stack it will require to call 10 levels deep. So, the next step on the tooling side is actually to, and [chuckles] don't beat me here but we internally call that JavaScript inception. So, we will use the JavaScript engine we have, JerryScript, that is written in C. we cross-compile that also to JavaScript. And this JavaScript engine written in JavaScript runs then in the browser so that in the browser you know exactly what the memory characteristics are as you are developing it. It sounds insane. But it's actually that…

**JAMISON:&nbsp;** [Inaudible]

**HEIKO:&nbsp;** It's the easiest path for us to not lose all the tooling you already have. And then the third step on the tooling side is remote debugging where you actually run the engine on the watch and whenever you set a breakpoint or anything, the watch talks to the phone. The phone runs a web server as it does already for development purposes and acts as a… it actually runs the remote debugging protocol from the Chrome dev tools so that you can inspect the state of the engine as it runs on the watch. And again, we also have an emulator and everything already. Of course the same JavaScript engine runs in the emulator. So, you can do that locally without even having access to the hardware. But the end goal is that you can use your browser and talk to your watch with the Chrome dev tools over the phone. That's the developer experience.

And then we are currently developing simpler application models, just mental models. Instead of giving free access to the screen we make the development experience way, way simpler with that approach, I think, so that you can easily create a garage door opener, an Uber application, or a timer, or alarm, something that is inherent to a watch. And it could be that this simpler application model will only be available on JavaScript or first available on JavaScript. So, on our road map JavaScript really is the dominant part right now.

**CHUCK:&nbsp;** Alright. Jamison, do you want to start us off with picks?

**JAMISON:&nbsp;** Sure do. Okay, I have three picks today. The first pick is I got a new keyboard a couple of weeks ago. And I love it. It's called the Poker like hand poker kind of thing. It's kind of a weird layout. It's called a 60% layout so it doesn't have a number pad or separate function keys. So, it's really compact. But I enjoy it. I like keyboards and this is a cool one.

My other pick is a band called, I think it's called Thao or “Tao” or something. Thao & The Get Down Stay Down. It's just like happy, joyful music. I don't know how to describe it really. Happy pop music.

And then my last pick is a talk by the guy who makes Pinboard. He's Polish so I don't even want to attempt to pronounce his name. But he gives fantastic talks and I really like this one. It's called 'Barely succeed! It's easier!' and it's kind of a bit of a takedown of how some of the tech industry works and focuses on rocket ships to the moon. And his approach is basically he just tries to build something that is sustainable and that people like and actually makes money. And he's a really interesting and entertaining speaker. So, I like this talk. Those are my three picks.

**CHUCK:&nbsp;** Alright. Joe, what are your picks?

**JOE:&nbsp;** Well, I'd like to pick every book that I've ever read because so far every book that I've ever read has been awesome. But instead of picking every book, just pick one specific one. And that is the upcoming Brandon Sanderson, that's the third book in 'The Way of Kings' trilogy. And so, I can…

**CHUCK:&nbsp;** Yay!

**JOE:&nbsp;** [Laughs]

**JAMISON:&nbsp;** Oh my goodness. My ears.

**JOE:&nbsp;** It's going to be out later this year. Yeah, sorry about that. That was…

**CHUCK:&nbsp;** Sorry.

**JOE:&nbsp;** I didn't mean to excite him that much. It's the third book in 'The Way of Kings'. What's it called? 'The Stormlight Archive', third book. And I'm really excited for it. So, I've been re-reading books one and two in order to get ready for that. So, I would like to pick the entire series of those books. I've been a huge Sanderson fan since I read the first Sanderson book I ever read. That'll be my pick, 'The Way of Kings' series. And normally I would pick two or three things but they're such big books it will take you a year to read them anyway. So, I think that's like a year's worth of picks.

**CHUCK:&nbsp;** Yep, definitely.

**JOE:&nbsp;** [Laughs]

**CHUCK:&nbsp;** Aimee, what are your picks?

**AIMEE:&nbsp;** Okay. I have two. The first one is a group that I heard mentioned on the Code Newbie podcast. And it looks pretty good. I know there's a Code Newbie [inaudible] but this might be something in addition to that. But it's called Juniors Are Awesome. But I know firsthand that it is really, really beneficial to have other people to talk through. As you get better and better you tend to forget what it was like learning. So, if you don't have the luxury of being around other people like in a bootcamp or something having organizations like this are just amazing. So, yeah it's called JuniorsAreAwesome.org. And there's a link in the show notes.

The other pick is just a small browser extension that I added yesterday that looks pretty cool. It's called Octotree. So, if you're browsing GitHub there's a little button in the top left corner that you can just more easily navigate the file structure. So, that is it for me.

**CHUCK:&nbsp;** Awesome. I just have one pick this week. It's a book. It's called 'Fully Alive' by Ken Davis. And it's really about living your life to the fullest. And it was a terrific book. I listened to it on Audible. It was about five hours long on Audible. It's just not a really, really long book. But if you are looking for something that will inspire you to do better and talk to you about ways that you can live your life to the fullest, live your life 'fully alive' as he puts it then it is a terrific book. So, I'm going to pick that.

Heiko, what are your picks?

**HEIKO:&nbsp;** Yes, originally I wanted to link to an article about how to produce proper SVGs or vector graphics from a designer perspective so you won't end up with all the mess in the SVG file. It's written by Sara Soueidan. And then I realized that actually she, the person will be my pick. She's just awesome. So, she's actually… I'm pretty sure you know about her already but she's actually a frontend developer and she had some good overview about CSS. But her recent content is mostly about SVG and how to deal with them and that's just great.

So, the second one then I realized is actually also a person, Jake Archibald. I think he was on the panel in the earlier days of this podcast. And it's not so much actually about him although I enjoy most of his talks and talking to him in general. But it's about service worker. And service worker, so it's been around a while, is I think underrated right now. I think that is the next great step in the whole web world that brings us closer to the native experience. And if I had to pick anything in particular it's a bit dated and also the audio quality isn't the best but it's his talk at the Generate London 2014.

And my third is a conference run by another fellow German, Marc Thiele. He runs the Beyond Tellerrand among a few other conferences. And the videos of the 2016 issue of that conference just came out last week. So, my pick are those videos. And I think… so, I spoke definitely with Jake together at an earlier Beyond Tellerrand. But I think Sara was also there. So, that says it all. That conference is just awesome.

**CHUCK:&nbsp;** Alright. François, what are your picks?

**FRANÇOIS:&nbsp;** Okay. I got three picks as well. So, the first two are related. I've been super interested in what kind of programming languages people have managed to run on Pebble. And so, the first one is a link from the Ada core team's blog. And they got Ada, the programming language running on the watch. They wrote a couple of apps in it. And then formally verified them which I thought was super cool.

And then there's a GitHub project that similarly lets you write Rust applications on Pebble. I love Rust, have been following the Rust development out of Mozilla for the past two years roughly speaking. And I was really, I built actually a prototype of something similar. But that project is much better than what I had done.

My third pick is a book. It's called 'The World of Yesterday' by Stefan Zweig. If you watched the movie 'The Grand Budapest Hotel' by Wes Anderson it actually I believe, it inspired it. Favorite book of all time. It's about the golden age of the 1920s and living through that and then the horror that happened in Europe all after that. It's really sobering. I recommend it to everyone.

**JAMISON:&nbsp;** This is, the book inspired the movie you said?

**FRANÇOIS:&nbsp;** The book inspired the movie, yeah. The book is old. It was written in the 1940s. But it's still worth the read.

**CHUCK:&nbsp;** Awesome. If people want to follow up, see what's going on with Pebble, with Pebble development options or with the two of you and what you have going on, what should people do?

**HEIKO:&nbsp;** So, we are both on Twitter. For me it's HBehrens. For you it's…

**FRANÇOIS:&nbsp;** Baldassarifr, my last name, first two letters of my first name.

**HEIKO:&nbsp;** I think we need to put the links there.

**FRANÇOIS:&nbsp;** We will.

**JAMISON:&nbsp;** [Chuckles]

**HEIKO:&nbsp;** And then likewise, the Pebble developer account on Twitter is PebbleDev, one single word. And they should get in touch with us on Slack. A very lively community there. I check this community actually before I go to bed and when I wake up in the morning. It's super crazy what people do over there. And then the mailing list I mentioned it earlier for JavaScript would be PBL.io/jsapps and then just subscribe there. All the other links we mentioned before such as the source code for the Tick-Tock watch face I think we better put into the show notes.

**CHUCK:&nbsp;** I also want to just shout out, you did come onto iPhreaks. So, if you want the perspective from mobile developers go check out the episode that we did with Heiko on iPhreaks. And yeah, I also just want to shout out about the watch because it's a great watch. I have friends who have the Apple Watch and I have to say that the thing that really, after talking to them, gives them buyer's remorse more than anything else I think is the fact that I plug my watch in about once every week and a half. [Chuckles] And it does most of what they rely on their Apple Watch for. So, if you're looking for a good option that costs a little less than the Apple Watch and does most of what you're thinking you want, then definitely give the Pebble a look. I have the Pebble Time Steel and I'm super happy with it.

**HEIKO:&nbsp;** Yeah, and you can soon program on it in JavaScript.

**CHUCK:&nbsp;** Sweet! Alright, well we'll go ahead and wrap this one up and we'll catch you all next week.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Do you wish you could be part of the discussion on JavaScript Jabber? Do you have a burning question for one of our guests? Now you can join the action at our membership forum. You can sign up at JavaScriptJabber.com/Jabber and there you can join discussions with the regular panelists and our guests.]_**


