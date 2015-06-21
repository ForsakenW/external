# external

Some external dependencies required by Forsaken.

Forsaken requires the [DirectX](https://en.wikipedia.org/wiki/DirectX) SDK, which is included with recent versions of Visual Studio.
The original code base was built against DirectX 6, which shipped in 1998.
Current versions of Visual Studio include the Windows SDK, which now includes the DirectX SDK.
However, two dependencies of Forsaken have since been [deprecated](http://blogs.msdn.com/b/chuckw/archive/2012/08/22/directx-sdk-s-of-a-certain-age.aspx): [DirectInput](https://en.wikipedia.org/wiki/DirectInput) and [DirectPlay](https://en.wikipedia.org/wiki/DirectPlay).
These dependencies were discontinued in 2007 and are no longer included in the DirectX SDK.

DirectInput continues to be supported, but is now part of the Windows SDK.
Although dinput.h is included, only dinput8.lib is provided.
This means that DirectInputCreate is no longer supported and DirectInput8Create must be used.

DirectPlay is no longer provided.
To build Forsaken, you have two options.
First, you can download the last version of the DirectX 9 SDK, from 2007, which includes the headers and libraries.
Second, you can use this repository.

To use this repo, clone it to your local system next to your forsaken directory.
The ProjectX.vcxproj file includes a reference to the external project, in case it is available.
Your directory layout should look like this:

```
...\parent
       \forsaken
           ProjectX
           skeleton
       \external
           \include
           \lib
```
