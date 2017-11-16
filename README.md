# Build `hsdis` for OpenJDK 9

This repository provides a script to build the OpenJDK 9 `hsdis` library with
binutils for 64-bit Linux to enable the `PrintAssembly` JVM option.

Simply run `./build` to download the dependencies and build and verify the
library.

## Motivation

There are many documented ways of obtaining an `hsdis` library. At this point
in time, shortly after the release of Java 9, most are incomplete or outdated
or for some reason simply fail to work.

On Ubuntu 17.10 the simplest way--ostensibly--to obtain an `hsdis` library is
with `apt install libhsdis0-fcml`, but my OpenJDK 9 JVM refuses to load that
binary. It also refuses to load [a manually built FCML 1.1.3][fcml].

The OpenJDK Wiki provides [instructions for building the OpenJDK 9 `hsdis`
library][openjdk], and JITWatch directs to [another set of
instructions][jitwatch], but both instructions are incomplete.

[fcml]: https://sourceforge.net/projects/fcml/
[jitwatch]: https://github.com/AdoptOpenJDK/jitwatch/wiki/Building-hsdis
[openjdk]: https://wiki.openjdk.java.net/display/HotSpot/PrintAssembly

## License

This software is released under the GNU GPLv3 on account of
`binutils-2.23.2.patch` being a derivative work of software released under that
license.

The `hsdis` library is released under the GNU GPLv2 only.

The `hsdis` license is incompatible with the GNU GPLv3. This software neither
modifies the `hsdis` software nor distributes any dependencies so I contend
that, as far as `hsdis` goes, the derivative nature of this software is on par
with instructions written for human beings and therefore not in violation.
