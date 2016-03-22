# SBT-JavaCPP : HAS MOVED under the [bytedeco organisation](https://github.com/bytedeco/sbt-javacpp)

Makes it easy to start playing around with JavaCPP in an SBT project.

## Usage

In your `project/plugins.sbt`:

```scala
addSbtPlugin("com.beachape" % "sbt-javacpp" % "1.3")
```

Adding the above line will set up your project's classpath to include `maven-plugins` as well as a add a dependency on
the core JavaCPP library.

To add a dependency on a JavaCPP preset in your project, the following snippet will do that for you, taking care
of adding the proper native preset for your target platform as well:

```scala
// in build.sbt

javaCppPresetLibs ++= Seq("opencv" -> "3.0.0", "ffmpeg" -> "2.8.1")

```

## Customisation

By default, this plugin will download the appropriate binaries for the platform of the computer currently
running SBT, you can modify this by setting it to another platform (for example, if you want to compile JARs to be run
on other platforms)

```scala
javaCppPlatform := "android-arm"
```

Alternatively, you can set the target platform by passing a System Property: `sbt.javacpp.platform`, which means that
you can change the target platform for your build straight from your command line.

```scala
sbt compile -Dsbt.javacpp.platform=android-arm
```

## Licence

The MIT License (MIT)

Copyright (c) 2016 by Lloyd Chan

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
