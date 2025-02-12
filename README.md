## *This Fork* ##

This is a fork of hashcat-legacy that probably no one should use.

I created this so I could solve a WebGoat challenge that involved cracking the signature of a JWT.  Way easier to use the latest hashcat (which has direct support for JWTs), but it wouldn't run in a docker container on my hardware, so I needed hashcat-legacy.  But that had a restriction on the size of the message whose signature needed to be cracked, when using -m 1450 (HMAC-SHA256).  So I made this.

Caveats:

1. I am a noob to the code base and to hashing.  Don't trust me.
2. I barely tested this at all.  Just tried it on a few JWTs served up by WebGoat, and it helped me pass them.  So I stopped thinking about this.
3. There are probably code changes that are unnecessary
4. There are probably bugs I don't know about
5. It's still building for debug (optimizations off) because it's fast enough for me.

Thanks to the pull request from peterpt against the real hashcat-legacy repo (https://github.com/hashcat/hashcat-legacy/pull/72/files) for some fixes to the makefile to allow building.

## *Hashcat* ##

**Hashcat** is an advanced CPU-based password recovery utility for Windows 7/8/10, Apple OS X, and GNU/Linux, supporting seven unique modes of attack for over 100 optimized hashing algorithms.

### License ###

**Hashcat** is licensed under the MIT license. Refer to [docs/license.txt](docs/license.txt) for more information.

### Installation ###

Download the [latest release](https://hashcat.net/hashcat/) and unpack it in the desired location. Please remember to use `7z x` when unpacking the archive from the command line to ensure full file paths remain intact.

### Usage/Help ###

Please refer to the [Hashcat Wiki](http://hashcat.net/wiki/) and the output of `--help` for usage information and general help. A list of frequently asked questions may also be found [here](http://hashcat.net/wiki/doku.php?id=frequently_asked_questions). The [Hashcat Forums](http://hashcat.net/forum/) also contain a plethora of information.

### Building ###

Refer to [docs/BUILD.md](docs/BUILD.md) for instructions on how to build **Hashcat** from source.

### Contributing ###

Contributions are welcome and encouraged, provided your code is of sufficient quality. Before submitting a pull request, please ensure your code adheres to the following requirements:

1. Licensed under MIT license, or dedicated to public domain (BSD, GPL, etc. code is incompatible)
2. Adheres to either C89, C90, or C99 standards
3. Compiles cleanly with no warnings when compiled with `-W -Wall -std=c99`
4. Uses [Allman-style](https://en.wikipedia.org/wiki/Indent_style#Allman_style) code blocks & indentation
5. Uses 2-spaces as indentation or a tab if it's required (for example: Makefiles)
6. Uses lower-case function and variable names
7. Avoids the use of `!` and uses positive conditionals wherever possible (e.g., `if (foo == 0)` instead of `if (!foo)`, and `if (foo)` instead of `if (foo !=0)`)
8. Use code like array[index + 0] if you also need to do array[index + 1], to keep it aligned

You can use GNU Indent to help assist you with the style requirements:

```
indent -st -bad -bap -sc -bl -bli0 -ncdw -nce -cli0 -cbi0 -pcs -cs -npsl -bs -nbc -bls -blf -lp -i2 -ts2 -nut -l1024 -nbbo -fca -lc1024 -fc1
```

Your pull request should fully describe the functionality you are adding/removing or the problem you are solving. Regardless of whether your patch modifies one line or one thousand lines, you must describe what has prompted and/or motivated the change.

Solve only one problem in each pull request. If you're fixing a bug and adding a new feature, you need to make two separate pull requests. If you're fixing three bugs, you need to make three separate pull requests. If you're adding four new features, you need to make four separate pull requests. So on, and so forth.

If your patch fixes a bug, please be sure there is an [issue](https://github.com/hashcat/hashcat/issues) open for the bug before submitting a pull request. If your patch aims to improve performance or optimizes an algorithm, be sure to quantify your optimizations and document the trade-offs, and back up your claims with benchmarks and metrics.

In order to maintain the quality and integrity of the **Hashcat** source tree, all pull requests must be reviewed and signed off by at least two [board members](https://github.com/orgs/hashcat/people) before being merged. The [project lead](https://github.com/jsteube) has the ultimate authority in deciding whether to accept or reject a pull request. Do not be discouraged if your pull request is rejected!

### Happy Cracking!
