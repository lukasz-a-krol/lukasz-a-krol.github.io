---
layout: page
permalink: /airtags_stationary/
custom_css: longtext
title: Using AirTags to detect stationary iPhones
sidebar_link: false
---
&nbsp;


On April 30th, 2021, Apple released a new product, called the AirTags. Those small, round devices can quickly find and track lost objects such as keys or bicycles. Almost instantly after the announcement, concerns emerged that AirTags could be also be used to track people, too. Apple did, to its credit, add some anti-stalking and anti-tracking mechanisms to the AirTags. An AirTag that is travelling with someone who is not its owner is meant to alert its target thereof, either through a notification (for those who have Apple devices with iOS 14.5 or higher) or through an audible noise that they make after three days. Only a few days after the AirTag's release, [many security experts](https://www.washingtonpost.com/technology/2021/05/05/apple-airtags-stalking/) [described their mechanisms as ineffective](https://mashable.com/review/apple-airtags-review/?europe=true): an AirTag slipped into somebody's coat pocket or backpack could easily have revealed their home address by the time the notification shows up or an alert rings.

While most of the security research has focused on how moving AirTags could be used to track people while they are in motion, the devices have one more crucial security flaw: they can be used to offer a regularly updated map of iPhones and, by extension, their owners.

To test this out, I left an AirTag in my parked car, and went for a long walk. Unsurprisingly, I could go on the *Find My* App on my iPhone and see where my car was located (every AirTag is allocated an emoji, which is used to show its location on a map). But what was perhaps more interesting is *when* the location was last updated: 17 minutes ago. I had left my car much earlier, so my AirTag must have contacted—or pinged—other iPhones than my own.

<img src = "/images/IMG_0185.PNG" height = "500px">

_Please note that all screenshots have been edited to preserve the privacy of those involved in the tests_

AirTags work by leveraging Apple's *Find My* network. In short, they send out regular signals which iPhones (and other Apple devices) pick up on. Apple claims to have [hundreds of millions of devices in its *Find My* network](https://www.apple.com/newsroom/2021/04/apples-find-my-network-now-offers-new-third-party-finding-experiences/)—so whenever an AirTag is close to one of them, its location should automatically be updated in the *Find My* network, and visible in the iOS app.

This, however, means that the AirTag can report on one more interesting fact—when it last connected with an iPhone or similar device. This matters little in a densely populated city like San Francisco, with its small flats and a huge amount of iPhones per square kilometer. But in a detached house or a location with far fewer iPhone owners, such information can be very revealing.

To test it out, I left behind an AirTag at a friend's house and went for a day trip. I regularly hang out at said house, so it wouldn't be out of the ordinary that I might leave a backpack containing an AirTag behind. But it turned out that, by seeing their AirTag's last seen time, I could easily track whether or not my friend was home, just by seeing whether the AirTag was in the Bluetooth range of any iOS devices.

<img src = "/images/IMG_0456.PNG" height = "500px">

I could easily tell that the AirTag had not pinged any devices for hours, suggesting an empty house.

<img src = "/images/IMG_0458.PNG" height = "500px">
sadfasfdaf
When my friend entered the house with a Bluetooth-enabled iPhone, it instantly connected to the AirTag, which I friend could also see after checking it on the *Find My* app. By detecting the presence of Apple devices, an abandoned AirTag could, by proxy, easily figure out whether or not somebody's house or office is currently empty.

To test this out further, I've been trying to measure the indoor range of AirTags (they seem to connect up to 25m, even across a wall, enough for a parked car to potentially detect an active iPhone inside a house, though this might also depend on the type of chip the iPhone has) and how often their location is updated in the *Find My* service (one article [suggests that AirTags broadcast two seconds](https://positive.security/blog/send-my), but observations have shown that, if they are around an iPhone other than that of their owner, their location is updated at irregular intervals, which are no longer than 30 mins). More testing is needed in both cases.

An attacker or social engineer could, for example, go to a business meeting and conveniently "forget" and leave behind a folder with an AirTag in a meeting room or executive's office. They could then, with a certain degree of confidence, figure out when said room is empty of Apple devices, which in many cases would mean that it is empty of occupants as well. Even more chillingly, an AirTag left behind in somebody's flat could even pick up neighbours' Bluetooth signals, similarly giving an indication when they are out. We tested this with a friend here:

<img src = "/images/IMG_0210.PNG" height = "500px">

As I went out for a bike ride with a friend, I left two AirTags, one at each end of a flat. One of them kept on pinging a device that was part of Apple's *Find My* network, the other one did not. This suggests that a neighbour in the block, and one who had a flat south of ours, had a device such as an iPhone on them. This isn't just information visible to a potential malicious attacker: anybody who left an AirTag behind at their phone could deduce the activity in their flat or the flats around them based on the prior pings the tag received.

<img src = "/images/IMG_0212.PNG" height = "500px">

The moment my friend re-entered the flat with a Bluetooth-enabled phone, both of my AirTags instantly connected to it. Any potential attacker who left an AirTag—or several—in a flat would instantly know that its occupant had returned (unless every neighbour also had constantly pinging iPhones in range of that AirTag).

While Apple does have the ability to alert somebody if an AirTag is suspiciously close to them, none of those attacks described above require anything  unusual or suspicious to happen. People forget folders, or leave behind AirTags in their flats all the time. Any attacker using this technique would have significant plausible deniability.

Such an attack does not, of course, offer perfect information. An empty flat could easily contain Macbooks or iPads that ping an AirTag (though I wasn't able to replicate this in testing; the AirTags I had stubbornly refused to pick up signals from either, only wanting to connect to iPhones). Similarly, AirTags do not reveal *whose* iPhone they connect to. An attacker has no way of knowing whether the AirTag last received a ping from their target's iPhone or from that of their neighbours. Finally, a target could still be in their home of office, and just outside of the AirTag's range, limiting the attack surface even further. Still, even coarse data might be sufficient for an attacker who wishes to conduct reconnaissance. Not only this, but it's incredibly hard for a detached suburban house's AirTags to get pings from anywhere but the house itself, reducing chances for false positives. Trust me, I tried.

In theory, any attacker could trivially build a Bluetooth scanner, or use another product with much worse anti-stalking and anti-tracking features. In practice, two things make AirTags particularly so useful to a potential attacker: their ubiquity and their plausible deniability. AirTags are relatively cheap, easy to purchase, and will soon be used quite widely. Secondly, an AirTag that has been "accidentally" left behind in an office within a folder or toolbox will arouse far less suspicion than, for example, a custom built Bluetooth tracker. To Apple's credit, it's very easy to track down the real owner of an AirTag, but this matters little if the attack can hide behind a veneer of plausible deniability, for example by pretending that they had accidentally left behind a jacket containing an AirTag at somebody's house.

Notably, an AirTag cannot track somebody's presence in a room if they have disabled Bluetooth on their phones. Still, with Apple getting rid of the headphone jack in favour of wireless connections, the amount of iPhones with always-on Bluetooth is likely to increase even further in the near future.

There is always room for hope. Apple could introduce updated, both the AirTag firmware and iOS, that might make such tracking more difficult to perform. Doing so might, however, reduce the effectiveness and granularity of the *Find My* network. Only time will tell what steps the tech giant will eventually take to further beef up the security of AirTags and its wider Find My network.
