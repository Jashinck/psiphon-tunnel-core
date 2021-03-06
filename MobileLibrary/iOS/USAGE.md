# Using the Psiphon iOS Library

## Overview

Psiphon Library for iOS enables you to easily embed Psiphon in your iOS app.
You can then tunnel requests through Psiphon, ensuring that your app can't be
blocked by censors.

The Psiphon Library is available as a `.framework` that can be easily included
in your project using these instructions.

## Using the Library in your App

**First step:** Review the sample app, located under `SampleApps`.
This code is a canonical guide for integrating the Library.

**Second step:** Review the comments in [`PsiphonTunnel.h`](PsiphonTunnel/PsiphonTunnel/PsiphonTunnel.h). They describe the interface and delegate requirements.

### Setting up your project

1. Get the latest iOS release from the project's [Releases](https://github.com/Psiphon-Labs/psiphon-tunnel-core/releases) page.

2. Add `PsiphonTunnel.framework` to project (drag into project tree).

3. In the "General" settings for the target, set "Deployment Target" to 9.3.

4. In the "Build Settings" for the target, under "Build Options", set "Enable Bitcode" to "No".

5. In the "Build Settings" for the target, click the `+` at the top, then "Add User-Defined Setting". Name the new setting `STRIP_BITCODE_FROM_COPIED_FILES` and set it to `NO`.

6. In target Build Phases, add a "Copy Files" phase. Set "Destination" to "Frameworks". Add `PsiphonTunnel.framework` to the list. Ensure "Code Sign on Copy" is checked.

## Compiling and testing

Only phone targets are compiled into the Library, so you must compile for and test on an actual device. If you don't do this, you'll get a linker error that says "missing required architecture x86_64 in file".
