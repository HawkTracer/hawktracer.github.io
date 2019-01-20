---
layout: post
title:  "HawkTracer 0.7.0 released!"
date:   2019-01-26 17:01:32 +0000
permalink: /:year/:month/:day/:title
---

We're pleased to announce HawkTracer 0.7.0 (Rabbit) release!

### Download
You can download the release from the GitHub page: [https://github.com/amzn/hawktracer/releases/tag/v0.7.0](https://github.com/amzn/hawktracer/releases/tag/v0.7.0)

### Changes
* fix crash when pushing events of size bigger than timeline's buffer
* [api change] rename HT_EVENT_GET_CLASS to HT_EVENT_GET_KLASS
* [api change] remove ht_timeline_listener_container_unref() from public
API
* fix data race when referencing/dereferencing timeline container object
* enable code coverage reporting on CI
* add feature for tracking heap allocations
* support informations attached to tracepoints for Chrome Trace converter
* remove C++ dependency for the HawkTracer core library
* add amalgamation script for generating single source/header HawkTracer
files
* improvements in the installation process (thanks J. Kim and Alexandru!)
* support reading big-endian data on little-endian platform (and vice
versa)
* many other tiny bug fixes and minor improvements

### Contributors
This releaes couldn't be made without our awesome contributors. Many thanks!
* [Alexandru Ene](https://github.com/alexene)
* [Justin Kim](https://github.com/justinjoy)
* [Marcin Kolny](https://github.com/loganek)
