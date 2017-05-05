# Stewart Lord

My resume is available upon request. This repo provides some deep links into interesting code I've written.

## A Bit About Me

I am passionate about the user experience. I respect simple pragmatic architecture. I think we should optimize the ratio of lines of code to user happiness. I want to know that what we're building delivers value. Some people affectionately call me a pixel nazi, or a code nazi because I care about the details. I like to solve gnarly problems and I love working with other passionate, talented people!

## Diff Changes

[Swarm](https://github.com/stewartlord/swarm) is a code review tool. This code sample determines the work an author did in a particular version of a review or between two versions of a review. If one version is given, it is easy. If two changes are given, it is hard.

[Reviews\Controller::getAffectedFiles()](https://github.com/stewartlord/swarm/blob/master/module/Reviews/src/Reviews/Controller/IndexController.php#L2015,L2149)

## Pragmatic Abstraction

Open Source projects tend to evolve organically. This often results in practical code that solves problems simply and with minimal disruption. When it came time to add SVG support to my popular [Identicon.js](https://github.com/stewartlord/identicon.js) library, I wanted to do so without breaking backwards compatibility and with minimal risk of regressions. To do so I wrote a small Svg class that adhered to the same interface exposed by PNGlib. This meant that the existing code was largely untouched and made it trivial to switch between SVG and PNG rendering simply by swapping out the image class.

[Identicon.Svg](https://github.com/stewartlord/identicon.js/blob/master/identicon.js#L138,L188)

## Memory Efficient Cache

[Swarm](https://github.com/stewartlord/swarm) talks to one or more Perforce Servers. Some data, most notably users and groups, is costly to query and must be accessed frequently. This data requires a local cache to achieve acceptable performance. The following code samples link into a library that provides cache invalidation via distributed counters and memory efficient reads/writes via streaming array iterators.

[Record\Cache\ArrayWriter](https://github.com/stewartlord/swarm/blob/master/library/Record/Cache/ArrayWriter.php)

[Record\Cache\ArrayReader](https://github.com/stewartlord/swarm/blob/master/library/Record/Cache/ArrayWriter.php)

## Magic Scrolling!

[Contrast](https://github.com/stewartlord/contrast) is a mostly dormant side-project of mine. It is a desktop diff viewer written in JavaScript with Electron. One of the goals behind this project was to gain some experience with Electron. Another goal was to implement an algorithm that would ensure the left and right lines in a side-by-side diff are aligned on a focal point as the user scrolls through the document. Beware, the code is a bit messy as tends to happen when one is hacking around on a side-project!

[script.js](https://github.com/stewartlord/contrast/blob/master/script.js#L383,L408)

## Search Expression Modelling 

Queries are often expressed as strings. This works pretty well for humans and for predefined lookups. But, what happens when an expression needs to be passed around and manipulated in several places in your code? The following sample models a search expression that can be built-up and pulled apart by adding, removing and nesting condtions.

[P4\File\Filter](https://github.com/stewartlord/chronicle/blob/master/library/P4/File/Filter.php)