# Readme for Issue Ticket

## Description

This issue ticket describes an error encountered while running Quire preview command or any npm script command on macOS Catalina 10.15.7. The error occurs due to a symbol not found error in the `cpp.42.dylib` library of the `libvips` module, which is expected in /usr/lib/libSystem.B.dylib. The error message is as follows:


```
dyld: lazy symbol binding failed: Symbol not found: _pthread_jit_write_protect_supported_np
Referenced from: /Users/michaelkim/Desktop/my-project7/node_modules/sharp/build/Release/../.././vendor/8.13.3/darwin-x64/lib/libvips
cpp.42.dylib
Expected in: /usr/lib/libSystem.B.dylib

dyld: Symbol not found: _pthread_jit_write_protect_supported_np
Referenced from: /Users/michaelkim/Desktop/my-project7/node_modules/sharp/build/Release/../.././vendor/8.13.3/darwin-x64/lib/libvips
cpp.42.dylib
Expected in: /usr/lib/libSystem.B.dylib
```


## Version Numbers

- macOS 10.15.7
- Quire CLI 1.0.0-rc.3
- Node 16.16.0

## Expected behavior

Quire preview command and npm script should execute without any errors.

## Steps to reproduce

1. Run Quire preview command or npm run dev on macOS Catalina 10.15.7.

## Attempts to solve

From different online solutions:
- Using older versions of node and sharp may help resolve the issue
- Installed Node Version Manager library to run older versions of Node.
- Downgraded to sharp 0.31.1
- These changes did not fix problem
- Upgrading to Big Sur or newer may fix the issue

I do not completely understand but according to the apple reference link below, all the libraries in /usr/lib have moved into the shared cache in Big Sur and newer. Operating on Catalina an older system seems to be the issue.

## Attempts to solve

After researching online solutions, the following attempts were made to resolve the issue:

- Tried using older versions of Node and Sharp as suggested in a solution found online.
- Installed the Node Version Manager library to run older versions of Node, but this did not fix the problem.
- Downgraded to Sharp 0.31.1, but the issue still persisted.

<br/>

I want to note that I am new to programming and may not have prior experience with the technical concepts related to this issue. According to the reference from developer.apple, these errors may be caused by the fact that all the libraries in `/usr/lib` have been moved to the shared cache in Big Sur and newer versions of macOS. This suggests that operating on an older system like Catalina may be the cause of the issue. It's worth noting that upgrading to a newer version of macOS like Big Sur or newer may resolve the issue, as suggested by the Apple reference link provided below.

## References

Reference: [Apple Developer Forum - Discussion on missing libraries in /usr/lib on Big Sur](https://developer.apple.com/forums/thread/655588)

