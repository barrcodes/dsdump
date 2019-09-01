## dsdump 
An improved nm + objc/swift class-dump

[![img](media/vmmap.png)](https://store.raywenderlich.com/products/advanced-apple-debugging-and-reverse-engineering)


### man

<!--man_start--->
```
dsdump(1)                 BSD General Commands Manual                dsdump(1)

NAME
     dsdump -- An improved nm + objc/swift class-dump

SYNOPSIS
     dsdump [option...] file

DESCRIPTION
     Provides an "nm-improved" experience when working with Mach-O executables
     and can display C, Objective-C and Swift information

OPTIONS
     -c, --color
             Adds color to output

     -a, --arch architecture
             Specify the arichtecture if file is FAT. Understands x86_64h,
             x86_64, arm64, arm64e

     -u, --undefined
             Only display undefined (externally referenced) symbols or classes

     -U, --defined
             Only display defined (internally implemented) symbols or classes

     -v, --verbose
             Specifies the verbosity level. The -v option can be used multiple
             times, while the long argument sets the exact level 0-5. Kind of
             like codesign(1)'s verbosity that everyone complains about...

     --objc  Dump the Objective-C classes

     --swift
             Dump the Swift type descriptors (classes, structs, enums)

     -h, --help
             Print out this beautiful, helpful document

EXAMPLES
     List the Objective-C internal and external classes called and implemented
     by vmmap:
           dsdump --objc $(which vmmap)

     List the Objective-C external classes called by vmmap:
           dsdump --objc $(which vmmap) -u

     List the Objective-C internal classes implemented by vmmap:
           dsdump --objc $(which vmmap) -U

     Thoroughly dump the Swift content in color in the Console app
           dsdump --swift
           /Applications/Utilities/Console.app/Contents/MacOS/Console -cvvvv

ENVIRONMENT
     DSCOLOR
             Enables color. Alternatively, use -c

     ARCH <arch>
             Specify the architecture if inspecting a FAT executable, Alterna-
             tively use --arch oioiuoiu

SEE ALSO
     nm(1), objdump(1), vmmap(1)

AUTHORS
     Derek Selander @LOLgrep

Darwin                          August 30, 2019                         Darwin
```
<!--man_stop--->


Compiled SHA1
```
SHA1: fda640f8220276bcbfdd8deab91866a57ff7d8d5
```

### Credits

* [https://opensource.apple.com/source/dyld/dyld-635.2/src/dyldInitialization.cpp.auto.html](https://opensource.apple.com/source/dyld/dyld-635.2/src/dyldInitialization.cpp.auto.html) Specifically the THREADED code for ARM64e
* [https://opensource.apple.com/source/objc4/](https://opensource.apple.com/source/objc4/) Specifically, the objc_class swift_class structs (and all the property, protocol, method, ivar, etc structs)
* [https://github.com/apple/swift](https://github.com/apple/swift) 
