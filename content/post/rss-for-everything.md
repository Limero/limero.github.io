---
title: "Use RSS for Everything"
date: 2019-07-30
---

## Introduction
I used to visit many different websites daily. Websites that all had different layouts without any form of consistency. On some websites, especially Twitter and Facebook, you even have to mentally filter out a bunch of junk every time you visit. It all gets tiring eventually, because it wastes your time.

The solution is to only follow the things that you care about. This is where RSS feeds and a reader comes to the rescue. You can get all your news, articles and things you care about in one consistent, minimal interface. A place where your in control of what you see and how you want it to be displayed. Just the way you want it, right?

## RSS reader

### NewsBlur
My choice of RSS reader is currently NewsBlur. It's open source, can be self hosted and it syncs between all your devices. Their web client and phone apps are all great. I choose to use their officially hosted version available at [newsblur.com](https://newsblur.com). You can use that for free with a limited amount of feeds, but I opt to pay for their premium service to support them and be able to follow an unlimited amount of feeds.

My favorite feature of NewsBlur is their [intelligence trainer](https://blog.newsblur.com/post/168431864825/intelligence-training-comes-to-newsblurs-android). You can use it to automatically hide stories matching certain keywords. So if you are not interested in a subject, you don't have to see it, but you can still get everything else from that feed.

### Newsboat
Another one of my favorite RSS readers is [Newsboat](https://newsboat.org), previously known as Newsbeuter. It's open source, it runs in the terminal and it can even fetch stories from NewsBlur. My primary problem with this reader is that when used with NewsBlur, it grabs the list of followed feeds and then checks them one by one, making it take way longer than to just use NewsBlur's own web client. I have started a discussion on if it's possible to improve NewsBlur usage in Newsboat which can be followed [here](https://github.com/newsboat/newsboat/issues/513). Until a solution is found, if you only use one device, no server sync with NewsBlur or similar services, then Newsboat is great and I highly recommend it.

## Services
### YouTube
YouTube has official support for RSS feeds for a channel's video uploads. Visit the channel you are interested in and grab the channel ID from the address bar. The channel ID contains 24 random characters.

If the channel you want to follow has a username in the link instead of a channel ID, you can use the [Youtube Username to Channel ID Converter](http://johnnythetank.github.io/youtube-channel-name-converter/) to extract it.

It can then be added to your reader like this:

```
https://www.youtube.com/feeds/videos.xml?channel_id={channelID}
```

### Mastodon

[Mastodon](https://joinmastodon.org/) is a "free, open-source social network server based on ActivityPub.". It's decentralized, so different people will be on different instances. But the format for the feeds are the same.

Mastodon has both Atom and RSS feeds available. I use RSS because Atom includes replies in addition to standalone posts.

Here are two example feeds of people I follow on different instances:
```
https://cmpwn.com/@sir.rss
https://octodon.social/@emersion.rss
```

### Twitter
Twitter does not offer official support for RSS, so their content must be crawled. There is an easy to use free service for this called [TwitRSS.me](https://twitrss.me) so Twitter users can be followed like this:

```
https://twitrss.me/twitter_user_to_rss/?user={username}
```

### Facebook
Facebook, just like Twitter has to be crawled to get a feed. There are services that do this for you. The one I use is [FetchRSS](https://fetchrss.com). It can be used for free but is limited to 5 feeds and requires registration.

```
http://fetchrss.com/rss/{string}.xml
```

### Blogs
This will probably be your main source of feeds. Sometimes it's not easy to find the feeds though, even when the websites have them. I usually open the page source (press CTRL+U in your browser) and search for `RSS`, `atom`, `xml` or `feed` and add the URL to my reader.

Here is the feed for this blog:
```
https://limero.se/index.xml
```

#### WordPress
Many blogs are made with [WordPress](https://wordpress.org) and they will always(?) have a feed available at:

```
example.com/feed
```

### Music releases
Spotify has a feature on their website where you can [enable e-mail notifications](https://spotify.com/account/notifications) for new releases by artists you follow. It used to work well but I find it very unreliable now. Sometimes I get release e-mails, but most often not.

I don't want to miss new music from my favorite artists, so I use RSS for this too. Neither Spotify, Apple Music or any of the other big music streaming sites offer this natively as far as I know, so my solution is to crawl. There is an useful tool called [RSS-Bridge](https://github.com/RSS-Bridge/rss-bridge) that can be self hosted and used to crawl websites to generate feeds. I created a crawler script for Apple Music and it has since been [merged upstream](https://github.com/RSS-Bridge/rss-bridge/pull/1026) so it's easy if you want to use it too.

### GitHub/GitLab
GitHub and GitLab are both excellent when it comes to RSS support. You can get almost anything as a feed by adding `.atom` to the end of the URL. Here are some examples, but you can do way more than this.

Want to follow releases on a project?
```
https://github.com/{username}/{project}/releases.atom
https://gitlab.com/{username}/{project}/-/releases.atom
```

Want to follow activity of a certain user?
```
https://github.com/{username}.atom
https://gitlab.com/{username}.atom
```

Want to follow commits to a certain branch?
```
https://github.com/{username}/{project}/commits/{branch}.atom
https://gitlab.com/{username}/{project}/commits/{branch}.atom
```

### Reddit
Reddit has almost as good support for RSS feeds as GitHub/GitLab. You can follow most things. For following subreddits, I prefer to use the `top scoring links` feeds to only get the top posts. A problem with the feeds from Reddit is that the amount of stories is limited, so if you don't fetch the feeds often, you'll miss out on stories. This is not a problem if you are using NewsBlur, which will continuously fetch feeds.

Some examples for following a few different subreddits:
```
https://reddit.com/r/archlinux/top.rss
https://reddit.com/r/linux/top.rss
https://reddit.com/r/selfhosted/top.rss
```

## Conclusion
RSS might not be everyone's cup of tea, but it has increased my productivity and focus, and it will likely do the same for you. I start my reader, look and the stuff I'm interested in, get out and then go on with my day.

Do you have any cool RSS tricks that you have found or have something that could improve the way I use RSS? Feel free to [contact me](/contact/).
