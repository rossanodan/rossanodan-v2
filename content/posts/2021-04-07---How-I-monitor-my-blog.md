---
title: How I monitor my blog
date: "2021-04-07T22:00:00.000Z"
template: "post"
draft: false
slug: "how-i-monitor-my-blog"
category: "General"
tags:
  - "NewRelic"
  - "Monitoring"
description: "I use different monitoring and analytics tools to monitor my blog. Among them New Relic."
socialImage: "/media/how-i-monitor-my-blog.jpg"
---

## What

I use different monitoring and analytics tools to monitor my blog: [Google Analytics](https://analytics.google.com/), [Vercel Analytics](https://vercel.com/analytics) and [New Relic](https://one.eu.newrelic.com/). Maybe is too much, given that my blog doesn't have a lot of traffic and it's not a "critical system" to be continuously monitored and kept online (if it goes down for a couple of minutes no one will complain!). But since these services are free to use and since I use New Relic at work, I decided to use it for my blog and maybe to learn more about it.

But.. **what is New Relic**? Well, this is what I understood so far: New Relic is a **monitoring tool that provides real-time data, usage analytics and allows you to monitor your services and to set alarms** for them (imagine you want to receive a notification when one of your services goes down to be able to promptly respond to the failures). If you want a more specific definition of it, visit the [official documentation](https://docs.newrelic.com/docs/using-new-relic/welcome-new-relic/get-started/introduction-new-relic/).

I don't monitor any service for my blog - I don't have any! - but only the front end performances. And I do so with [New Relic One](https://docs.newrelic.com/docs/new-relic-one/use-new-relic-one/get-started/introduction-new-relic-one/).

## Why

I do monitor my blog because I want to understand its performances and what I can do to improve it.

## How

My blog is built with GatsbyJS so I used the plugin [gatsby-plugin-newrelic](gatsby-plugin-newrelic). I won't write here what I did to set up New Relic because there's nothing their [README](https://github.com/newrelic/gatsby-plugin-newrelic/blob/main/README.md) doesn't say. And it explains how to do it so well!

What I can add is that I monitor only my production environment. Here's [my configuration](https://github.com/rossanodan/rossanodan/blob/master/gatsby-config.js#L163) to monitor production.

Here you can see a part of my dashboard where I see data coming through.

![The dashboard](/media/Dashboard-1.png)

Here you can see my blog's **FID**, First Input Delay.

> To put it in simpler terms, the FID is the delay between when you click or tap on something like a link or a button, and the time that the browser responds to your action and starts processing it.

![How long my blog takes to load by URL](/media/Dashboard-2.png)

I want to be honest: I can't understand all of these charts yet. But that's why I choose to monitor my blog with New Relic: I want to learn and become more familiar with it.

So don't blame me if I'm not saying anything really interesting in this article. More interesting stuff will come, with time.

## Conclusion

I started monitoring my blog a few days ago so, for now, there's not so much I can say but New Relic looks good and very easy to use. It offers a lot of charts, analytics and alerts... Which I didn't try yet!!

If you are searching for a good monitoring tool for your application, New Relic is what you need.