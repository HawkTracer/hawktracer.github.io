---
layout: post
title:  "HawkTracer 0.10.0 released!"
date:   2019-11-09 22:19:49 +0000
permalink: /:year/:month/:day/:title
---

We're pleased to announce HawkTracer 0.10.0 (Squirrel) release!

### Download
You can download the release from the GitHub page: [https://github.com/amzn/hawktracer/releases/tag/v0.10.0](https://github.com/amzn/hawktracer/releases/tag/v0.10.0)

### Changes
  * fix amalgamation process for non POSIX.utf-8 locale (#65)
  * restore Python binding tests
  * simplify and document timeline features
  * allow using dynamic strings as labels for tracepoints in C language (C++ already had that feature)
  * fix memory leak on uninitializing HawkTracer library
  * implement automatic memory management for listeners (so the listener object no longer needs to be manually destroyed)
  * simplify FileDump and TCP listener's API (introduce one function to create listener and register it to a timeline)
  * introduce new, polished tracepoint macros
  * add more benchmark tests
  * minor bugfixes and documentation improvements
  * deprecate:
    - ht_timeline_register_listener: ht_timeline_register_listener_full should be used instead
    - ht_timeline_unregister_all_listeners: HawkTracer no longer allows unregistering listeners. Instead, user should call _stop() methods on the listener object

### Contributors
This releaes couldn't be made without our awesome contributors. Many thanks!
* [Marcin Kolny](https://github.com/loganek)
