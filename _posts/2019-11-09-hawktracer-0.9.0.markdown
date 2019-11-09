---
layout: post
title:  "HawkTracer 0.9.0 released!"
date:   2019-11-09 17:30:19 +0000
permalink: /:year/:month/:day/:title
---

We're pleased to announce HawkTracer 0.9.0 (Vole) release!

### Download
You can download the release from the GitHub page: [https://github.com/amzn/hawktracer/releases/tag/v0.9.0](https://github.com/amzn/hawktracer/releases/tag/v0.9.0)

### Changes
  * support dynamically allocated strings as labels for tracepoints
  * support auto-deleting tasks from task scheduler
  * add function for force-flushing file listener #51
  * fix compilation on some platforms (thanks Iakov!)
  * fix thread safety of ht_timeline_flush() API #56
  * allow configuring Global Timeline buffer size #59
  * documentation improvements

### Contributors
This releaes couldn't be made without our awesome contributors. Many thanks!
* [Iakov Sumygin](https://github.com/yak32)
* [Marcin Kolny](https://github.com/loganek)
