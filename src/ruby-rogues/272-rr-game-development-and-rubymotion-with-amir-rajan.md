---
layout: layouts/post.njk
title: >
      272 RR Game Development and RubyMotion with Amir Rajan
date: 2016-08-10 07:00:10
episode_number: 272
duration: 59:58
audio_url: https://media.devchat.tv/ruby-rogues/RR272RubyMotion.mp3
podcast: ruby-rogues
tags: 
  - ruby_rogues
  - podcast
---

01:42 - Amir Rajan
- [Twitter](https://twitter.com/amirrajan)
- [GitHub](https://github.com/amirrajan)
- [Blog](http://amirrajan.net/)
- [A Noble Circle](https://itunes.apple.com/us/app/a-noble-circle/id977865620?mt=8&ign-mpt=uo%3D4)
- [Surviving The App Store: How to Make It as an Indie Game Developer by Amir Rajan](https://leanpub.com/survivingtheappstore)
02:24 - [A Dark Room](https://itunes.apple.com/us/app/a-dark-room/id736683061?mt=8) (ADR); Revenue and Downloads
- [Revenue Updates for A Dark Room et al](http://amirrajan.net/app-dev/2015/11/13/adr-revenue-updates/)
09:16 - Quality, Heart and Soul, and Putting Yourself Into a Product
- [iPhreaks Show Episode #161: Successful Indie iOS Game Development with Amir Rajan](https://devchat.tv/iphreaks/161-ips-successful-indie-ios-game-development-with-amir-rajan)
14:31 - Choosing [RubyMotion](http://www.rubymotion.com/)
- [Albacore](https://github.com/derickbailey/Albacore)
- [NeXTSTEP](https://en.wikipedia.org/wiki/NeXTSTEP)
17:43 - [Objective-C](https://en.wikipedia.org/wiki/Objective-C) vs Ruby
- [HipByte/Flow](https://github.com/HipByte/Flow)
21:51 - Cross-platform Availability23:53 - ADR =\> Watch/TV Capability with RubyMotion26:17 - The Ecosystem in iOS and RubyMotion28:11 - Code Structure29:58 - Testing; UI Automation
- [mac\_bacon](https://rubygems.org/gems/mac_bacon) &nbsp;
31:29 - Open Source and Proprietary 33:15 - Other Components
- [UIkit](http://getuikit.com/)
- [SpriteKit](https://developer.apple.com/spritekit/)
- [motion-game](http://www.rubymotion.com/developers/motion-game)
- [Cocos2d-x](http://www.cocos2d-x.org/)
- [CocoaPods](http://cocoapods.org)
34:07 - Going on a Sabbatical40:58 - .NET =\> Ruby
- [Inversion of Control](https://en.wikipedia.org/wiki/Inversion_of_control); (IoC) Container
&nbsp;Picks
- [Transistor](https://www.supergiantgames.com/games/transistor/) (Amir)
- [Hoplite](http://www.magmafortress.com/p/hoplite.html) (Amir)
- [Alto's Adventure](http://altosadventure.com/) (Amir)
- [Shadowrun: Dragonfall](http://store.steampowered.com/app/300550/) (Sam)
- [Minecraft: Story Mode](https://itunes.apple.com/us/app/minecraft-story-mode/id1001286466?mt=8) (David)
- Sriracha and Egg in Ramen (Chuck)
- [Ruby Rogues Facebook Page](https://www.facebook.com/RubyRogues/) (Chuck)


### Transcript

 **DAVID:&nbsp;** Did you see the picture of the New York subway that has put up posters that say, "Hey, Pokémon Go players. We know you want to catch them all. But stay behind the yellow line."

[Laughter]

**DAVID:&nbsp;** And there's a picture of Pikachu on the tracks waving like, "Come on, sucker! It's payback time!"

**_[This episode is sponsored by Hired.com. Every week on Hired they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on Ruby developers providing them with salary and equity upfront. The average Ruby developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with a company or deny them without any continuing obligations. It’s totally free for users. And when you’re hired, they give you a $1,000 signing bonus as a thank you for using them. But if you use the Ruby Rogues link, you’ll get a $2,000 instead. Finally, if you’re not looking for a job but know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept the job. Go sign up at Hired.com/RubyRogues.]_**

**CHUCK:&nbsp;** Hey, everybody and welcome to Episode 272 of the Ruby Rogues Podcast. This week on our panel, we have David Brady.

**DAVID:&nbsp;** Ruby Rouges panelists deny pretty much everything. News at 11.

**CHUCK:&nbsp;** Jessica Kerr.

**JESSICA:&nbsp;** I took a Pokémon gym last night.

**CHUCK:&nbsp;** I don't even know what that means. Sam Livingston-Gray.

**SAM:&nbsp;** I can carry 80 gigs of data in my head.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. And this week, we have a special guest and that is Amir Rajan.

**AMIR:&nbsp;** Hey, how's it going guys and gals?

**CHUCK:&nbsp;** Do you want to give us a brief introduction?

**AMIR:&nbsp;** Yes. Let's see. I'm a game developer. It's great that I can actually say that now. Usually, when I go to talk to people and I say, "Oh, I'm a software engineer," and that's usually when the conversation stops. So now, I can actually say 'game developer' and they keep talking to me. It's great.

So, I'm a game developer. I've been doing it for, I guess, three years now. I made a number one app for the App Store called A Dark Room, and working on two other games now, The Ensign which is the prequel and then A Noble Circle which is a 2D platform and that's based off of the satire by Edwin Abbott and his book Flatland. That's my third game. I guess I'm enjoying what I'm doing right now, being a game developer.

**CHUCK:&nbsp;** I've played A Dark Room and spent a lot of time beating it. I'm curious, and I know that we've had you on some of the shows and we've talked about how that came about. But I think that story's fairly interesting from the standpoint of developers and just going out and doing what you feel like you want to do. Then, from there, we can get into Ruby Motion and game design and all of that stuff.

**AMIR:&nbsp;** Yep.

**CHUCK:&nbsp;** Does that sound like a good way to go?

**AMIR:&nbsp;** Yeah. That sounds awesome and yeah, I think that's a good thing to do. Ruby Motion, I think, the short version of it is that I used it, and it worked really well for me. I actually did the Android port just recently about two weeks ago, also on Ruby Motion so being able to reuse the code base was good.

But as far as the whole story, I actually started off my career as a .Net developer. I was on .Net since 2005. So from 2005 to 2013, I was a .Net developer, and I was like, "Okay, I need to take a sabbatical." I quit my job, ended just bench coding on whatever I wanted. I found A Dark Room, the web version on Hacker News. It went viral on Hacker News, and of course, as a good developer, I right click 'View Source' and I saw the person's name and his name is Michael Townsend. I sent him an email and said, "Hey, I'm on a sabbatical. I'm going to learn iOS development and one of the things on my checklist was to actually build a video game. So let me re-envision your game in the mobile medium, add my own spin to it and all the good stuff. And if it makes money, great, we'll share profits or whatever."

And he said, "Yeah, that's fine."

So then I spent some time doing an Objective-C, using XCode and that was really frustrating. So then, I got off of that and found Ruby Motion, got back into VIM and all that wonderful goodness [inaudible] Rake and everything. I built the game out in about four months, pushed it into the App Store, did nothing for five months. You sent out a tweet saying, "Oh, it's there. It's available for everyone to download," and like the first day, we got like 30 downloads. So it's pretty abysmal.

Then, out of nowhere, it goes viral in the UK. Then, it goes viral in the US and stays up in number one spot for like 20 days. It's ridiculous. It was just madness at that point. During that first year, we were in the top 10 in like 70 countries. Then, we were top 100 in all of the countries. At the end of 2014, Apple actually recognized us as one of the top 10 paid games of 2014 which was really good.

**CHUCK:&nbsp;** It's awesome.

**AMIR:&nbsp;** Yeah, it's really awesome, and the great thing is it's a text based RPG. You don't expect a text based RPG, that's premium with no ads, no in-app purchase to actually make any kind of splash in the upstream but it did. You know, I'm just transitioning from doing C# corporate development, just the general nine to five job, cubical work to just being on your own and that whole thing, there's a lot to be said there, I guess. But that's the short version, I guess.

**DAVID:&nbsp;** I had a coworker who worked at acclaim entertainment and he worked on the port of Mortal Kombat 2 from the arcade stand up console to the PlayStation, and it went PlayStation Gold which means it sold more than 30 million copies and he was on the dev team and the developers got to share like 1% royalty but that was amongst all thirty developers so the team lead each got like 0.1, but the time it got down to him, it was like 0.05 or 0.005 of a percent of the royalty. Then, he just looked at me and grinned and he said, "Thirty million times anything is a nice number." It paid for his house.

**AMIR:&nbsp;** So from a revenue standpoint, it was actually a bitter sweet. I have all this on my blog so you can actually read detail revenue numbers but I'm really transparent with all of that stuff. When we hit the number one spot, we're getting 20,000 downloads a day so that was insane. But then, Apple takes 30% cut right off the bat. Then, we do a 50-50 split on royalty and so, it turns out, if you're self-employed, you pay 15% self-employment tax and then, given the tax bracket I was in, I was in the 30% or whatever. So overall, I was paying 43% taxes long on net revenue.

We had $800,000 in revenue for that first year, and I walked away with about $260,000 for that year. It was a 14-month journey so if you like do the math and try to actualize them, I was at about a bill rate of about $111 an hour. If you can land a job that gives you a bill rate of $111 an hour, you're pretty much making what a number one app would make in the Apps Store.

**DAVID:&nbsp;** Thank you for sharing up, by the way. I decided to share the story about a claim because I didn't know if you wanted to just be transparent about your revenue shares and that sort of thing. I was going to give you an easy out there. Thank you for sharing that. I really appreciate that.

**AMIR:&nbsp;** No, no, any revenue information you want, I'm more than happy to share. No problems there.

**DAVID:&nbsp;** That's awesome. The thing is that I work at a claim with this coworker. I worked there for a year and a half. I destroyed my health. I destroyed my sanity. I did not destroy my marriage because I quite my effing job. Basically, I walked and told my manager, "Look, I took this job to support my family. Not the other way around," and tendered my resignation. But it took me 18 months and literally not being able to know what day of the week it was anymore because if it was ended in a 'Y', I had to go to work for twelve hours.

I didn't make a single penny in revenue in royalties. You had a number one game in the App Store. In other words, you made $111 an hour by winning the lottery.

**AMIR:&nbsp;** Yeah, and that's what I try to tell people, there's a part of it that's winning the lottery and that's getting viral and making to the number one spot. I've done a lot of data mining stuff to try to figure out exactly what happened there, and it's still a complete crapshoot on what connections I made with publishers or get that working.

Now, when we hit the number one spot, the quality is [inaudible]. So it's really easy to make that number one drop off, but to stay there for 18 days, that was crazy. The funny part was that on our one year anniversary, I actually made the game free and it started climbing the free apps. So first day, we had like 30,000 downloads which is actually par for the course. So you get like 10X the number of downloads for a free app as you do for a paid-up.

Second day, we're at 60,000. For the number one game, you know, it's fine. But then, the third day, I was tracking the app and we passed Candy Crush in the free Apps Store. Oh, man, that was- I took a screenshot and I was like, "Screw you Candy Crush." Eventually, after seven days, we had a million free downloads and we were the number three app overall. The only two apps are ahead of us was the Facebook Messing App which apparently everyone had it install, and then Crazy Taxi by Sega which was the Editor's Choice for that week. It was crazy.

Then, we went back to paid and just took the flag and everyone's like, "Where to go? Where does game go?" And it's like, "We're back in the paid section." We conquered both App Stores.

**CHUCK:&nbsp;** You said that you have to have the quality in order to keep your spot at number one, and if you've played A Dark Room, it's pretty minimalist. So quality isn't necessarily like graphics or anything, right? So what do you mean by that?

**AMIR:&nbsp;** A couple of things I think, attributed to the success for A Dark Room, one of them was that we were just so different from every other app out there. So you get the rigmarole, this is some kind of grid matching game or this got the cartoon-y graphics or the yelling icon for the [inaudible] thing, right? You see the face is, "Arrgh!" A lot of those apps is doing that. So I think, having that contrast really made us shine. The fact that we didn't have anything, made us shine from that perspective.

The other thing with quality was that, I know you guys and gals can related to this, you can almost up in my heart and soul in today's game and I strongly believe that when someone does that and you work with something or you actually use something that someone really put their effort into, it shows through. It's hard to objectively put like a thumb or a finger on, what that really is.

I think, another thing was that, I remember the first day when I started working on the game. I was burning the midnight oil. I didn't know I lost track of time. Next thing I know, it's like 4 AM and I'm still coding. It was just a fun thing. But you see that quality show through. I think, another thing that helped A Dark Room stay there was that, I actually put developer commentary at the end of game so you actually get some background of who I am as a developer, who Michael is as a developer and how we built the game. So you get that personal connection. I think, that really, really helped with what are my recommendation too.

The way you think about that idea of like putting yourself into products is that something that you've noticed also or --

**CHUCK:&nbsp;** I think, it gives a better chance of success. I know people have pour their heart and soul into something that will just wasn't going to work. But, you know, I think if you have something that can succeed, I think... I don't know, I'm not sure exactly how to say it, but I think --

**AMIR:&nbsp;** It's okay, just --

**CHUCK:&nbsp;** No, what I'm saying is I think, in those cases, they can see the attention to detail, they can see the passion you have for it, they can see the level of commitment that you have to it, and they connect better with it that way.

**JESSICA:&nbsp;** There's a big difference between meeting requirements and making a beautiful piece of software.

**AMIR:&nbsp;** There was an aspect of that shows. At least, we really show that there's something happening.

**CHUCK:&nbsp;** There's a series of games called Lifeline where- and they make you crazy, actually because they're on a time delay. You're supposed to be interacting with somebody who's in real time, going to die because you're going to give them bad advice, and then you get to restart, and do it all over again.

**SAM:&nbsp;** Sounds great.

**CHUCK:&nbsp;** Yeah, it's fantastic. But the time you get to the end of it, then the developers, they tell you who they are and what they're doing. Crashlands is kind of the same way. The developers are very transparent about who they are and what they're doing. Those two game shops have done something that you don't see from the AAA game shop site like EA Sports and- I'd say, acclaim, but they're bankrupt. Haw-haw! Wouldn't happen to a nicer company.

[Laughter]

**CHUCK:&nbsp;** Yeah, Ubisoft or Bungee or something. But you see a title from those games, you know immediately, AAA game, it's going to have high production value. Might not be any fun to play, but it's going to have very high production value. But for the small indie shops, when you get this transparency, the people who made Crashlands have made like five other games, and Crashlands was a lot of fun but I had no interest in going to the App Store and searching for that developer.

Until I started watching the videos of them talking about the things that they were doing and how they were doing it and how the two brothers, and one brother was at the hospital. They've got this whole story and all of a sudden, I'm really interested in why they're developing, why they're doing what they're doing, and now, I'm interested in their other games.

So you putting your stuff at the end of your game, saying, this is about me, this is about Michael Townsend. This makes me want to go look at other things Michael Townsend has done for the web. It makes me want to go look at other things you have done in mobile space. Like you said, you get two more games coming out, and I have no idea how much benefit you will get in this iteration of putting yourself into the game for people to see you and be transparent. But I strongly suspect, I have no... I mean, the plural of Dave's anecdotes is absolutely not the data but my suspicion is that people will be much warmer towards your follow up games when they go, "Oh, it's that guy! It's that same guy."

**AMIR:&nbsp;** Right, and when the app is released, it became the number six app overall. So it was a shorter period of time but it was immediately featured by Apple on their many features and what not. It tracks about, I'll say 33% revenue of ADR because you have the people that download the game and don't finish it but I'm pretty sure that people have finished the Dark Room. I now present almost a quasi-interstitial saying that, "Hey, the prequel is available." I'm pretty sure that people go ahead and follow up and download the Ensign also.

**CHUCK:&nbsp;** I did.

**AMIR:&nbsp;** Yep. So it's one of those things where there's definite sticking us once you get that first wind.

**CHUCK:&nbsp;** So what made you choose Ruby Motion? I mean, if you're going to go build an iOS app, it seems like the conventional wisdom is to go pick up. At the time, it would have an Objective-C.

**AMIR:&nbsp;** I actually thought about this because I knew this question is going to come. I really reflected on this a lot, especially, coming from my background. So a couple of things. Visual Studio, as much as people rag on Microsoft, Visual Studio is freaking awesome. As far as the idea is concerned. It's not them or Emacs but it's pretty good for a code editor.

When I went to XCode, I actually started building A Dark Room in XCode and Objective-C. So I went to XCode and just the experience of XCode as an IDE just wasn't fun. I had the Vim bindings of the points that I used. An XCode Vim is on but it's just still wasn't that great. JetBrains does a much better job. JetBrains does ReSharper so they have something called AppCode and that was okay but it just felt too much like what I was trying to get away from, for my corporate environment.

Then, that's when I looked at Ruby Motion. The funny thing was that I got introduced to Ruby doing build automation for .Net projects. There was a [inaudible] Albacore, back in the days. It's made by Derick Bailey, and you build .Net projects using Albacore and we had Jenkins integration at that point. I never got actually introduced to Rails. It was strictly movie reviews kind of mentality, and that's when I did all that good stuff. I did all these build automations and I said, "Man, Ruby is just so fun language to be in. Being Vim and just use rib and the REPL, all that was felt just right. Then, when I saw Ruby Motion, I was like, "Okay, well, I get to use Rake. I get to use whatever header I want. The REPL integration is good for iOS simulator. I can publish my app without using my mouse. All of this stuff is exactly where I want to be with the development.

Then, once you actually start building the application, the second part that I found was really important was the cultural aspect of it. I hate to say but there's almost an implicit culture that comes with choosing a language. You know, it's a tough statement to make but when someone says, I may- kind of say PHP, PHP is "Argh!"

[Laughter]

**AMIR:&nbsp;** Man, can you believe that?

[Laughter]

**CHUCK:&nbsp;** PHP is not a four letter word.

**JESSICA:&nbsp;** Guys, guys, guys! We're family friendly.

**AMIR:&nbsp;** I'm a PHP 1.0 developer or a FoxPro developer. That implicitly has some alter associating with it. Good or bad, right? You have years that almost say that you're there, has to develop and I think, okay, he's out on [inaudible]. So there was an implicit culture that I knew I was walking into by choosing Ruby Motion and that was exactly what I found when I did that.

That's what I was worried about when using Objective C was that going to Objective C, I get a lot of the NS. API is the old... what does that stand for? I already forgot --

**CHUCK:&nbsp;** NeXTSTEP.

**AMIR:&nbsp;** NeXTSTEP, yeah. So you get a lot of arcane NeXTSTEP APIs: RestKit, AFNetworking. At least some of the previous versions had that arcane feel to them and Ruby Motion had a lot of the wrappers for the UI kits stuff that just made it to feel like Ruby. So there's my long winded, very well-thought out response.

[Laughter]

**CHUCK:&nbsp;** So one of the things I hear about Ruby Motion is that you write stuff that looks a lot like Objective C except it's Ruby, and you kind of said the other way around, really, you're using the frameworks but it looks like Ruby. So is it both or can it be both?

**AMIR:&nbsp;** Yes. It's both. The short version is both. The idea there is that, there's a HipByte which is the company that built Ruby Motion. They have a frame that they call Flow. Flow basically is, instead of using auto-layout or Androids widgets, they have almost the Flexbox style view rendering engine. So the idea there is that you can go on that higher level and do some of the Boilerplate stuff and productivity things at that level. But if you need a deep down into the NeXTSTEP APIs, you know that option also.

It's that aspect of, I've got the power Ruby when [inaudible] first came out, there weren't a lot of libraries so you basically have to write Objective C but then you saw commonalities and I'm doing button quick event this way where I'm passing this delicate. Well, now I'm going to create an implicit block of the yields, and going in and mixin, and suddenly, [inaudible] is a lot simpler.

So you start building your own DCells and you start building out more idiomatic Ruby APIs. That work when I originally started. There was some groundwork there but I had to work through a lot of these things. Then, when it comes to ask, what if the framer doesn't want to support it, then you go into the actual, "Okay, well, I can just use the Objective C libraries."

It works CocoaPods also so I had it accessible. In terms of the game, it actually playable by blind people. There is a voice over capabilities. There were no Ruby gems available for that so I just pulled in a CocoaPod and because it's Objective C, I just use that Objective C API through Ruby, and it is ugly.

When you look at the APIs, it's NeXTSTEP APIs and you'll find yourself extending NSObject and say, "Okay, well, I want UI labels to have this function in there," and you just extend it and you mix it in, open the [inaudible]/ You don't want to do when you have those options, those newer, better APIs readily available. It's nice being able to do that.

**CHUCK:&nbsp;** We've had a show or two where we've just gripe about Ruby. One of the places where Ruby really kind of falls down is in graphics and rendering and windowing and that sort of thing. Then, the answer from the Ruby community, as well, Ruby is just isn't designed for that and my response to that is Ruby so freaking awesome that it should be for everything, anywhere, ever --

**AMIR:&nbsp;** Of course.

**SAM:&nbsp;** That's like, "Doctor, my arm hurts when I do this." Well, don't do that.

**CHUCK:&nbsp;** Well, don't do that. Yeah, exactly. But I had to generate a whole bunch of graphics for a website and there are lots of tools that would've made it very, very easy. But by golly, I wanted to do it in Ruby and literally the only easy way to do it - this was in 2007 so there were even fewer tools back then. The one tool that I really had, that I knew how to use was Java 2D Canvas and JRuby was out and stable and so --

**AMIR:&nbsp;** Like I got to use JRuby.

**CHUCK:&nbsp;** Yeah, I really don't want to try and handcraft the bits in a bitmap, buffer, and then figure out how to pack it using the Pac-Man. I was going to use the Java 2D Canvas and just save the thing off as PNG file. Yeah, that code looks like Java. Looks really, really ugly. But the stuff around it is pretty. Once you get two steps away from it, you're back to Ruby again and it's nice.

**AMIR:&nbsp;** That's why I brought up the cultural aspect because is that, yes, I can choose Objective C and then you're right, I don't have Ruby code that looks like Objective C. But there are other human nuances to picking a specific stack or framework and that's one of the things. It's the same thing that, "Well, why don't I do it in Lua? Why don't I do it in Xamarin? Or Phonegap?" It's the same kind of things that you have to evaluate.

At that point in time, the Ruby community just approached the idiomatic Ruby. Ruby really resonated with me and that's why I continue to do Ruby Motion. I think, why people like Ruby as a language, too.

**SAM:&nbsp;** That's interesting. I guess, earlier you've answered one of my questions because I was going to be, whether you had published to the Android App Store as well, but obviously, if you're talking about extending stuff in Objective C, you didn't do that. I'm curious though --

**AMIR:&nbsp;** Until two weeks ago. I didn't do it --

**SAM:&nbsp;** Really? Interesting, okay.

**AMIR:&nbsp;** Yeah. A Dark Room is on iOS and Android now.

[Cross-talk]

**CHUCK:&nbsp;** -- Both were written in Ruby Motion, correct?

**AMIR:&nbsp;** Correct.

**SAM:&nbsp;** Okay, well so, that obviously wasn't one of the deciding factors for you, though, when you chose Ruby Motion which is funny because like when you look at the site, that's their tag line, that you can publish to different platforms.

**AMIR:&nbsp;** In 2013, they didn't have the option. It was strictly iOS. The funny thing was that I had a Windows phone until 2013. I was a hardcore --

**CHUCK:&nbsp;** It is hardcore .Net.

**AMIR:&nbsp;** Yes, I have the --

**CHUCK:&nbsp;** You told all your friends, "It's not that bad! It's actually got a pretty great interface!"

**AMIR:&nbsp;** Yeah, it was a really good interface and I've actually built an app. I actually build Windows phones, I built a budgeting app that are actually deployed to the Windows Store and everything. It was XAML Visual Studios. The tipping point was my CPA contacted me and said, "Well, we need to do your taxes," and I had to get my Scottrade PDF coming out. I didn't send a PDF from Scottrade.

There's an option of how do I email this PDF, and I try to email, and email is the link. It doesn't download the PDF and create an attachment. It sends over the link and I was like, "I'm not going to give her my Scottrade password. It's ridiculous," and at that point though, that was the last straw, like screw this. I'm going to the Apple App Store. I'm going to get an iPhone.

When it came to Ruby Motion, I didn't have an Android device so at that point, I was just going to push iOS and see what happens there. That's pretty much my reason for not choosing [inaudible]. I have no idea this will even succeed and makes it at number one spot.

**CHUCK:&nbsp;** So A Dark Room got a very clean, very simple interface, right? I mean, it's a text adventure game where you have buttons to choose. It's almost like 'Choose Your Own Adventure', right?

**AMIR:&nbsp;** Yeah.

**CHUCK:&nbsp;** I realize the market is still very, very, very small. Do you have any plans to port to the Apple Watch or to the Linux Pebble? If so, will Ruby Motion even do that?

**AMIR:&nbsp;** Ruby Motion does do Apple Watch. It does TV, too so it does Apple TV also. The tricky part there is- here's the secret with it. There's not a lot of TV apps so the monetary value for doing the port to those devices, isn't there. Except, that if your app does support those devices, suddenly Apple cares and then they might feature you.

So you have an iOS app, you have an iPhone app that also supports watch and TV, they're more inclined to feature your apps on the iPhone because you built a watch app and a TV app.

**DAVID:&nbsp;** Lifeline is like that. I'm confident that their Apple Watch integration is entirely just there as like a loss leader. It's a 'Hey, Apple please pay attention to us.'

**AMIR:&nbsp;** If feature is substantial, if you get the first position- So there's a banner feature at the top. You're guaranteed millionaire. You will get easily 700,000 downloads that week, if you can do that. If you get the best new apps or like apps replaying today, if you get the first position feature there, you can see a 7X in revenue. It's crazy. It's amazing.

So yeah, it can be a very good loss leader. From my perspective, pushing A Dark Room, I have an Apple Watch. It's okay. It gives me notifications but I don't see that as being a good medium for that. Then, my other game which is A Noble Circle, it's a 3D platform, it's a portrait game so if I push that to TV OS, I have to make it landscape. So that's a tricky part there.

With regards to just do a meaningful work or doing craftsmanship, I feel weird putting a product out there that isn't perfect so for now, no Apple Watch or TV. But if you can support it, there's a good chance that will get you a feature.

**CHUCK:&nbsp;** So I'm curious, as you work on The Ensign and The Noble Circle, you know, the ecosystem around iOS has changed quite a bit over the last few years. How does that affect what you're doing with Ruby Motion?

**AMIR:&nbsp;** Short answers is it doesn't. The Ruby Motion works- and you're going to see the chinks in my armor with [inaudible] and compilers and runtime. But basically, there's two parts to Ruby Motion. There's the compiler and then, there's the Ruby Motion runtime. The compiler, it basically uses the LVM tool chain to take your Ruby code, it parses that and pretty much directly maps it to Objective C.

So if you think about a new APS that are available, they're pretty much available in Ruby Motion because the language- you can basically go from surrounding brackets to parenthesis, and it's almost a mechanical change to Ruby Motion. That part is just for free. You get that. Now, the 'gotcha' is that there's the Ruby Motion runtime. The runtime adds the additional features that Objective C doesn't have like the mixins, [inaudible], method missing, class initialize, all those things.

Those aspects are in the runtime so it's kind of the opposite. When you have a new Ruby feature come out, that's when Ruby Motion has to 'catch-up' and maintain parity with Objective C and Android. But as far as the new Objective C APIs, it's basically, a recompiler against the new Objective C runtime and you get those things. You still have to- I guess, this is the mothership where you still a download XCode and you still have to download all the XCore developer tools but you don't open up XCode after that.

It's the same thing for Android. You get the same APIs. You basically mentally translate like JRuby. If you convert Java to Ruby, you get those APIs but then you get the additional features of all the Ruby stuff they get on top of that.

**CHUCK:&nbsp;** Do you structure your code in the same way that you structure regular iOS apps? Do you have view controllers and [inaudible] and all of that stuff? You have the nice Ruby syntax and whatever else Ruby Motion gives you, right?

**AMIR:&nbsp;** Yes. It was actually pretty interesting. You still have your app view controllers and all of that good stuff. When I started on A Dark Room, I only have the iPhone 4S so the 5 wasn't out. Definitely, the 6 and 6 Plus, I know that those things were out. Auto-layout wasn't out either. So this is like a Legacy Code base. It's 25,000 lines of Legacy Ruby Motion codes. It's crazy.

But basically, it got to the point where I would say, "Well, now, we need to support iPad, how do I go about doing that?" So what I did was I would have an iPad view controller and the phone view controller but then I would use a mixin for all of my common code. So all of my common interactions like creating a button or flashing this button in or throwing up an alert. Basically, those protocols and interface 'methods' using the term interfaces loosely, those are going to mixin and then, it was just a matter of using that mixin with the concrete view that I want to use.

So you use all the defaults stuff and then, you can use your mixins on top of that. So HipBytes, their Flow framework, what they're trying to do is create a consolidated view for both Android and iOS so you get a native controls, native view concepts for both devices but using a common suite of views and things like this. So they abstract out the idea of whether you use an activity or fragment or view controller or navigation controller. It kind of consolidate all these stuff.

That's interesting to see how that comes along. I was unable to take advantage of that because I was dealing with the Legacy Code base and all that stuff.

**CHUCK:&nbsp;** Now, one more question about this. Then, I think, we should go back into your story because I think that's very interesting. I find the idea of writing apps for mobile in things like Ruby and JavaScript just really interesting. So the other question I have is how do you test? Do you just use our spec or do you have something else that you used to test on Ruby Motion?

**AMIR:&nbsp;** It's got the best name - MacBacon.

[Laughter]

**AMIR:&nbsp;** It's an our spec dialect so it's got some assertion support and my ADR code base is actually has, I think, 2000, 3000 lines of test so I actually test the engine very heavily. It's called MacBacon. It looks like our spec. You get some really low level assertions that is like [inaudible]. It's got the old Fluent Assertion approached. Our spec is not the expect assertion. The new our spec expect this assertion stuff. But you just basically use that and there's a Rake spec in there that lets you run the specs on the device and then your emulator.

As far as you do automation, you can actually do your automation in both Android and Ruby Motion. The tricky part for me is that when you start getting into this part of the game, it's actually NP complete, I think. It's not a solvable algorithms so I couldn't automate the UI once you bought the compass. You know what I'm talking about there? But I couldn't automate the UI there. There was a lot of manual testing from that standpoint. You're getting click buttons and do all that stuff through the test suites. It's pretty cool.

**CHUCK:&nbsp;** A Dark Room is open source so people can go and look at all of this, right?

**AMIR:&nbsp;** The web version is open source. Michael gave me a proprietary license for the iOS script. Just going into kind of dipping us into this some [inaudible] stuff. When we hit the number one spot, we had to do with clones. You see the ugly side of open source at that point because people would just wrap the game in a webview, put ads in it and then, put it out there and then just generate revenue from the Android version. Or people would use A Dark Room dash Free for the iOS version, and then people will download the free thing and then, I would get an email saying that, "Hey, your game doesn't save. It's riddled with ads. It sucks!"

When you hit the number one spot in a week's time, you don't have time to go through a one year trademark. We are a registered trademark now, but you just don't see that kind of thing happening. Then, the systems that, be like the government systems and stuff, they don't support that kind of set up so we would do takedown notices and they're like, "Well, you have a common law trademark and that's fine, and that will only get you so far," so iOS, they honor that. But Android, because I didn't have A Dark Room on Android, they said, "Sorry, we can't do anything. You don't have common law trademark here." Or, they'll say, we need the trademark number and we don't have that.

It's bittersweet, you know? It was open source so I was able create a derivative work that benefited the original author and myself. But then, there were other apps out there that didn't do that, which is sad to see, and there are derivative works out there that did do that. They were open source based on that, but I was given a private license from Michael.

We learned our lessons and Michael release a new game called Gridland. It's a web based game and it's proprietary also. It's not open source. No engine either. The Ensign is proprietary and A Noble Circle is proprietary also. It sucks but I guess, that's how the chips fell.

**CHUCK:&nbsp;** Is there anything else to the stack other the Ruby Motion that you want to talk about. Are you using Core Data or anything like that on the back-end?

**AMIR:&nbsp;** There's no service side component. It's all Ruby Motion. The funny thing is that, A Dark Room, being a text-based game, it's all UIkit so that part's really, really fun because I made a game- I would get emails from recruiters and they're, "Hey, we saw you have a number one app. We would love to hire you."

And I was like, "Have you seen the app? It's buttons, progress bars, labels. I think, you might be looking for someone that knows how to actually design a UI." But yeah, it's all UIkit. A Noble Circle is using SpriteKit. I'm considering moving that over to something called motion-game which is a bridge on a C++ library called Cocos2d-x. It's just Ruby Motion and straight iOS, and that one CocoaPod library for the voice over stuff and that's it.

**CHUCK:&nbsp;** So how do you go on a sabbatical? If I need a sabbatical real bad, what do I do?

**SAM:&nbsp;** Asking for a friend.

**AMIR:&nbsp;** You go to college. You graduate without [inaudible] at all. You stay gainfully employed and live off of ramen for seven years. Then, you'll have enough money to go on a sabbatical when you're tired of corporate development. Does that work?

[Laughter]

**CHUCK:&nbsp;** I like ramen, so yes.

**AMIR:&nbsp;** You know, it's awesome! Ramen and Hot Pockets. That's another thing with I guess, the success stories that you hear about these overnight success stories. But this is literally like ten, fifteen years in the making. So you go to college, and then through college I did two jobs, graduated without having your dad, didn’t buy the fancy car coming out of it and just kind of maintained that low level lifestyle and save up as much income as I could to where I could take that risk.

Now, I know that some people are not in a situation where you can actually do that. Some tips when you're going on sabbatical. Definitely plan ahead. I think, I wasted the first six weeks of my sabbatical doing things that I should have done like handling insurance, handling the transition for medical. What do I do with my 401k and Roth? Where do I go for my co-work space? With my new schedule, I'm going to look like- now that I don't have to worry about that it's a Monday or not. So all of those things, I wasted six weeks just to get in that habit.

Another thing is that, getting into a new habit takes some time also. I would say, it took me about three months just to feel like I was being productive in this new environment. If you're only going to take a three-month sabbatical, I don't think that's enough time for you to really, really benefit from that. Especially, if you don't spend the time beforehand doing that stuff.

Actually, when I went out to sabbatical, my wife and I pared down to one bedroom apartment. We're in a two-bedroom apartment and I sold everything I owned. I basically had a desk, my clothes, my laptop and my car. It was really tough. I had game systems - PS2, PS3. All of those things and I just completely sold it off, and it was this idea of, "Okay, I want to focus on really learning and building myself, as just personal growth."

So, pared down, really focus on what you want to get out of that sabbatical then, do it, I guess. We went to the one bedroom apartment. I promise that her standard of living wouldn't suffer for me taking this sabbatical. I just kind of a load off my life savings at that point and my [inaudible] was, "Okay, I can do this for a year. I'm going to put 50K on the table. Do this for a year. If I run out of 50K, I just go back and find a job again. So that's kind of what I did.

If you're going to take a sabbatical, plan ahead and try to add at least to six months if you can and cut down your expenses, cut down all the things that you don't care about so you can really focus on what you do. So I have stuff now after three years. I put a good dump payment on the house. I have paid off house now which I'm really happy about. I actually have a room --

**CHUCK:&nbsp;** A dark room?

**AMIR:&nbsp;** A dark room, yes. So I have a room and I have stuff now and it's good. One nice thing with actually going on sabbatical was that once you've done the minimalist lifestyle, you find that your attachment to stuff, kind of goes away. Like something breaks you'll say, "Okay, whatever. It broke." No skin off my back, right? Just getting rid of that upkeep. It was really cool to go through that 'dress to change' and then come back and have new perspectives on everything.

Same thing with languages. I felt there was a strong correlation there with going from one language to another, and then looking at other platforms and stacks and feeling the pains of XCode, knowing the benefits of it. Knowing the balance of the Visual Studio then, Emacs and just being able to speak and empathize with those lifestyles, I guess, and cultures. So just save a lot of money. That's how you'll got to.

**SAM:&nbsp;** I think, it says something about programmers that when you took a sabbatical to get away from, and years in .Net development and programming, you spent a couple of months programming. I think that's something that maybe many of us on this call would do and I certainly would. But did you take any time like was there a week or two of like just pure brain rotting vacation in there?

**AMIR:&nbsp;** Yeah, quite a few weeks. I did do some travel. Again, luckily for the success of A Dark Room but a couple things that change was my how much I work per day. So I didn't do a full eight hour day. Even today, I do that. I work about five to six hours but I work every day. Another thing that was really interesting was going to sleep and waking up. I go to sleep when I'm tired and I wake up when I'm not so not having an alarm clock and all those things was really interesting. I guess, that was kind of a break.

Another thing I did was look after my health so I have an actual workout schedule and I have a regimen to work against and just not worry so much about a deadline or a specific task because again, that was another thing with motivations with sabbatical was that I wanted to just disconnect from those deadlines and aspects.

Another thing, I think is important to touch on is that if you're building a product, I know there's developers out there, "I want to build a product, part time." Decide: are you building a product or you're trying to learn something? Because I see too many times that say, "Oh, I want to build this X, Y, Z in this new tech, new platform, new environment and I'm going to kill two birds with one stone and do both things." It doesn't work.

So if you want to monetize in building that, I would have approach it much differently that much differently than what I do. I may have just wrapped it in a web view and just clean it up, and try to put it out there for some quick cash. So it was relaxing, and I guess I'm taking a week off now so I have a big release for A Noble Circle and I was going to take some week out and binge on League of Legends or something. Definitely, a more consistent, slower paced lifestyle.

Another thing that's probably worth with mentioning is that when you talk to people about going on sabbatical or taking some time off, eventually, you get tired of just chilling on the beach, drinking Mai Tais and all that stuff. It does get boring. You start to really think about what does really mean. What is meaningful to you when you actually want to do with ‘life’? It's an interesting position to be in and to really be able to reflect on that and think on that.

**SAM:&nbsp;** Yeah, I found that my limit for that on vacation is about three days.

**AMIR:&nbsp;** Yeah. Then I go start crazy and I've got to do something. I've got to [inaudible] or something.

**CHUCK:&nbsp;** Anything else we should talk about before we get to Picks? If people want to buy your games, where do they go?

**AMIR:&nbsp;** You can just go to iTunes and search for A Dark Room. It'll be the first hit. The same thing with Android. I'm going to be the first hit there. Yeah, I think that's primary it. I guess, I was kind of surprised that there was maybe more talk about my transition from .Net to Ruby.

**SAM:&nbsp;** Oh, yeah. I mean, I went through a similar transition. I started out as an Access developer. I actually left the Microsoft world, went right when .Net came out.

**DAVID:&nbsp;** Here's one that happened to me when I moved from C++ and PHP and Python to Ruby. I know, I know. I said the 'P' word. Sorry.

[Laughter]

[Cross-talk]

**DAVID:&nbsp;** Yeah. When you came to Ruby, did you find yourself dragging along of .Net baggage mentally with you and writing .Net programs in Ruby? How did you get to where you were speaking Ruby fluently and idiomatically?

**AMIR:&nbsp;** This is actually hilarious when it happened. I had a really, really difficult time with the static versus dynamic typing so C# actually has a dynamic language runtime. I was going through this transition to Ruby, actually brought dynamic capabilities into C# and creating method missing and mixins and prototypical stuff to where it actually helped me out because I would get a JSON payload from an HTTP request. Instead of having, I guess, an actual model with actual excesses and setters and getters, it would create an almost like a property bag that would gain some validation capabilities and it was almost more like a jQuery, JavaScript mangled mess. But it was lots of thought --

**SAM:&nbsp;** But it was your mess.

**AMIR:&nbsp;** It was my mess and it turned out to be really helpful because we had architectural issues, things where we had to replicate objects across tiers so instead of having these other process, Coco Object here, plain old Ruby object here all the way across. We're able to leverage that dynamic capability. But when I went to Ruby, I actually said, "Where's the IoC container?"

For those that haven't done a .Net or Java or static type languages. IoC container is basically a means for redefining [inaudible] because you can't redefine [inaudible] in at least C# or Java. Basically, this quasi-factories that would inject a construction with some rules about how to do select time management. Is that static? Is it a single instance for the entire application? Is it a single instance for the thread? It's the nuance since every time, etcetera, etcetera?

Because you can't redefine [inaudible], you have IoC containers that provide a capability for you. So when I'm going to Ruby, I'll say, "Well, where's the IoC container." I didn't understand the concept that you can redefine [inaudible]. You can actually do kernel methods, create objects and classes and everything and do factory resolution that way. So I spent some time trying to create an IoC container because I felt like, the Ruby will definitely needs this stuff.

[Laughter]

**CHUCK:&nbsp;** Definitely.

**SAM:&nbsp;** Meanwhile, the rest of us are --

**AMIR:&nbsp;** Yeah, I know it's like, "What the hell are you doing?"

**DAVID:&nbsp;** No, I just remembering the the valley and cavalry charges that were made in 2007, 2009. It comes about every two to three years where somebody says, "We need inversion of control."

**AMIR:&nbsp;** And so, the thing is like, dependency inversion is still something you can do. It's just very different and your IoC containers, you don't need that because you're using Ruby. You don't need it.

**DAVID:&nbsp;** You get it so implicitly and fluently for free that you can still use dependency injection and inversion of control in Ruby. There's just no ceremony around it.

**SAM:&nbsp;** I didn't even realize that that's what you're feeling.

**AMIR:&nbsp;** So that was a learning experience for me. But some of that baggage did come over. You know, the other aspect is that there's one little essence that I love is going from a local variable to just a bare method to module to a class, that transition. Just because you know how to put parenthesis right around your method names, it's such an elegant transition that... I don't know, it was wonderful discovering that.

**DAVID:&nbsp;** Thank you. I'm working with developers all the time who will insist on putting parenthesis on their method calls and keeping the 'at' sign in front of their instance variables because obviously making a method call when you could just be accessing this dot variable or at variable. That's much slower and we want to use the at variable to make it clear that we're accessing a local variable and like, no, no, no, no, no, no, you don't understand.

You want to get rid of it to make it clear that you are sending a message to yourself to get a thing and if it's a local variable, great. If it's proxy out to another service, it's transparent, and you don't need to know.

**AMIR:&nbsp;** Just so, I'm a little crazy --

**SAM:&nbsp;** -- Not much time refactoring.

**AMIR:&nbsp;** So I'm a little crazy that my actual method definitions don't have parenthesis either.

**DAVID:&nbsp;** That's a new thing for me. Six months ago, we could not have been friends.

[Laughter]

**DAVID:&nbsp;** But I'm actually okay with it now.

[Cross-talk]

**SAM:&nbsp;** -- Trip to Seattle and it's all good now.

**AMIR:&nbsp;** Why don't you have parenthesis? You're so weird! So, yeah, it was just such a subtle thing but, yes, perspective, right? You don't appreciate it until you come to a language that has come from a language that didn't have it. You have this crazy idea and all these refactoring tools because you have to parenthesis, and it's weird.

**SAM:&nbsp;** Any other things that you missed? I know when I used to do Visual Basic development. I really, really love the integrated debugger, and switching away from that, I spent a lot of time in some languages where you pretty much have to do print statement debugging. Even though, there are debuggers available on Ruby now, I'm still at print states --

**DAVID:&nbsp;** It's okay.

**SAM:&nbsp;** -- because like, why would I do that? Is there anything like that you miss?

**AMIR:&nbsp;** Yes, definitely it's the debugger. It's tricky. It's a swath of- I miss the debugger but I also learned to live without debugger. You go to spectrum, they get to work in. You want slow feedback, high fidelity, which is the debugger or fast feedback, low fidelity, which is the print statements. Being able to move across that spectrum was worth it.

That's something that when I was in Visual Studio, I only knew two things. I knew the low fidelity, high feedback which was compiler, and I knew high fidelity, low feedback, which was the debugger, and I didn't have a really good understanding what was in between and how you can ebb and flow through that spectrum. It was enlightening from that perspective but yeah, I do missed the debugger.

Another thing is that, I'm an Emacs user but I use Evil so I use them bindings with Evil, obviously. So it's the one true editor but I'll never be as productive that I would in C# that I am in Virtual Studio but, I gain productivity in every other language. And text files, because I can't even open a text from Visual Studio. I can Open XML, I guess, but there was a tradeoff there, and that's something I miss that I'm not as productive in C# anymore but I do have productivity across other language which is great.

**CHUCK:&nbsp;** The last big Windows project that I worked on was device drivers and so we had the Visual Studio debugger and then, when that failed us, we would whip out KD, which is the kernel debugger, or we would whip out, we call that Wind Bag. It was the W-N-D-B-G or something like that.

**AMIR:&nbsp;** DBG?

**CHUCK:&nbsp;** Yeah, and we just call it Wind Bag. The beauty of KD and Wind Bag is that they give you assembly code. You were looking at the actual opcodes going into the CPU on the machine. There was no more fidelity than that, other than a volt meter on a transistor or somewhere in the hardware. Yes, as Sam is mocking in the back channel for using the word 'beauty' there. He was absolutely beautiful --

**SAM:&nbsp;** Do you like memory heaps and light stack?

**CHUCK:&nbsp;** Yeah.

**SAM:&nbsp;** You always like pretty grass too and we're like, "Okay, we're the memory spike? How many process we've uses at that point in time." It's crazy.

**CHUCK:&nbsp;** I wanted that in Ruby for so long. I had a bug that took me six weeks to track down because you'd hit F12 in Visual Studio, and you get nothing. You'd be like, "I have no idea where the heck I am," and it took a kernel debugger to show me that we were destroying the stack so three instructions before. So by the time the debugger said, "Where am I?" All the information in the computer to tell the program where it is, was gone. It has been destroyed and I was able to actually track it through with like grain of rice, one step at a time until I found it. I was able to repair it in the binary and then say, "Okay, this is the code change that we made so this will fix that," and I've wanted that in Ruby for so long and it finally dawned on me - I'm never ever going to get an assembly output of Ruby code. It's never going to happen, stop wanting it.

**SAM:&nbsp;** Maybe a few years [inaudible] so it'll get close but even then --

**CHUCK:&nbsp;** Yeah.

**SAM:&nbsp;** One thing that I sometimes feel annoyed by having, again, made that transition from Visual Basic way back in the day, is that, especially at first, it feels like all of these things that you didn't even realize were separate functions, you have to go and find- First off, you have to realize that that thing that you want to do has a name and figure out what that name is and how to search for it. Then, you have to find a tool to do that one thing and it can feel like, you have to, you know, since you've undone [inaudible] from the IDE, like you have to go and master everything all at once. So that can be kind of overwhelming.

Sounds like you had some sort of transitional help with that by doing some built stuff in Ruby part way along the way. But did you hit at that at some point?

**AMIR:&nbsp;** I did. One of the biggest thing is that when I first started using or doing Ruby, it was just a straight then. Even auto-completion, I really didn't understand how to do auto-completion there. That was frustrating. You know, having to go to the docs and it was a major time sink.

But it has its benefits because when you start thinking about, "Well, my [inaudible] really do matter," I joke about it for .Net side is that depending on what type you have, the length of a numerable object is either link with parentheses, count as a property, or linked as a property. You never think of it because you have the IDE integration. Auto-completion just tells you, this is the type you have, this is the inference. When I started doing Ruby and JavaScript and all those things. I became very much aware about the consistency of my functions and methods and what I really expect to be there or not.

So again, you know, I miss it. The productivity aspects of it are- the auto-completion, even in Emacs with company mode and all this stuff, is not as good as a stackly-typed language. It just isn't. But I'm missing so much because we compensate by being more consistent with their function names are more predictable with a lot of that stuff. And you just let live and learn and then, you just really get good at [inaudible]. Everything's run of the bat.

[Laughter]

**SAM:&nbsp;** Just takes a [inaudible] and it'll be fine.

**AMIR:&nbsp;** Yeah, it's good. It's good.

**CHUCK:&nbsp;** All right. Well, it sounds like we've hit a LOL so let's go ahead and do some Picks.

**AMIR:&nbsp;** All right. My picks are going to be video games. Potentially Android games. My first pick would be Transistor. This is by the team that made Bastion. The cool thing about this game is that it's kind of like a turn-based role playing game where you play a computer program. It's got beautiful graphics, beautiful atmosphere, beautiful narrative, and they actually use the word 'Hello World' in the game. I immediately connected with that as a developer. You'll see a moment what I'm talking about. She like rides off in a motorcycle and says, "Hello World," and that was really cool. That's a fun game. It's a premium game. You pay once. No in-app purchase on that stuff.

My second Pick would be Hoplite. Some way too many hours in Hoplite. Hoplite is a turn-based strategy game but it's almost like a crossword puzzle for people that like turn-based strategy games. Every morning, I'll open it up and try to beat a level or try to beat one of the daily problems. So awesome. Hoplite would be my second game.

And the third game would be Alto's Adventure. Have anyone played Knights from the Sega Saturn, back in the day? It gives such a good experience of like flying and traversing dreams and all that good stuff. Alto's Adventure is a ski-jumping game almost but they do a beautiful job. The presentation is wonderful. The music is wonderful, and it's just a game that gets you in flow state of mind.

So Transistor, Hoplite, and then Alto's Adventure. Those are my three Picks.

**CHUCK:&nbsp;** All right. Sam, what are your Picks?

**SAM:&nbsp;** Oh, yes, we're on the topic of games. I've been playing a lot of Shadowrun Returns: Dragonfall. This is sort of a railroad-y game but it's got some really fun writing in it. There are a couple of bits of dialogue that really like made me laugh out loud. I enjoy sort of turn-based strategy games. I have a hard time finding good ones that I enjoy playing but this has occupied my free time for probably 30 hours or so now. The other nice thing is it's like $3 on Steam so it's a pretty low commitment, if you don't like.

**AMIR:&nbsp;** Three bucks on mobile game, that's way too much.

**CHUCK:&nbsp;** I know, that's super expensive.

**AMIR:&nbsp;** Way too much. Way too much.

**CHUCK:&nbsp;** I can't spend $3 on this. It'll make my thumbs tired. All right, Dave, what are your Picks?

**DAVID:&nbsp;** I was going to pick a tech Pick but I realize that if we're talking about games, I have to pick some games, and I remembered that I've actually got games that I need to pick and share with the show. The first one is Minecraft: Story Mode which is out on, I think, everything. iOS is the platform that I prefer on the Mac port for Steam. Once you can get it installed and playing and working, it's pretty good. But it is the absolute worst install experience I have ever had, bar none on a Macintosh. You'll see what I mean if you try to use it. Once you're into the game, you're okay. You're golden. But yet, a full screen app, you can't command tap out of and it presents a dialog somewhere off screen that you have to interact with. And this is a positive Pick. Once you're in the game, it is --

**AMIR:&nbsp;** -- Story Mode [inaudible]?

**DAVID:&nbsp;** Yeah, Minecraft: Story Mode. I'm playing on the iPad. Absolutely, loving it. The voice acting is superb. I love Patton Oswalt. It's just a ton of fun. It's from Telltale Games. We know they do really good episodic-type games. I'm just buying the packs as they come out. They will sell you four episodes at a time. They just recently released Episode 6. They're $5 an episode and they are about two hours’ worth of gameplay each. I mean, they're pretty short. But you can go back and change your choices as you go through.

Episode 2 in particular, you'll feel a little bit ripped off because it feels like it's only half an episode because you go after one of these legendary people heroes to recruit them and it turns out that in story one, you make a choice between which hero you want to go after and you get a completely different chapter two, if you pick the other person. So there's a reason it feels like half an episode, it's because you only played half the episode. You went the other way. So it's a lot of fun. Tons of tons of replay value.

The other one was Never Alone: Ki Edition. It's been ported to iOS, as well. You can play on the iPad. It is one of the most gorgeous games I've ever played. It's absolutely immersive and beautiful and wonderful and fun. Those are the game Picks that I have and you know what? I'll save my tech Pick for next week so those are my picks.

**CHUCK:&nbsp;** All right. I've got a couple of Picks. The first one is, I know it's not on the level of Dave's Hot Sauce Picks but lately I've been eating a lot of ramen noodles with Sriracha sauce in it. I just love it.

**AMIR:&nbsp;** So good. I'm right there with you, buddy.

**CHUCK:&nbsp;** One other thing, my dad, he was a missionary in Japan and so one of the things they put in their noodles in Japan is eggs. So typically, what I'll do is I'll actually take the ramen, get the water to a boil, then I'll add the flavoring to it, and then I'll beat an egg and drop it in there and then I'll put the Sriracha in and that's really good. So I'll pick that. I've been to a few ramen restaurants in Las Vegas and in San Francisco and here in Salt Lake and there are some pretty good places.

I'm also going to really quick mention that the show does have a Facebook page. In fact, the show should go out around the end of August so if by the end of September, we have 250 likes, then, I'll do a free webinar and I'll let whoever's on the Facebook page actually pick, if they wanted to be.

**AMIR:&nbsp;** Speaking of ramen, I got accepted to a RubyKaigi to present over there. So I'll be presenting on Game Development Plus Ruby Equals Happiness. Just a general idea of building games with Ruby, what it feels like, the evolutionary aspect, having functions called pro-grenade and kill anime, and how cool that is and all that good stuff.

**CHUCK:&nbsp;** Nice.

**AMIR:&nbsp;** So if you find yourself in Japan. Reach out to me, we'll have ramen, and all that good stuff.

**CHUCK:&nbsp;** All right. Well, I don't have any other pics so we'll just go and wrap this up. Amir, if people want to follow you on Twitter or see what else you're doing, where do they go?

**AMIR:&nbsp;** I'm on Twitter. My handle is @AmirRajan. From there, you'll see my website it's AmirRajan.net. I chose the .net ending, that was deliberate back in the day and I've kept it since then. So you have AmirRajan.net. I also have a book out about Surviving The App Store. It's a Leanpub publication if you go to Leanpub.com/SurvivingTheAppStore. You can read all about the revenue, my marketing tactics, all that good stuff and you kind of see everything there. From my sabbatical, all the way to the rise and fall of ADR. I got that also. Feel free to reach out to me. I'm more than happy to talk about anything.

**CHUCK:&nbsp;** Very cool. Well, for the show, these guys got me to install Pokémon so I have to go outside now and catch one.

**SAM:&nbsp;** Oh, no.

**CHUCK:&nbsp;** So, we'll wrap this one up, and we'll catch you all next week.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Would you like to join a conversation with the Rogues and their guests? Want to support the show? We have a forum that allows you to join the conversation and support the show at the same time. You can sign up at RubyRogues.com/Parley.]_**


