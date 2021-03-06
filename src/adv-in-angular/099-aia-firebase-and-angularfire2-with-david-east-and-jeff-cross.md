---
layout: layouts/post.njk
title: >
      099 AiA Firebase and AngularFire2 with David East and Jeff Cross
date: 2016-06-30 07:00:29
episode_number: 099
duration: 48:27
audio_url: http://media.devchat.tv/adventures-in-angular/AiA099FirebaseAngularFire2.mp3
podcast: adv-in-angular
tags: 
  - adv_in_angular
  - podcast
---

## Check out [Angular Remote Conf](https://allremoteconfs.com/angular-2016)!!
&nbsp;02:01 - David East Introduction
- [Twitter](https://twitter.com/_davideast)
- [GitHub](https://github.com/davideast)
- [Adventures in Angular Episode #11: AngularFire with David East and Kato Wulf](https://devchat.tv/adv-in-angular/011-aia-angular-fire-with-david-east-and-kato-wulf)
02:34 - Jeff Cross Introduction
- [Twitter](https://twitter.com/jeffbcross)
- [GitHub](https://github.com/jeffbcross)
- [Adventures in Angular Episode #68: Reactive Programming with Jeff Cross and Rob Wormald](https://devchat.tv/adv-in-angular/068-aia-reactive-programming-with-jeff-cross-and-rob-wormald)
02:52 - Angular Mobile + [Firebase](https://firebase.google.com/)03:57 - Firebase: Key Characteristics06:22 - Mobile \> Web Traffic?08:27 - Firebase + Angular 210:39 - Upgrading to [AngularFire2](https://github.com/angular/angularfire2) with Angular 213:43 - Data That Works Well15:09 - Interplaying with Traditional Forms of Data20:15 - Intermittent Connectivity Issues21:42 - Websockets Componentry24:14 - Authentication and Security25:48 - Projected Use Cases 
- [firepad](https://github.com/firebase/firepad)
30:53 - Compliance; Security Roles34:11 - What’s coming in Firebase?39:35 - [Firebase YouTube Channel](https://www.youtube.com/user/Firebase)
- [Firecasts](https://www.youtube.com/playlist?list=PLl-K7zZEsYLnJVX_0zbKytptZGugPIbJR)
&nbsp;Picks
- [Ricoh Theta S Digital Camera](http://www.amazon.com/Ricoh-Theta-Digital-Camera-Black/dp/B014US3FQI) (Lukas)
- [Kuula](https://kuula.co/about) (Lukas)
- [Gaia GPS](https://www.gaiagps.com/) (Ward)
- [Procrastinate on Purpose: 5 Permissions to Multiply Your Time by Rory Vaden](https://www.amazon.com/Procrastinate-Purpose-Permissions-Multiply-Your/dp/0399170626) (Chuck)
- [Newbie Remote Conf](https://allremoteconfs.com/newbie-2016) (Chuck)
- [Aftershokz](http://aftershokz.com/) (Jeff)
- [Firebase YouTube Channel](https://www.youtube.com/user/Firebase) (David)
- [Freakonomics Podcast](http://freakonomics.com/) (David)


### Transcript

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on JavaScript developers, providing them with salary and equity upfront. The average JavaScript developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with the company or deny them without any continuing obligations. It’s totally free for users. And when you’re hired, they also give you a $1,000 bonus as a thank you for using them. But if you use the Adventures in Angular link, you’ll get a $2,000 bonus instead. Finally, if you’re not looking for a job but know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept a job. Go sign up at Hired.com/AdventuresInAngular.]_**

**_[Ready to master Angular? Oasis Digital offers Angular Boot Camp, a three-day, in-person workshop class for individuals or teams. Bring us to your site or send developers to ours classes in St. Louis or San Francisco – AngularBootCamp.com.]_**

**_[This episode is sponsored by Telerik, the makers of Kendo UI. Kendo UI integrates seamlessly with both AngularJS 1.x and 2.0. It provides everything you need to integrate with AngularJS out-of-the-box bindings, component configuration, directives, template directives, form validation, event handlers and much more and yet Kendo UI tooling does not depend on AngularJS. So, if you want to use it with Angular or not that’s totally up to you. You can check it out at KendoUI.com]_**

**CHUCK:&nbsp;** Hey everybody and welcome to episode 99 of the Adventures in Angular Show. This week on our panel we have Ward Bell.

**WARD:&nbsp;** Hello, everyone.

**CHUCK:&nbsp;** Lukas Reubbelke.

**LUKAS:&nbsp;** Hello.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. Quick shout-out about Angular Remote Conf coming up in September. We've got two special guests this week. We've got David East.

**DAVID:&nbsp;** Hello, everyone.

**CHUCK:&nbsp;** And Jeff Cross.

**JEFF:&nbsp;** Hello.

**CHUCK:&nbsp;** We've had you on the show before but do you want to reintroduce yourselves?

**DAVID:&nbsp;** Yeah, my name is David East. I'm a Developer Advocate at Google where I work full-time on the Firebase team. And I also do a 20% project, so one day a week I work with the Angular team, right now on the material project.

**CHUCK:&nbsp;** Oh, so you're a 20% Angular team member?

**DAVID:&nbsp;** Yes. 20, one day of the week, Jeremy Elbourn can tell me to do anything. Get his coffee, fix a component or whatever. Write documentation. I'll just do it. I'll just listen to, he's my benevolent overlord.

**CHUCK:&nbsp;** Gotcha. How about you, Jeff?

**JEFF:&nbsp;** I'm Jeff Cross. I'm on the Angular team. I'm a tech lead of the mobile team on the Angular team. We're focusing on making mobile development with Angular 2 really nice. And I work with David East every once in a while as well on the AngularFire2 library for Angular 2 and Firebase.

**CHUCK:&nbsp;** Now if you kind of get what Firebase is I can kind of see how Angular mobile, Firebase, that can all come together for something interesting. But can you tell us specifically how these two projects gel?

**JEFF:&nbsp;** You know, I've been working with the Firebase team since before they were at Google, even on the AngularFire 1 version for Angular 1 we were collaborating early on. And so, it's just always been personally interesting to me and others on the team. We've always been fans of Firebase. And so, their big focus for the past, I don't know, maybe since Firebase started has been mobile applications, making it easy to build these nice features into mobile applications like the real-time database, making authentication easy, and making everything fast and performant and lightweight so it works well on mobile. And so, when we forked off this mobile team earlier this year, we knew that Firebase was one thing we wanted to focus on as well as helping other people in the community build integrations. And so, I just naturally started working with David to build this out even though it's not strictly a mobile tool.

**WARD:&nbsp;** Before we get too far, can David talk a bit about what the key characteristics of Firebase are and how to distinguish itself from other kinds of databases that people might be familiar with?

**DAVID:&nbsp;** Yeah. Well, so it all started out as just a real-time database. And then we realized that people would actually want to log their users in. So, we created an authentication service that handled a lot of OAuth type things just out of the box so you could authenticate with Twitter, Facebook, GitHub, Google, email/password, anonymous authentication. And all that just sort of worked without having to run your own server. And then people were building lots of cool apps and stuff on that. And so, we then created a hosting service or a static hosting provider where you can just through one line on the command line just do Firebase deploy and then boom, you have all of your web apps just right out there for everyone to use.

And then when we came into, we were acquired by Google and they invested tons of resources, the team's grown three or four times the size since we've been acquired. And at I/O we had our big, I don't really exactly know what to call it, not really like a relaunch but we had a big revamp where we added almost over a dozen new features where now we redid our authentication. We added a bunch of features like remote config, which is primarily for Android and iOS apps. We have Google Cloud Messaging, which is Google's way of sending push notifications to Android devices and iOS devices. Got renamed Firebase Cloud Messaging. And so, that's now part of our services. And so, [inaudible] just a ton of new stuff that we have.

And so, rather than just being a real-time database anymore which is just a part of it, we're an entire platform for building applications. Our logo is app success, or our motto is 'App success made simple', because we want to take all that difficult work of not just running backend infrastructure but how do I engage my users? How do I have success? We also integrate heavily with AdMob. So, if you want to actually make money and stuff like that, we have this whole end-to-end cycle from not just building your app but engaging your users and growing and making money as you go along.

**CHUCK:&nbsp;** So, I guess I shouldn't mention that we had the folks from Azure App Service on last week.

**DAVID:&nbsp;** You can mention. They're…

**CHUCK:&nbsp;** [Chuckles]

**DAVID:&nbsp;** Microsoft's got great people.

**CHUCK:&nbsp;** I'm curious. So, it sounds like Firebase is becoming more of a complete mobile platform or mobile support platform as opposed to just like you said, just the real-time database. So, what I'm wondering is as you split the focus… because it felt like Firebase really was sort of focused before on these web applications that could use Firebase as a backend. With you splitting your focus to mobile and to the backend as a service, I'm just really saying this poorly. But I guess what I'm driving at is that should we be worried that you're going to be more focused on mobile than you are on the web traffic? And what are you adding in there for the rest of us?

**DAVID:&nbsp;** Yeah. Well, so there's a ton of stuff I didn't mention. So, I just mentioned what came off the top of my head. But we also released a storage client. So essentially, doing binary file storage. Most people consider that just a way to upload images. But it's truly any time of binary file can go onto it. And so, it's a serverless storage and it has a similar authentication and file system or structure that our real-time database has. And so, that is also available on web. Firebase Cloud Messaging also has a web client that works well on Chrome. Firebase hosting is one of our key features, too.

And so, I won't say that while we did release a lot of features that are primarily for the mobile environment, we have crash reporting which primarily just really works well on mobile, that doesn't mean that we're leaving behind our roots and web. I still work heavily on the Angular team. And like I said, Jeff and I are working on upgrading AngularFire2. We had one of our developers on Firebase hosting work with the Polymer team on creating a brand new PolymerFire library. And there's just a lot of stuff in the pipeline that we have specifically around progressive web apps too that we're really looking into and pushing forward. So I wanted to say, so we do have a lot of new mobile features but I really wanted to say, “Oh, it seems like it's being left behind.” It's just another add-on to the platform.

**WARD:&nbsp;** So, it's wildly expanded since I last paid attention to it [as] the database. Tell us a bit about the intersection with Angular 2 and what's going on there.

**DAVID:&nbsp;** Yeah. So, we had an original binding for Angular 1 where we were, essentially we would synchronize the real-time events. So, for those who don't know about the real-time database, essentially I think I left out the question Ward had originally asked me about how is it different than other databases. Well, with most databases you sort of have almost an HTTP-like model. So, you do a, you make a request out to a database usually in the form of a query, like a SQL query. And then you get a response from it and from that you have your set of data. You do whatever with it.

And with the real-time database it's inverted. You essentially say to your database, “Whenever something changes here tell me about it.” And so, rather than asking for your data you get your data delivered to you in real-time. So, you write with, for the case of a web developer you'd write [another] JavaScript library. I'm very interested when data changes in this location of my database. And when it does, tell me what changed. And so you get this callback function that gets fired off every single time. And that is the synchronized state of your data. And so, you can render that to the view. You can do whatever. And it's all, every update is notified to you within milliseconds. So, it's all quick and in real-time.

And so, for AngularFire 1 we took these real-time observers and we couldn't just use them out of the box with Angular 1 because of the digest loop. So, we integrated that with the digest loop, tried to do it as efficiently as possible. Soon we were just creating thousands of watchers and just throttling everything. And so, we worked on that library a lot. It's one of our, one of the hardest libraries we've worked on as far as integrating with another framework or library goes. And that's gone really well for us. And so, we've learned a lot from that. And so now, with Angular 2 we're taking some of these similar concepts but rather than integrating with digest because you don't need to do that anymore, we're integrating with the observable, with RxJS and Angular. And so, these real-time events work really well when you mix them in with observables.

**CHUCK:&nbsp;** I'm a little bit curious. You talked about AngularFire2 and how it works now with the new way that Angular does things. One thing that I am a little bit curious about is if I am familiar with AngularFire with Angular 1, how different is it going to be for me to integrate or upgrade my app so that I'm using AngularFire2 with Angular 2.

**DAVID:&nbsp;** So, I think that as far as learning AngularFire2 versus AngularFire 1 there's a lot of similar type… so, we sort of follow this binding pattern where we essentially like in AngularFire 1 you would say scope.items is a Firebase array that points at the item's location in my database. And then that would then synchronize this array onto scope. And the way that works is that it looks like a synchronous call even though that's not a synchronize call. Data is downloaded asynchronously but the scope.items starts out as an empty array. And so, no data has gone over the network yet. It just sits there. Now as the data comes back we're going to start populating this array. And every time this happens we're going to fire up the digest loop so that stays in sync with your template and everything and keeps everything kind of magical.

But there is like this famous little GIF, I think Matt Podwysocki showed it at ng-conf where there's the little kid is with the spray hose and he keeps trying to grab the water in the spray hose. And so, every time he's squeezing it, he just can't get it because he's letting go every time he grabs. And that's kind of what this process is like, because while everything updates in real-time and it's awesome you can never catch this array. You can't operate on it. You can't say scope.items.map or anything like that. Because that data is going to be updated over time and later. So, you would have to call a promise on it and so you'd have to say, “Hey, when this data has loaded, now I'd like to operate on it.” But so, the problem with that is that with a promise it only resolves one time. So, you're not going to continue to get those real-time updates. And so, we have a couple of helper functions that allow you to, we call them factory methods that allow you to extend the behavior to fix this problem.

But with AngularFire2, this is where observables come in really, really well. Because observables are collections over time. They're just arrays that live out throughout minutes, days, whatever. It's just arrays in time. And that is what your data in Firebase is. You're storing an array in your real-time database. And then when you're synchronizing that back you're essentially getting that back as an array onto the client. And that array is going to update. It's going to get bigger. It's going to get smaller. And observables are a really, really nice way of modeling that, because it follows that same idea that it's just a collection that can live out over time. And I can map on it. I can reduce it. I can do all the crazy little observable operators. And it just fits in perfectly for what the real-time observers do in the real-time database.

**WARD:&nbsp;** What kinds of data is this best… by the way, I'm totally on board with this. If there was ever a poster child for observables, this is it. What kinds of data are most suited to be created and consumed in this fashion?

**DAVID:&nbsp;** Actually to speak on your point of poster child, when we were acquired, Eric Meyer, one of the godfathers…

**WARD:&nbsp;** Mmhmm. Yeah, yeah.

**DAVID:&nbsp;** He sent a tweet that was like, “My favorite subject Firebase is going on an incredible journey with Google,” or something like that. And he used an observable pun by saying “My favorite subject.”

**WARD:&nbsp;** Yeah.

**DAVID:&nbsp;** So yeah, he used this a lot in his demos. But yeah, so what kind of data works well is that the database itself is just really one big JSON object or one little JSON object depending on how much you're storing. But it's just a JSON object. And so, your, how you access this data is through sort of like a RESTful path you would think of it. So, you could say /items would point you at your list of items where /items/1 would get you to the first item. And so, the further you nest in with the paths, the more specific to your data you get. And it's just the same key/value pairing but it's hierarchical. So, you can have objects within objects within objects as well.

**WARD:&nbsp;** Yeah, that makes sense. I see all kinds of data that fits this pattern. And then there's also a lot of traditional data that sits in a very different kind of store. How do you recommend people interplay… you're not saying are you, everybody suddenly move everything out of your Oracle database into my Firebase one. Maybe you are and that would be a curious statement. So, how do you interplay with traditional forms of data and make an application, and this is a good question also for Jeff. How do we bring these two different strategies together when people have data of these different types?

**DAVID:&nbsp;** What I think is that what the real-time database does well is that when you have data that changes often, quickly changing data or just really when you're structuring application data, NoSQL which there are some databases, a NoSQL database, NoSQL fits in really well there. Because you don't always need the constraints of a schema right off the bat when you're developing. Sometimes you can play fast and loose as you're figuring it out. And then over time you can develop a stronger schema. And it makes it easier to migrate it that you didn't have to specify the specific strict requirements off the bat when you don't even know exactly what you need. And then it's pretty easy to build all your application data. You model your views after, your data structures after your views. And then when you keep that all in sync it just works out really well.

And that doesn't mean you have to migrate completely away from an Oracle database or something like that. Transactional databases, relational databases and stuff, they still have a really great, strong set of use cases. But for a lot of your application stuff when you're just synchronizing data to a client this NoSQL type is, JSON data works out really, really well. And areas where you're probably wondering where it doesn't work out so well is anything that's binary data. This is JSON. So, it's string. It's string-based data. So, unless you want to base64 encode everything which is probably not super-fast to do, you don't want to store that in there.

And so, we also at I/O we released a brand new library called Firebase Storage which is essentially built on top of Google Cloud Storage and it's serverless, binary storage. It's like petabyte scale where you can, I guess the project manager on the team always tells me to say you could build Snapchat on this, he says. That's how scalable this thing is. And it's like, they're really big into how scalable it is. And you can store tons and tons of data and you do it in the exact same structure that you do with the real-time database. So, if I say /user/1 in a real-time database that will pull me back the first user. But for Firebase Storage if I go /user/1.png that could pull me back their profile picture. And so, just by following the convention of the same paths it really handles everything well.

**JEFF:&nbsp;** Yeah, I would agree too that application data is for me that's where I've seen Firebase really shine. And the data that tends to not be updated often or lives in a warehouse somewhere probably either gets copied to that database or gets dealt with differently outside the database. It really depends on the requirements of how you data works, how you would integrate it with Firebase. But yeah, probably, I don't know if Firebase is the best for a large user database that doesn't get updated very often. But David could speak more to that.

**WARD:&nbsp;** [Inaudible] either/or proposition. I think that there are different stores for different purposes. And I think we're past the point where it all has to be one or the other. And I think we have these polyglot database ideas. Don't you think, David?

**DAVID:&nbsp; Yeah** , that's absolutely the case. If you need really strong slicing and dicing of data that's where relational databases and your SQL servers and your Oracle databases of the world give you this crazy powerful querying. And real-time database isn't for this heavy, is not going to spit out some… with SQL you can spill out like crazy XML files or pull query XML files, do all this crazy stuff. Whereas this is really for synchronizing, representing your data, the state of your data in this database and then getting its changes as it happens. And that's where like Jeff's saying, this is where this really shines.

And it doesn't have to be changing every couple of seconds. A lot of people say, “Oh, I don't need the real-time database because my data isn't real-time.” And I tend to think that if… your data didn't have to update all the time to think about things in this way because you would rather get notifications that your data has updated than have to poll a server just to see if anything has changed. You don't always want to make some request just to be like, “Hey, did anything change? I don't know. Nothing did? Alright, that's fine,” where it's better to have the server have, because the real-time database [patch] is a WebSocket persisted from the real-time database servers to your client. And it knows efficiently when something needs to be updated, which is a much more sane model for you as a developer.

**WARD:&nbsp;** Yeah, absolutely. Now, you guys have… you know, the mobile world is a world in which one loses connectivity, says the guy who just sitting at home lost his entire internet connection.

[Chuckles]

**WARD:&nbsp;** But I'll [bet] with this whole real-time idea that you got good stuff for dealing with intermittent connectivity issues.

**DAVID:&nbsp;** Yes. So yeah, if you are in a tunnel, let's say you're using your app on your phone and then you go through a tunnel, you'll likely cut connection. And the real-time database library will continue actually to work offline as it would online for intermittent connections. So, it does a really good job of that. It will actually fire events locally. So, if you save something it won't just hang. It will actually fire that event locally. And then when you regain connection it will persist that right to the server and then any updates that also happened while you were offline get merged down to your client. So, a lot of times people don't even know when they're offline. They're offline for maybe 10, 15 seconds because it just continues to work as it usually would.

**CHUCK:&nbsp;** Hopefully you're not the one driving when you go through that tunnel.

**DAVID:&nbsp;** [Chuckles]

**CHUCK:&nbsp;** And using your app at the same time, I mean.

**DAVID:&nbsp;** I mean, you got to be dedicated to QA testing, you know.

**CHUCK:&nbsp;** That's right.

**WARD:&nbsp;** That's right. It's hands-free. [Inaudible] they're tying this right into the driver-less car thing so that Firebase is driving the car and we don't even know where we're going anymore. Which brings me naturally to…

**CHUCK:&nbsp;** [Laughs]

**WARD:&nbsp;** [Laughs] Brings me naturally to Jeff. I know about the HTTP component in Angular 2 which is a request/response style approach. This suggests we need something in Angular 2 for WebSockets. And Firebase obviously, [I mean] not so obviously, I assume you're using WebSockets. Is that right, David?

**DAVID:&nbsp;** Correct.

**WARD:&nbsp;** So, what have we got going there? What componentry is available or is going to be available to somebody who wants to talk to WebSockets?

**JEFF:&nbsp;** Good question. So, the nice thing that we haven't talked about already is zones in Angular 2 make it so we actually don't need a Firebase library for Angular 2. We don't have digest and that to worry about anymore. So, the actual only reason for a Firebase library is so we could provide these nice abstractions of synchronized lists with observables that fit into these patterns. But to the question of WebSockets we actually thought about it. I think we have a design issue opened on the Angular repo somewhere from probably six months or so ago. And we looked at it and we don't want to add anything to Angular core or to even our maintained projects unless there's a clear need for it. And WebSockets was one of those things where we know some people are using plain WebSockets and they've implemented their own protocols with it, how to batch messages or how to have their own kind of abstractions of rooms or channels or whatever. And then a lot of people are using Socket.IO to manage it and other libraries like this. And Socket.IO even has a library underneath it, like a backend library. I forget what it's called.

And so, we looked at it and we were trying to decide, is there any value we can provide without being too opinionated on? Or is there a right balance we can strike with WebSockets? And at that time it wasn't clear that there was a need for anything like that because you could just, if you are using Socket.IO then you could just use that and use the patterns it gives you. And same with WebSockets. You probably have invented your own protocol. We didn't want to invent a protocol on top of it without enough use cases to design for. And so, we figured the community would probably develop libraries that become necessary. And if it became clear there was something necessary in the core then we would tackle that. But right now, it doesn't seem like it's necessary. Unless you would like one, Ward. Then I would [vouch] for you.

**WARD:&nbsp;** No, no, no, no. You are absolutely right. There's no kind of standardization in the way that there is, has traditionally grown up around HTTP. So, I get it and I think that's a good answer.

**JEFF:&nbsp;** Though, I'm sure Rob Wormald has experimented with it because he's the one who goes and builds observables libraries for everything. So, if you look at the ngrx project there's probably already a repo there for it.

**WARD:&nbsp;** One of the things that I get asked a lot about is what do we do for security in Angular 2. And everybody has their own definition of what that means. Certainly it includes the authentication processes that are part of Firebase. Is there a plan afoot to sort of say, “Why don't you just use Firebase for authentication and then continue on with your HTTP with other things that you've got going?” Is that one of the [plans] that's being considered? Or what's the story?

**JEFF:&nbsp;** I would say that the strategy in general is similar to Angular 1. Like with HTTP we're providing some basic things like the XSRF token that you can save and gets added to requests. And providing some of these low-level things. We haven't gone much higher level than that. But I think what I realized from Google projects and from outside projects is most people are using some other tool that manages authentication or some backend that has a library that does it for you. And so, I haven't heard a lot of need of any higher level abstractions to manage authentication. So, I think the reasonable recommendation is if you're using Firebase auth, yes we use that library and we might have… we have some abstraction for it in AngularFire2. But it doesn't do much other than expose an observable API for it. And then if you're using some other backend, some other service, then it probably provides a library and you should be safe just using that and it should just work.

**CHUCK:&nbsp;** So, what sorts of projects do you foresee people using Angular and Firebase to build?

**DAVID:&nbsp;** Oh man. Where to begin. So, the really cool thing is that a lot of times people think, “Oh, real-time data. So, you're going to build a chat app or a collaborative to-do list app.” And those are all things that you can do but you can take it really far. Like a lot of times people don't… when you start thinking out of the box a little bit you tend to see the amazing things you can do. Like the most innovative project I've ever seen for using the real-time database was at I think it was the Product Hunt hackathon. And this guy made this app where it's a web app actually called Produck Hunt and it was like Duck Hunt but with Product Hunt products. So, it used the Product Hunt API. And then you could shoot these products with your phone except it was a web app.

**CHUCK:&nbsp;** [Laughs]

**DAVID:&nbsp;** So like, how? So, the question was how. And you would hold up your phone to the screen and it would be an actual, you would see the cursor move when your phone moved. But there was no app on the phone. And so, you're like, “Oh, has he got some web Bluetooth? What's going on?” And it wasn't that. And what he actually did was is he loaded up the web app. Actually, he had a web app on his phone and what he was able to do is he held up the, you would calibrate with your mobile device and he would use the gyroscope positioning to know then whenever the phone moved where to move the cursor too. And he used the real-time database to sync that cursor position across multiple devices. So, the phone's gyroscope position was able to speak to the desktop. And the desktop would just render the cursor in a different position. And then when he would tap the trigger button it would then, if the cursor was in the position it would fire and you know, get the little product.

And there's stuff like that I've done to a much lesser extent and much lesser creative. But I created an entire interactive slide deck that used the, we have a library called Firepad that's essentially open source Google Docs. So, all the real-time collaboration that Google Docs give you we have a total open source library that handles that. And it also plugs into CodeMirror and Ace editor. And I use that functionality to be able to live code to people remotely. And then I could hit a couple of hot keys and then I would just mess with the DOM. And so, I would actually turn it to go full screen or I would be able to render the result into an iframe next to it. And this would refresh on everyone's screen on the page. And so, I was controlling what was happening and people are like, “what is this? Are you the NSA? Are you controlling my computer?” And it's not that I was doing anything like that. I was just manipulating the DOM. Every time I would send a command it would just synchronize in the real-time database so it would essentially just do a flag or something like that.

And so, really the possibilities are endless when you know that you have the synchronization control in real-time on all these connected devices.

**CHUCK:&nbsp;** Messing with people. I love it.

**DAVID:&nbsp;** Yeah I know, it's true. [Chuckles] It's really good for that.

**WARD:&nbsp;** Yeah, I think of more quotidian type applications [laughs] myself. The [people] I'm doing aren't shooting at products at the screen but they are tracking the movement of different things, whether it's blood pressure moving or whether it's vehicles moving or people moving, trying to coordinate things. Those are all naturals for the kind of thing that you're doing. So, I guess I'm used to thinking in those terms. And we've never really had an easy technology to do that in. And so, so many of us had done it with polling all these years. And it's nice that you're making it so easy to think about it in a different way.

**DAVID:&nbsp;** Yeah, I know. It's kind of, that was sort of the magic. I've been using Firebase for I guess three years now. And way, way back in the day, I remember when I first used it I was actually, I was a .NET developer. And I was a consultant. So, we would go on site and we would spend the first two weeks, we used to call it sprint zero where we would essentially build the original backend for the app. And we would work so fast on that because the client would never actually see what you're building. You're like, “Do you want to look at my POJOs or my POCOs? Do you want to look at my services?” They don't really care. They want to see something visual and tangible. And so, I started building a backend scaffolder with T4 templates and PowerShell. And so, it essentially would look at your database schema and it would generate a backend for you. And I thought that was just genius. And then the implementation wasn't so genius.

But and then I discovered Firebase and then I realized that I was being like, “Man, I wish my horse was faster.” And then they built a car. And then at that moment I was just hooked. And then I just started building with it. And it took even with my generator it was still really difficult to get up and running. And with Firebase it was like I just included a script file on my web app and I'm already syncing data across clients and within milliseconds.

**CHUCK:&nbsp;** So, one other thing that I can see with some people is that they want to control their own data. So, sending it off to a third-party like Firebase is either something they're not willing to do or given certain regulations it might be a little riskier to do. Is there a way to have this in local storage or have your own version somewhere or have it synced somewhere?

**LUKAS:&nbsp;** So, if I could jump in here. I actually solved this problem using Firebase with HIPAA, or healthcare clients that basically had HIPAA compliance issues. And I actually wrote about it on my blogs. [Inaudible] using Firebase just as an event bus. But what you can do is actually store your data on your HIPAA compliant server and then when the data updates you then update a smaller record on the Firebase side which is generally just a unique ID and a timestamp. And once that's updated then all of your connected clients can say, “Oh, this thing just updated. Let me make a REST call back to my compliant server and get the full object.” And so, it's actually really lightweight and it's worked really well.

So, I've used it in multiple projects where basically the data had [compliance] constraints. And so, you store all your data on basically the client servers and then you use Firebase just for an ID and a date stamp to broadcast those events to all your connected clients. And then have them then update to get the full object.

**CHUCK:** That's slick.

**LUKAS:&nbsp;** I mean, it was totally genius. But the implementation not so much, as David would say.

**DAVID:&nbsp;** [Chuckles] No, it's actually…

**LUKAS:&nbsp;** [Laughs]

**DAVID:&nbsp;** Yeah, that's actually, he's using one of the things, my favorite part about the real-time database is the authentication mechanism behind it is really just JSON Web Tokens. And so, we give you a server secret key. And with this server secret you can then mint JSON Web Tokens. And so, you could login with any backend. As long as you mint a token with this secret that client can login to the real-time database. And then from there you give… this JSON Web Token has a payload that gives you information about what this user is. We have a security model we call security rules that declaratively allow you to say, “Okay, what paths can this use access?” And from there you can actually write these rules that say, “Only let users within this role permission to modify this data or read this data,” and stuff like that. And when you mint your own token you get a ton of power over that because you can actually customize that payload yourself. And so, that's where your own role-based security and all that type of stuff with custom tokens is it's a really great model. And it's great because literally any backend as long as you mint your own token can authenticate with real-time database.

**JEFF:&nbsp;** True story, bro.

[Chuckles]

**CHUCK:&nbsp;** So, what's coming up in Firebase?

**DAVID:&nbsp;** What is coming up?

**CHUCK:** What features are coming out in the future?

**DAVID:&nbsp;** Right. So, I'm not the man with the plan with all the features. But what we are working on right now is that with all this big hurrah we had at I/O we released a ton of new stuff. And we have not caught up completely with it within our big ecosystem of libraries. And so, we have libraries for every JavaScript framework you can really imagine out there. And not all of them are on all the new stuff. And so, we have just finished the AngularFire 1.x integration, so the Angular 1.x integration. That one is now on the new SDK. And where Jeff and I are actually currently working on upgrading AngularFire2 to work with the new SDK. And we are fervently working on getting that done. And then once we have those upgrades in then we want to start making some of the new features work seamlessly with the libraries.

So, specifically the first one would be the Firebase Storage library. And we have some pretty cool ideas of creating directives that pretty much automatically download your images from Firebase Storage as if it was just a regular URL. Because what we do is we provide that similar structure as the real-time database does and we do it through this type of URL called a GS URL which is not a traditional URL. You can't hit it in your browser, do a GET request, and get back the image. Because it goes through your security model. And that's how we represent it. And so, you use this GS URL to download the image using the client. And so, we had this idea, well what if we just create a directive that gets this URL and then from there it downloads it from Firebase Storage and then just renders it, just like a regular image. And then what's great about that is that essentially you don't have to write any code to do it and it still follows the security model in place, the same declarative security model for Firebase Storage.

**CHUCK:&nbsp;** Cool.

**DAVID:&nbsp;** Oh, and one of the things that we're also working on, I demoed this a little bit at ng-conf and we're still working on trying to make this a bit more robust is that we have what we call declarative querying within AngularFire2. And so, AngularFire2 does observable… it synchronizes Firebase data with observables. And so, we synchronize data as two types of collections. Objects, so just a regular JSON object, and then also lists, so an array. And when you want to query this array we have all these query methods within the real-time database. And your queries in the real-time database are real-time. So, if something bumps in and out of the window the query actually adjusts in real-time.

And Jeff actually was the one who had this idea. I didn't like even understand it at first because it was so crazy. But essentially you can specify an observable as a parameter of the query. And so, you're pretty much giving an observable to an observable. But when this observable as the parameter to the query emits a new value we just automatically rerun the query with the new result set. And so, you can actually have a real-time query that reacts to real-time events. And so, this real-time event could be something the user typed something in using Angular 2 forms which is also observable-based. It could be a property within your real-time database. Anything that's an observable you can just plug that into this Firebase list query and it just automatically keeps everything in sync and queried. And it's such a small amount of code for such a powerful feature.

**JEFF:&nbsp;** Yeah, the use cases where I think it really shines are lists, like an [infinite scrolling] list or a grid where you're changing what is getting sorted or what is the sort order. You could represent the sort order or the field that it's being sorted by with an observable. And whenever the user clicks to change that, it would just emit a new value. And Firebase would automatically change the query to get a list based on the new query. Whereas before, you would have to destroy the old Firebase reference, create a new one, manually create the chain of operations to get the query and do a lot of that yourself. Now it's all automatic with observables. And it cleans up after itself, too.

**WARD:&nbsp;** So, this is also, the thing that struck me is a find near me as I move around. We usually think of that in geo terms, so who are the 10 nearest friends of mine kind of thing. And as I move, something has to feed that back in. But actually, near me can be abstracted to say, let's say I'm moving through some products and there's some notion of what's near me as I'm scrolling through some products. What are the related things? And as my context changes in my application, I could imagine myself composing new queries that go off to Firebase that look for things that are relevant to, that are near to in an abstract sense, what it is I'm looking at now. That would be kind of cool.

**JEFF:&nbsp;** Yeah. That's a perfect use case. You could have an observable of the category you're looking at or the exact product and that could be associated with other products in the database and automatically update some widget on the page.

**WARD:&nbsp;** Sounds like a great demo.

**DAVID:&nbsp;** Another thing that we're going to be, we're working on right now is we actually just launched a Firebase YouTube Channel. And with that we are going to essentially every single week we're going to be releasing videos that are all screencast based. And it's just going to be covering a new topic or building an app or do something every week. And right now I'm tasked with doing a lot of the web stuff. And so, once we get these libraries updated my whole goal is to do an entire almost course on building AngularFire2 apps. And so, like setting up an Angular 2 app, integrating AngularFire2 in, and showing the true power of using these two together. And then we're going to be doing that across all platforms, all frameworks and stuff like that. It's going to be, every week it's going to be a new slew of videos.

**WARD:&nbsp;** Holy smokes. I know how much work that is. [Chuckles]

**DAVID:&nbsp;** Yeah. [Chuckles] We have a really, really amazing studio team here at Google. So people, when I release… so this whole series is called Firecasts. And whenever I release a new Firecast someone's like, “Wow. This video is so amazing. I didn't know you were so great at aftereffects.” I'm like, “Yeah no, I don't do that.” [Chuckles] I do all of the coding and then someone else does their witchcraft and wizardry on it.

**CHUCK:&nbsp;** Yeah, we'll definitely need to get a link to that in the show notes.

**DAVID:&nbsp;** Oh yeah, for sure. I'll put that as one of my picks. Spoiler alert.

**CHUCK:&nbsp;** [Chuckles] Alright. Well, speaking of picks let's go ahead and head that direction. Lukas, do you have some picks for us?

**LUKAS:&nbsp;** I do have some picks. So, two years ago when I went to Google I/O I was expecting them to just shower me with gifts of computers and cameras and phones and watches. And what they ended up giving me was a Google Cardboard which is basically a box that you put your phone in and it's 3D. Surprisingly, I really, really, really, really like it. [Inaudible] how [submersive] it was. My kids loved it. Kind of viewfinder 2.0. Well recently my friend showed me, turned me onto this camera. It's called the Ricoh Theta S Digital Camera. They're about 350 bucks. It's about the size of a candy bar. And what you do is you just hold it over your head, you take the picture, and it takes a full 360 shot. So, for instance we're at the beach and he'd just over his head, boom. And you can actually then from there export it and kind of scroll around with it like you were actually there at the beach. So, 350 bucks. I would expect something like this to be much more expensive. It takes great photos.

And then there's this kind of companion site that my friend, [inaudible] his friend built called Kuula.co. So, it's K-U-U-L-A dot C-O. And people have posted a bunch of their 360 VR pics. And they're really, really cool. Super addicting. And so, I'm really excited about VR, 360, these panoramic pics. And I really think it's the future.

**CHUCK:&nbsp;** Alright. Ward, what are your picks?

**WARD:&nbsp;** Quite coincidentally I was looking at the New York Times virtual reality stuff. And I subscribed to it. And this Pluto thing came in and I clicked on it like you know you shouldn't. Probably check the box…

**CHUCK:&nbsp;** [Laughs]

**WARD:&nbsp;** That says I agree to whatever the terms and conditions are without reading it. And I got a Google Cardboard in the mail, too. And what a fun way to learn about Pluto or whatever it is to see it [inaudible] in there. So, I'll give you props for that, bringing that up, Lukas.

But the pick I was going to do relates to my getting lost a lot. And I have something on my phone called Gaia GPS which can download maps and keep track of where I am as I'm getting lost in the woods. And it's a must have phone app and I recommend it to you.

**CHUCK:&nbsp;** Alright. I've got a few picks. The first one's a book. It's called 'Procrastinate on Purpose' by Rory Vaden. I've been really enjoying it. He talk a lot about you only have so much time and here's how people who are successful manage their time. And it goes into more than just “Put the big rocks in first.” In fact, he talks more about prioritization than about getting the big chunks of things that are big chunks of things done. He talks about automation and systems and having people do it for you. And anyway, it's a pretty awesome book. So, I'm going to pick that.

I also just want to shout out here real quick. We're coming up on Newbie Remote Conf. So, if you're a new programmer and you want advice from experienced folks we've got a terrific lineup and you can find that at NewbieRemoteConf.com.

Jeff, what are your picks?

**JEFF:&nbsp;** My favorite thing probably right now, now that the weather's getting nice, are my AfterShokz [open] earphones. They're these Bluetooth earphones that they don't actually go around or on your ear. They just go on your temples and vibrate your bones so you hear sounds. So, you can, I believe these are street-legal on your bike or if you're running they're nice on the street or working out. They're nice because they don't obstruct your ear and you can still hear things around you but also listen to music or talk on the phone. They're pretty cool. Miško actually showed these to me a while ago and I picked them up. And they're one of my favorite gadgets.

**CHUCK:&nbsp;** I've got a pair of those. I'll plus one that. They are pretty nice.

**JEFF:&nbsp;** [Chuckles]

**CHUCK:&nbsp;** You can hear what the kids are fighting over in the backseat.

**JEFF:&nbsp;** [Chuckles]

**CHUCK:&nbsp;** While you're listening to your podcast.

**JEFF:&nbsp;** Exactly. The kids don't know you're ignoring them.

**CHUCK:&nbsp;** [Chuckles] Alright. How about you, David?

**DAVID:** So, I'm going to reiterate the Firebase YouTube Channel. On there we have a whole set of all the Firebase talks from I/O. Like if you want to learn more about the real-time database I did a whole talk on that. And then for every single feature that Firebase now offers we actually have these really crazy animated intros that are all made by these motion graphics designer that do these nice one-minute explanation and this visual flair of how everything works. So, if you're interested I'd check that out.

And then my second pick is in relation to that, is that we at I/O actually had two talks on the Firebase track by the Angular team. So, Rob Wormald and&nbsp; Alex Rickabaugh did the, who work with Jeff, did the Angular Mobile talk and showed a lot of the cool new things with Angular 2 and progressive web apps and some of the Firebase integrations. And then Jules Kremer and Kara Erickson did an Angular 2 overview talk where they did, Kara did this amazing live coding where she shows how to build here Puppy Love app she did at ng-conf. But she integrated it with AngularFire. So, I recommend watching that.

And the last thing I'm going to do in a non-technical realm, and I feel like I'm almost like a noob because I'm just now discovering this. But there's like, long ago there was a book called 'Freakonomics'. And then since there there's the podcast on it. And they had a self-improvement month last month. And someone told me about it and I listened to it. And I'm now hooked. The whole, the last month they had was how to be more productive. And I thought it was going to be like, “Oh sure, you just tell me to do more things,” or something like that. But the actual advice and the actual experts they spoke to in each podcast was just unreal. And the whole way it was set up was super interesting. And I genuinely get sad every time one ends. So, I highly recommend you check out the Freakonomics Podcast and especially the self-improvement month.

**CHUCK:** Yeah, that's a good show. Alright. Well, if people want to keep tabs on what's going on in Firebase land, where do they go?

**DAVID:&nbsp;** Go to the new website, firebase.google.com. We have a whole set of marketing pages that teach you everything it's about. But then we also have tons of documentation. We have a whole docs team, so lots of stuff to learn. We have tons of API references, sample apps, libraries, all there at firebase.google.com.

**JEFF:&nbsp;** And for the AngularFire project, the GitHub project is the best place to look, GitHub.com/angular/angularfire2. And we've got some good guides there, thanks to David East.

**DAVID:&nbsp;** You're too kind.

**CHUCK:&nbsp;** Awesome. We'll go ahead and wrap this one up. Thank you both for coming and we'll catch you all next week.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Do you wanna have conversations with the Adventures in Angular crew and their guests? Do you want to support the show? Now you can. Go to AdventuresInAngular.com/forum and sign up today!]_**


