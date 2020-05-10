---
layout: post
title:  "No-thread support in HawkTracer"
date:   2020-05-10 14:40:31 +0000
permalink: /:year/:month/:day/:title
---

### TL;DR
HawkTracer no longer requires a multithreading environment, so you can use it to profile applications running without OS, e.g. on microcontrollers.

### Why?
From the very beginning HawkTracer required a runtime which supports multi-threading. It wasn't a problem, since most of the time HawkTracer was used with applications running on advanced operating system (mainly Windows, Linux or OSX).

Recently we found another usecaes for HawkTracer - profiling applications running on microcontrollers. The feature has been requested by [@andreasbuhr](https://github.com/andreasbuhr) ([issue #73](https://github.com/amzn/hawktracer/issues/73)).
Number of applications running on microcontrollers is rather simple and doesn't require advanced operating system, using HawkTracer in its current state wasn't an option.

Today we've merged [a change](https://github.com/amzn/hawktracer/commit/bd2fa02692911a8e7a98d2be99a31c3cf98f81f0) that makes threading optional in HawkTracer, so it can be used in very simple environment.

The change can be found in master branch, and will be available in the next HawkTracer release (v0.11.0).

### Limitations
With threading support disabled, HawkTracer limits some of the functionality:
 * no thread safety - all the thread-safe features (e.g. thread-safe timeline) is no longer safe - HawkTracer assumes there's only a single thread, and disables all the internal checks
 * single instance of Global Timeline - when threading support disabled, HawkTracer creates only one Global Timeline for the whole program (instead of timeline-per-thread, as it's done when threading support is enabled) - this limitation again is caused by assumption that application doesn't run more than one thread
 * TCP listener not available - at the moment TCP listener requires background thread to listen to incoming TCP connections. If threading is disabled, the listener can't be used.

### Usage
To compile HawkTracer with multithreading disabled, use following CMake command:
```bash
cmake -DENABLE_THREADS=OFF -DENABLE_TCP_LISTENER=OFF hawktracer_build_dir
```

Threads can be also disabled in the amalgamated HawkTracer files, by undefining `HT_ENABLE_THREADS` and `HT_ENABLE_TCP_LISTENER` macros in the `ht_config.h` configuration file.

### Contributors
Special thanks go to [@andreasbuhr](https://github.com/andreasbuhr) who requested the feature and tested our changes with ARM Cortex-M7 microcontroller. Thank you!
