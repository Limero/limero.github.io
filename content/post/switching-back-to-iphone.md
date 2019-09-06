---
title: "I'm Switching Back to iPhone"
date: 2019-09-06
---

## Background

My first smartphone was the iPhone 4, next one the iPhone 5 and my third, the iPhone 6. I then switched to Android and went OnePlus One -> Nexus 6P -> OnePlus 5T. I have now decided that it's time for me to go back.

For the last year, I have been actively working on moving away from Google services. Primarily because I don't trust them. They collect way too much data about its users. Check out what they have about you in [My Activity](https://myactivity.google.com). Getting rid of Android is my next step and iPhone is the way I will go.

Apple's [approach to privacy](https://apple.com/privacy/approach-to-privacy) is one I respect more than the direction other tech companies go, where they collect tons of personal data and sell it to third parties. Apple still makes proprietary systems so there is no way to guarantee that they are doing what they are saying, but I generally trust Apple more than the other tech giants.

## Operating system

The iPhone comes with a clean software experience out of the box. You set it up and you are done. Every iPhone looks and behaves the same, for better or for worse. You give up much customization, but you gain a great experience right away without tweaking. You are also guaranteed to continue to get software updates directly from Apple for years to come.

When you buy an Android phone, it comes with the vendor's own flavor of Android. A Samsung phone and an LG phone will look and behave completely different, even though they are both running Android. Different manufacturers ship varying amounts of modifications and extra applications on their phone. Some companies, such as OnePlus, Sony and Motorola ship a ROM relatively similar to clean Android, while Samsung and LG ship a ton of junk a top of Android.

The problem is that the ROM shipped in all of these phones is proprietary. You don't know what is being done on your phone in the background. You will have to trust the company that made your phone. I don't trust any of the big companies making Android phones, not even [OnePlus any more](https://gizmodo.com/oneplus-admits-it-was-snooping-on-oxygenos-users-says-1819487335). Even if you trust the manufacturer, the phones all come with Google services installed from the factory, so they will spy on you regardless.

The solution is to run a custom ROM from a vendor you trust, preferably where all source code is open source and available. The most famous one is LineageOS (previously known as Cyanogen OS) and it is my ROM of choice. It doesn't come with Google services and it's code is all open source. The problem is that LineageOS is very hit or miss, even on officially supported devices. On my old OnePlus One, it's rock solid. Everything just works.

However, LineageOS on my OnePlus 5T has not been as smooth. I run the latest nightly builds, as no stable releases are available yet. Occasionally the phone will randomly restart and the general performance varies. The OnePlus 5T is also a device still supported by OnePlus, so new firmware updates has to be flashed manually or LineageOS will not update. Sometimes the firmware can't be flashed unless you update your custom recovery, which in my case is TWRP, and you'll have to run a custom version because the official releases are not kept up to date.

Also, when you run a custom ROM, some apps will not work, such as Pokémon GO. This can be fixed by rooting your phone with Magisk and then using Magisk to hide the root to pass SafetyNet.

The more I have to do the steps above, the more I appreciate a nice out of the box experience. An experience that iPhone gives me.

## Applications

When you chose to run Android with as little Google services as possible, you will be making sacrifices. The open source alternatives for many Google apps are not as good. Understandable, as they are made by volunteers as hobby projects while Google puts millions into their projects and has a lot of data collected through varying methods.

When the open source alternatives are not as good, you can either work with inferior products (that's what I have done previously) or sell your soul to another company, like Microsoft.

### Maps

This is the biggest one. Google Maps is the best. Google has huge amounts of data. When you look up a company, Google will have it and they will have the opening hours, reviews and other useful information.

OpenStreetMap might have better maps than Google, but the information about places is lacking. Having to look up opening hours on a company's Facebook page is awful.

The open source app I found to work the best is [Maps](https://f-droid.org/en/packages/com.github.axet.maps) (a fork of MAPS.ME). It is based on OpenStreetMap, so the maps are great, but finding companies and up-to-date information about places is almost impossible depending on the area. Public transport data is not available where I live either.

[OsmAnd](https://f-droid.org/en/packages/net.osmand.plus) is another alternative recommended by many Android users, but I find it way to sluggish and difficult to use.

Apple Maps is not as good as Google Maps, but it has improved a lot since it was first release in 2012. It has a very fast and easy to use app. While it doesn't have as much data has Google Maps, it has way more than OpenStreetMap. Public transport works great too.

### Apple Pay

Sometimes it's convenient to be able to buy things in a store with only your phone. Avoid Google Pay though, as you'll give Google a comprehensive list of all purchases.

Apple Pay is better. Much better. Even better than directly using your debit card. Apple only saves "anonymous transaction information" and they generate unique information for each transaction, so if you go to a store multiple times, the store can't connect the visits together to create a profile on you. If you instead use your debit card, the store knows that you are the same person returning and they could use that information to analyze your purchasing habits.

It's possible that Apple Pay is the second most private way of buying things in a store after paying with cash.

### Health

Pokémon Go has a feature called Adventure Sync that will give you benefits in the game even if you walk with the game turned off. This is done by reading data from your health app. On Android, this is Google Fit. If you play Pokémon Go on an Android phone you can either avoid Fit and be at a disadvantage or you can enable it and let Google monitor you.

Using an iPhone, this monitoring is done through Apple's Health app which should be more privacy friendly.

### iMessage/FaceTime

I don't plan on going deep in to Apple's ecosystem and I will continue to use other alternatives, such as [Signal](https://signal.org).

However, some people continue to use regular plain text SMS, so having the ability to use iMessage for these people is much better. The same applies to FaceTime.

### App Store

On Android, you are allowed to install whatever you want from wherever you want. Sometimes it is nice, but in day-to-day use, it's more of a hassle, at least if you don't want to use the Google Play Store.

All open source apps are installed through [F-Droid](https://f-droid.org) and then [Aurora Store](https://f-droid.org/en/packages/com.aurora.store) is used for everything else that would previously be installed through the Google Play Store.

On iPhone, everything is installed and updated automatically through the App Store. Less freedom, but also less things to manage.

# Conclusion

The operating system on the iPhone is not open source, the applications are not open source, the services they run are not open source. You don't own your phone, you are renting it from Apple.

I have struggled enough to make Android less terrible and have had enough. If you want to use a phone to it's full potential **today**, you'll have to embrace a big American corporation.

I trust Apple way more than I trust Google. Apple is selling expensive hardware and overpriced accessories. Google is selling your data.

My next phone will be an iPhone and I will use it until better alternatives are available. My eyes are on the [Librem 5](https://puri.sm/products/librem-5).
