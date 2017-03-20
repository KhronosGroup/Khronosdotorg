# Vulkan FAQ

This FAQ is on [Github](https://github.com/KhronosGroup/Khronosdotorg/blob/master/api/vulkan/faq.md), where we welcome pull requests.

## ToC
* [General](#general)
* [Gaming](#gaming)
* Khronos APIs:
  * [EGL](#khronos-apis-egl)
  * [glTF](#khronos-apis-gltf)
  * [OpenCL](#khronos-apis-opencl)
  * [OpenGL/GLSL](#khronos-apis-opengl-glsl)
  * [SPIR-V](#khronos-apis-spir-v)
  * [Safety Critical](#khronos-apis-safety-critical)
* [LunarG](#lunarg)
* [Mantle](#mantle)
* Support
  * [CAD](#support-cad)
  * [HLSL](#support-hlsl)
  * [Java](#support-java)
  * [Microsoft](#support-microsoft)
  * [SLI](#support-sli)
  * [Visual Studio](#support-visual-studio)
* Vendor
  * [AMD](#vendor-amd)
  * [Apple](#vendor-apple)
  * [NVIDIA](#vendor-nvidia)
* [Vulkan Conformance](#vulkan-conformance)
* [Vulkan Features](#vulkan-features)
* [Vulkan Where/How/When](#vulkan-where-how-when)
* [Web Vulkan](#web-vulkan)

## General
### In addition to cross-platform support and being open source, what else sets Vulkan apart from DirectX12?
From an external point of view, the biggest difference has to do with the platforms and the hardware that they support. DirectX12 has just a few target hardware devices that it was designed for. It only has to run on one operating system, whereas Vulkan supports hardware from 10s of companies, and supports a much broader range of platforms. There is a bit higher level of abstraction in Vulkan that accommodates increased portability with negligible cost. The abstraction is a good thing. It enables portability, while providing the same performance and usability you get from DX12.
 
### Do you have any benchmark results between Vulkan and DirectX12? (assume that everything is in same conditions except API)
Not at this point.

### Does Vulkan contain something similar to how DirectX uses Direct2D for rendering 2D shapes and fonts?
No it does not. Our initial goal in Vulkan 1.0 is to address the functionality of current GPUs and current drivers. So we have stressed the hardware capabilities as opposed to anything that you could handle through middleware. So high quality text rendering, anything involving fonts, is out of scope for this level of activity. We think it's ideal for layered implementations and layered APIs that would run on top of Vulkan.
		
## Gaming		
### Can I integrate Vulkan inside of an Unreal Engine game project?
UE4 has experimental support for Vulkan as of 4.12 for its mobile feature set on Android and Windows. It's under active development with the goal of supporting all mobile and desktop rendering features.
		
### Is Vulkan Heralding the Rise of Linux as a gaming platform?
This is a broad topic, and it is unlikely that Vulkan, in and of itself, would result in the rise of Linux as a gaming platform.
OpenGL is also a cross-platform graphics API available on Linux, and it has not yet led Linux to that status.  It is more
likely that the broad acceptance of a platform like the Steam Box would be more of a move in that direction.
		
### What is the current stance of Microsoft, Nintendo, and Sony about using Vulkan on current/future consoles?
That is entirely up to the HW vendors when they generate the newest consoles.  It is possible Vulkan could be used as it
does provide a thin graphics API which would place more optimization potential on the application itself.  However,
it is more likely that at least Microsoft would instead choose to use an optimized API based on DirectX 12 instead.
		
## Khronos APIs: EGL		

### What interaction will there be between EGL and Vulkan?
It was the EGL team that developed the WSI extensions for Vulkan.The WSI extensions are essentially the new generation EGL to Vulkan. This may be an oversimplification, but EGL is intended to play the same role for Vulkan that it plays in the OpenGL ES world. The EGL group has historically defined the context creation and Windows system interface for OpenGL ES. In Vulkan, we made a conscious decision not to separate Windows system integration from the API in quite so strict a manner. In Vulkan, Windows system integration is defined by a series of extensions to Vulkan, rather than a separate API. We've had extensive conversations with Google and Android and other platform owners in order to make sure that mechanism works well across multiple APIs including Windows. The bottom line is that there is no EGL for Vulkan, rather Windows system integration in Vulkan is handled by extensions.

## Khronos APIs: glTF		
### Will Vulkan support Khronos' glTF?
glTF is just a file format for transmission of 3D assets across the network, typically into a web-based application, often used in WebGL. Yes, if you have an application that's using WebGL or Vulkan, there's nothing too specific about glTF that would mean you couldn't use it together.

## Khronos APIs: OpenCL		
### How do I choose between using Vulkan and OpenCL when doing general computing?
If your application is interacting with graphics and displaying your results, then doing it all in Vulkan is probably easier and more suitable. But if it's a more scientific computing kind of application, then OpenCL is more appropriate. OpenCL has a lot more focus on things like type precision requirements than Vulkan does with its foundation being in graphics.
		
### Are there any plans on Vulkan and OpenCL interoperability?
The OpenCL working group has started to discuss Vulkan interoperability, but we don't have it yet. And we have interop with OpenGL and Direct-X, so interop with Vulkan would make perfect sense.
	
## Khronos APIs: OpenGL/GLSL		
### Can OpenGL be developed as a layer on top of Vulkan?
It is certainly feasible. There are rumors of projects for running OpenGL on top of Vulkan, but we don't have any direct knowledge of them. This would have all of the issues that writing an OpenGL driver straight to the metal would have in accessing all the hardware features. If you wanted to get comparable performance, you can do it because Vulkan is that level, but you would be signing up for duplicating all that cleverness that has evolved inside the major IHVs over the years.
		
### As a beginner, is it better to learn OpenGL before Vulkan?
If you're really new to 3D graphics, OpenGL, or one of the traditional APIs, is the best place to start learning and not get totally swamped by all the details that you need to drive Vulkan. The interesting thing is over time, the middleware layer could evolve to potentially provide some interesting learning platforms over time. Right now, if you are starting from scratch, start with OpenGL.
		
### What performance improvements might a well-tuned OpenGL application for games / simulation expect with a switch to Vulkan?
If your application is well-tuned and is GPU-bound at present, you'll perhaps notice some reduction in CPU power. The CPU may be idle more often, but you're not going to get a graphics difference, because the pipeline is the pipeline. If it's maxed out now, it will be maxed out in Vulkan. But you might expect to get many of your CPU cycles back, so you may have the opportunity to enhance your rendering using some offline sort of CPU techniques. You may get more out of that if you choose to give back some of that. If you are happy that you're using less power and your CPU is idle more of the time, that's great, but you may choose to add some techniques back in outside the rendering pipeline, so that you can still get better results, but you're doing it in a combination of CPU and GPU work.  Vulkan also supports multi-threaded rendering so this feature will enable an application or game to parallelize across several threads what used to be done on a single rendering thread (command buffer construction and submission).
		
### Are shaders in Vulkan written in the same way as in OpenGL or GLSL?
In OpenGL, the only choice for writing shaders is to use GLSL, and pass the GLSL into the driver at runtime. In Vulkan, you can also write in GLSL, and use an offline tool chain to translate that to SPIR-V. (Standard Vulkan only accepts SPIR-V). There are plenty of other choices, and there will likely be lots of people experimenting with different languages and different kinds of tool chains, middleware, and game engines as a variety of ways of generating the SPIR-V that goes into the driver. So you can do it the way it works for OpenGL, or you can experiment with the new and different ways. Some of those can be linked directly into an application, so you don't have to rely solely on offline support. We usually call it off-driver support, but you could do it online by using a side tool real-time. It just isn't part of the core Vulkan drivers stack.
		
### Will we be able to mix OpenGL rendering with Vulkan rendering?
Nvidia at least has mixed OpenGL and Vulkan rendering and has published the extension that allows this. One of our first extensions is a pretty limited form of interop where you can synchronize between an OpenGL context and a Vulkan queue, and additionally copy image content from Vulkan to OpenGL. Interop is certainly a technical possibility, and I expect we'll probably have additional extensions in the future.
		
### What about proper text support (high quaility LCD) that is lacking in OpenGL?
Our initial goal in Vulkan 1.0 is to address the functionality of current GPUs and current drivers. So we have stressed the hardware capabilities as opposed to anything that you could handle through middleware. So high quality text rendering, anything involving fonts, is out of scope for this level of activity. We think it's ideal for layered implementations and layered APIs that would run on top of Vulkan.
		
### Can OpenGL functions be used with the Vulkan API?
The short answer is no. For all the hidden state that is being carried around by OpenGL implementations to interact with the very explicit exposed ... to Vulkan is a pretty normally technical problem. There are extensions that allow this by explicitly passing surfaces between one side and the other, and otherwise maintaining them as pretty independent entities. You can use GL and Vulkan in the same application and without interop you could render to different surfaces with GL and Vulkan, but you would need an extension to mix rendering. You can certainly use both of them in the same process. You can use them independently. It's sharing data or sharing state between them, that requires an extension to one or both APIs. Although, for multi-window applications, there is no real problem.
		
### Will GLSL be the standard shading language for Vulkan?
Vulkan contains no normative reference to any high level language specification. The only thing that a Vulkan implementation requires is the ability to accept shaders in the SPIR-V format. We have defined for the convenience of the developers, an extension to GLSL to allow it to generate Vulkan compatible SPIR-V (9:40) but we pose no barrier, we intend to encourage other mechanisms of generating valid SPIR-V. The SDK is a set of tools which you can use to validate whether a SPIR-V program is legal for Vulkan and should be accepted by a Vulkan implementation. We strongly encourage developers to develop their own language ports or their own tools such as graphic tools, graphical tools such as the SDK to generate languages using other high level formalisms.

## Khronos APIs: SPIR-V		
### Isn't glslang an official GLSL to SPIR-V compiler?
GLSlang is what we are all using and are hoping will be the standard, although the community is of course welcome to build on that. It's an open source project, and it implements the new version of GLSL that supports the Vulkan features. Under the GitHub Khronos group folder, there is a GLSlang repository. It's the official reference Khronos validation layer to validate that the GLSL you're using to conforms to the specification. That has on it an example translator from GLSL to SPIR-V. Right now it's probably abut 90% complete. The push constants and descriptor sets and input passers, a few things like that are new to Vulkan, and there are some features present that are not in Vulkan and that GLSL won't support when you're compiling for Vulkan. That tool is available. You can translate or modify it for Vulkan GLSL into SPIR-V. Then send that into the drivers for the different platform. Everybody is welcome to contribute to that project. The lead author og GLSLang, John Kesinich, is an active member of the working group and he is also the editor of the GLSL specification. We endorse his compiler. We don’t guarantee that it is bug free, but we do guarantee that we will expend effort to fix it if there are issues. You are certainly allowed to create your own GLSL/SPIR-V compiler, but we would rather fix the bugs in ours if you’re aware of any.
		
### Will there be a SPIR-V layer to allow running DirectX over Vulkan?
That is certainly a technical possibility. The issue there would be to translate Direct-X shade of code that is post-compiled code into SPIR-V for consumption. The other option of course is to compile direct form the HLSL, if that's how you're generating your binary blobs, which I think would be typical in the more modern Direct-X APIs. Either path will work. Khronos isn't planning to do that work, but if that is the best path for your engine, we hope you've got all the tools, and if not, let us know.
		
### Does the SPIR-V specification guarantee that precompiled SPIR-V objects will run on all Vulkan targets, regardless of the hardware vendor without having to tweak shaders for each HW platform they are targeting?
That is our most profound hope, for the SPIR-V and Vulkan relationship. We are very aware of the pain that the compiler differences have caused in the OpenGL and OpenGL ES environment. We’ve written the most rigorous specification we know how to write for SPIR-V, and we ask that you report any issues. The one caveat is that Vulkan does not specify error behaviour. If you write a SPIR-V shader which does not follow the SPIR-V specification, we are not responsible for what different implementations may do with it. We do provide a SPIR-V validator and if your SPIR-V passes that validator and behaves differently on different implementations we want to know about it. We will conformance test it and we will fix it. There are capabilities in SPIR-V which are basically feature capability support bits, and so if you have a shader which works on one implementation that supports some capabilities and you run it on an implementation which does not support those capabilities, then obviously, that’s not going to work. But otherwise we do sincerely hope that things are portable and that there are less implementation variation in SPIR-V consumers than there has been in GSL compilers.

## Khronos APIs: Safety Critical		
### Is Vulkan ready to be used for safety critical applications ?
That's coming, and Vukan is a much more transparent API. But I wouldn't call the current draft of drivers mature. It's a positive for safety critical systems, but obviously in a safety critical environment you're going to need to move slowly and do a lot of testing closely with the platforms that you intend to target. We have a conformance test, but it is not yet rock solid and it does not have 100% coverage. We are improving it as fast as we can, but right now, I would say it's time to be planning and developing, but not fielding. Specifically regarding ISO 26262 certification, there is quite a lot of activity inside Khronos about building safety certified versions of the various APIs. We have OpenGL SC, which is a safety certifiable version of OpenGL ES, but there is no current safety certified spec for Vulkan. Although now that the Vulkan 1.0 spec is out, I think that discussion will gain more momentum inside Khronos.

## LunarG		
### Is Vulkan intended to be used with specific SDKs only ? Can it be used without the Vulkan SDK from LunarG?
If individuals don't want to use the SDK, they could go find the different elements, which are open source and free from multiple repositories, then build it in and compile it together. Bringing it together in one place, binaries already built, and providing a forum where questions can be asked is the benefit of getting the SDK from LunarXchange (vulkan.lunarg.com). 
		
### Do any of the current SDKs include a Vulkan emulator?
Not that we are aware of.
		
### If you are mixing the use of Vulkan and OpenGL within an application, I assume the debug and validation tools in LunarG only give you information from the Vulkan API and layers?
Yes. The LunarG SDK is for the Vulkan API only.
		
### I noticed out-of-the-box the samples in LunarG SDK do not run (Samples can't find the driver).
Most likely you did not have a driver installed on your system that supported Vulkan.

### What versions of Linux are supported by the LunarG SDK?
At the time of public launch, the LunarG SDK supported Ubuntu versions 14.04 and 15.10. As time goes on, future releases of the SDK are validated on the two latest Ubuntu LTS releases. The LunarG Vulkan SDK for Linux is a self-extracting installer. The installer will create a local SDK directory of the form VulkanSDK/<version> in the current working directory. Starting with version 1.0.13.0, the installer will no longer copy the Vulkan development and runtime headers, libraries, and binaries to system locations. See the Linux Getting Started Guide included in the LunarG Linux SDK for more information.

### I'm using Ubuntu with Intel GPU. Which LunarG SDK or Intel Mesa driver should I use?
At the time of public launch, the LunarG SDK supported Ubuntu versions 14.04 and 15.10. As time goes on, future releases of the SDK are validated on the two latest Ubuntu LTS releases. There is a curated list with links to drivers on the [Khronos Website][3].
		
### What is the relationship of LunarG to Khronos?
LunarG is an independent software company being sponsored by Valve to help build out the Ecosystem for the Vulkan API. Hence LunarG is a Valve representative in the Khronos Vulkan Working Group.
		
### With OpenGL, we had helper APIs like GLUT, then FREEGLUT, and GLEW. Is the Lunar SDK intended to serve as that common front end for OS dependencies, or what?
The LunarG SDK provides the critical and canonical Vulkan API Loader and Validation Layers. In addition, it provides sample code as examples, and other tools such as RenderDoc, vktrace/vkreplay. For more information about what is in the SDK, you can download it for free from the [LunarXchange][1]. You can also see an overview in the [LunarG Vulkan SDK][2]
		
## Mantle		
### How is Vulkan similar to Mantle -- what are the differences?
The impact of AMD's stepping forward and providing Mantle as a place to start was huge for the Vulkan working group. We probably would not be where we are today without them and we take off our hats to them (and their lawyers) for being willing to make that happen. The original proposal for Vulkan was basically a cleaned-up version of Mantle. AMD got the conversation really going, but over an 18-month period there have been contributions from a lot of the other members at Khronos as well. Some were small tweaks, and some really major features: render pass was never in Mantle, for example, yet it's a core part of Vulkan now. So there's an obvious heritage there, and if you have an experience with Mantle, I don't think you would have any trouble at all moving to Vulkan. Some of the API names are the same, and it's lived on there, but it is a significant update. There are some very significant differences and enhancements, and it's cross-vendor, cross-platform, so ... I think we've landed in a really good place. Overall Vulkan is truly a better API.
		
## Support: CAD		
### Does Khronos have any CAD-oriented partners who are going to adopt Vulkan for their applications?
There's quite a lot of interest in the professional design community in Vulkan. We talk a lot about games, but Vulkan of course is not designed just for games. Any application that is CPU bound can benefit from Vulkan. For example, a high-end CAD application with a model with hundreds of millions of polygons, very often is CPU-bound and Vulkan can help there. But of course the dynamics in the professional industry are different. In the professional authoring industry, there's a lot more legacy code and that's why it's important that OpenGL is not going away, so the professional applications will not be left stranded. But if they want to migrate to Vulkan to take advantage of things like the multi-threading for large model interactivity, that is the kind of application that Vulkan is designed to enable.
		
## Support: HLSL		
### Is an official HLSL -> SPIR-V translator planned?
The working group does not have any high-level language projects under development, except for ongoing support of the GLSlang Compiler. We are aware of people in the community, of course, who have pretty large tool chains around HLSL, and we expect those things to show up. It probably won't come through Khronos.
		
## Support: Java		
### Could Vulkan be used with Java in the future?
There is no barrier to it. We defined a C language binding and anyone is welcome to create bindings from that to other languages. That’s happened quite a lot with OpenCL, and so if history is a guide then that is probably likely to happen. Even using Java as a shading language, a kernel language in OpenCL’s case, a Java-to-SPIR-V compiler, there are actually open source examples already. This is the first time that any of the OpenGL family of languages have ever attempted to present specifications or large software components as projects.
		
## Support: Microsoft		
### I don't see Microsoft involved, does that mean that will oppose it or at least persist with Direct3D? Will it even run on Windows?
Microsoft has not expressed any intent to support Vulkan any more than they have had token support of OpenGL over the past few years. There are well defined mechanisms by which IHVs can ship a Vulkan driver on any version of Windows. There's a loader that works on any version of Windows. But it will be as it is the case now with OpenGL: it will be up to an application that is installed that requires Vulkan to negotiate with the implementation to install an appropriate Vulkan driver for the hardware that is on the machine. Vendors are enabled to ship drivers for whichever API they wish and Vulkan drivers are already shipping from multiple hardware vendors for multiple versions of Windows. Right now, we have Windows out there from the hardware vendors, everything from windows 7 up to windows 10. So even in the Windows ecosystem, Vulkan is available on all versions of Windows on DirectX12, so there is potentially some value to the developer community to having a single API that spans multiple Windows versions.
		
### Will the raspberry pi 2 have Vulkan support? Or the next Pi?
Broadcom is a Khronos member and an active participant in the Vulkan working group, but the Raspberry Pi Foundation itself is not. Our old friend Esben, who is the Godfather of Raspberry Pi was a member of the working group, back in the day, but we haven't heard from him for a while in an official capacity. We do expect Vulkan to appear in quite small embedded systems in general, so it's certainly possible. Vulkan support is equivalent to OpenGL ES 3.1, so any hardware that supports that should be capable of supporting Vulkan. Current shipping versions of Raspberry Pi are not ES3.1 capable, but as Broadcom is deeply involved and their GPU driver engineers are involved. They are very aware of the Vulkan spec and they have approved it.
		
## Support: SLI		
### Is SLI supported?
There’s no direct support for SLI or alternate frame rendering the API currently that we're aware of. Multi-GPU support of many kinds is a very high priority, we’re very aware of the lack in Vulkan 1.0. It will require either a large extension or a new version to address properly, we are very aware of the need and we are very interested in solving it.
		
## Support: Visual Studio		
### Are there solution or cmake files for building the source for Visual Studio and/or other compilers?
"The various Vulkan source projects run by either Khronos or LunarG currently support generation of build tools using
CMake.  On Windows, the only officially supported compiler at this time is Visual Studio 2013 (although Visual Studio
2015 can also be used with some restrictions)."
		
## Vendor: AMD		
### Is there an ETA for AMD to pass conformance tests and share proper drivers?
The driver AMD posted today [Feb 18, 2016] is beta and has not passed the conformance test yet. We have a few things tried out. It's literally in our internal drivers and down to a single digit number of issues out of somewhere in the region of 40,000 tests in the suite. We're preparing our logs, and our first non-beta driver with a WHQL test, then we'll be conformant, or at least have the logs posted and be waiting the committee's decision.
		
## Vendor: Apple		
### Will Apple will support Vulkan? (OS X and iOS)
Apple is a member of Khronos and they actually are on the board, and they're active in several of our APIs, but they have not publicly stated any support for Vulkan at this point. It does look like they seem to be mainly focused on Metal right now. From Khronos' point of view, there is no barrier to any OS platform adopting Vulkan and Apple, just like anyone else, will be more than welcome to adopt.
		
## Vendor: NVIDIA		
### Will Vulkan have an interoperability with CUDA?
Vulkan have an interoperability with CUDA will likely happen eventually, but I don't think NVIDIA has something in the works in the short-term.
		
### I see NVIDIA has started a C++ interface to Vulkan which is C. Is this intended to be a standard for Vulkan C++ developers?
This is something that some folks from NVIDIA have put out there and I don't know if it's the first, but I'm sure it wont be the last.We all hope to see lots of these ecosystem contributions showing up soon. The Vulkan working group has tried very hard not to be too ambitious and not to claim any of the high level space. Compare that to the OpenGL space where the driver ranges from very close to the hardware up to a quite high level of abstraction. In Vulkan, we’re doing our best not to dictate those solutions to the community but to let the community decide what it needs and tell us. The NVIDIA project is a great example of the kinds of things we encourage everyone to try. It's not an official khronos project, if it turns out to be widely adopted and widely used, we will do our best to support it. If you have other ideas for the right way to integrate C++ shaders or C++ bindings for the APIs we look forward to your contributions and encourage them. This is the kind of thing that we would hope to see from the community at large -- that the people find, or people create these layers that they believe will be good for developer productivity and make them open sourced and get contributions from the community and just really see what takes off.
		
### Is NVIDIA going to add Vulkan driver support for: GeForce 500 and 800 series GPUs, Fermi, GRID SDK, Jetson TK1, NSight, GTX480
We're currently not planning to support Vulkan on [???]Class GPUs, though it's not an engineering issue: it's an install based issue. So if that causes you pain, please consult your local NVIDIA representative now.
		
## Vulkan conformance		
### How exactly is a conformance test run?
That's an interesting side effect of the way that we're doing conformance, which is quite different from the traditional OpenGL way of doing it. We do not have a mechanism for removing conformance certification from a device, and the rule is if you have in good faith designed a device to pass conformance, then you get to call yourself conformant. One of the reasons we're excited about having the conformance test out in public, though, is that as it evolves, community members can run it. They can ... I don't want to say name and shame, but they can name and perhaps register issues. We hope that will have multiple good effects. One is it will encourage all implementers to be much more aggressive about updating, so that they maintain conformance, and that conformance is visible to the community. The other, of course, is that the conformance tests can evolve more rapidly, and just make the API more reliable.
		
## Vulkan features		
### I understand the benefit of command creation on multiple threads. Is there any benefit to having command submission on multiple threads? Or will a typical program still use the main thread to do submission?
If you have multiple queues, I think it might make sense to submit work to each of the queues from different threads. The queues themselves, you would need to serialize on a single queue, so if you had multiple threads submitting to a single queue, you could do it if it's convenient in your app. If you just have multiple threads that you want to submit, obviously the synchronization is your problem. There's probably no real benefit to doing that at all. It's a design intent of Vulkan that submit is supposed to be very cheap. The heavy lifting is supposed to be done at command buffer construction time, so the expected model for a given render target is to mult thread the command buffer construction like crazy, but then if you marshal all of those and have a single thread submit them, that's not going to hurt you. It's not going to be the top pull. Also, If an application remains single threaded, you can still expect CPU performance improvements and the stuttering improvements and so on that Vulkan offers, so going multi thread it is not a requirement to reap the benefits of Vulkan.
		
### What is the desktop GPU's hardware support for render passes (considering DX12 doesn't have this concept)?
During development we were a bit concerned about whether desktop GPUs would make use of them on desktop GPUs. During the implementation of our drivers, I realized that there are a few optimizations that we can make, a given knowledge of the structure of the frame, so ... it is a feature that was strongly requested by our mobile members, but I think that if you used them wisely, then there are certainly things there that desktop GPUs can take advantage of. It's not a mobile-only feature. There is opportunity there for desktop as well.
		
### Is a shader debugging tool for Vulkan available?
If you look out in the web, you'll see there are people working on a shader debugger. The problem, of course, is that the holy grail of symbolic debugging of shaders in high-level language is unsolved in OpenGL, and it's going to continue to be very difficult, perhaps even more difficult in the new world, where the high-level language compiler is further decoupled from the driver. There are obviously debugging features in the LunarG SDK and in the layers, but they are more at the level similar to the debug functionality that you get with debug expansions and OpenGL. In terms of a traditional, symbolic debugger such as what you might use with a C++ or C program, the Vulkan working group is not working on any such thing. Such a tool would require very close cooperation with a hardware vendor. We don’t intend to do it but some hardware vendors may provide that capability. There are excellent debugging capabilities provided by tools such as the LunarG SDK and we look forward to other products from the community. In particular, the RenderDoc that is included in the SDK would be the best tool currently available for it.
		
### Can Vulkan be used for headless rendering? Does Vulkan support stereoscopic rendering?
Multi view is on the agenda for future work, which would include stereoscopic as an important special case. Headless rendering, definitely. Vulkan natively doesn't even have WSI built into it: that's an extension. The integration with the Window system is much cleaner with Vulkan than OpenGL. If you don't need to render anything, then you don't have to concern yourself about getting a display service in your context. It is much better partitioned and if you do use the WSI extension, the swap buffer architecture there is mostly low-level and explicit, just like the rest of Vulkan. It's a cleaner and more flexible Windows system integration that is also common across platforms.
		
### How does the Vulkan loader detect vendor drivers in a Linux system?
On Linux, the loader detects the drivers via a JSON file that's installed in some system communications. The JSON file indicates where the actual driver library is. There are also some environment variable overrides that you can use to point to a different location rather than a system location.
		
### How much platform-dependent code is needed to write a Vulkan application?
The core Vulkan specification has no platform dependencies whatsoever. We have brought Windows system integration closer to the core in the sense that windows system integration is now a core extension rather than a separate API. The WSI, for instance, on Windows vs. Linux is mostly the same extension. There would be some difference there, but a lot would be the same calls.
		
### What is Vulkan's performance with ray tracing and other needs in CGI film-making?
The fundamental pipeline model underlying Vulkan is essentially exactly the OpenGL model. Anything you do through the rasterization side is traditional rasterization. You certainly can use the compute shader capability to write a ray tracer just as you could have done with compute shaders in GL. Maybe Apple has a little more flexibility, but there's no explicit support.
		
### What antialiasing modes are available?
The Vulkan header file defines multi-sampling modes. Multi-sampling is the basic answer, We have multi-sampling modes up to 64x but we have not defined sampling patterns for 64. We do not have anything comparable to TIR in the Windows space. That would be for a future version. We are considering those options but we haven't done anything for that yet. Multi sampling is the basic mode. We do not have super sampling formally supported, but we have per-sample shading which is similar. So the Vulkan spec allows implementors to expose multi sampling and super sampling directly. We require every implementation to support 4x multi sampling. I'm not sure what other requirements we impose and we don't have anything more complex that that at this time
		
### Will Vulkan extensions that get used a lot eventually get added into core vulkan?
The Vulkan working group is very interested in your input. If you see an extension that is of intense interest, giving us notice on our public Github platform is a good way to show your interest. Its very early days, the specs have only been out a week. The short answer is yes, the long answer is yes but please give us more input about what you need. We'll prototype a new hardware functionality as extensions and absorb it over time.
		
### Talk about WebGL and Vulkan.
The WebGL working group is beginning to think what Vulkan impact is going to be. There’s no decisions yet, but the current discussions are heading in a direction that WebGL would begin to absorb some of the Vulkan functionality where it becomes appropriate for the web and that functionality becomes pervasively available. So WebGL has an interesting place in ecosystems because it has to run everywhere and on multiple platforms. So if Vulkan isn't there, we have to be sure that WebGL can still run on that platform. But that's not a totally new problem for WebGL, because there is the Angle project where you can run WebGL, over DirectX as well as OpenGL, so there are similar kinds of solutions that will enable us over time to help WebGL take advantage of Vulkan functionality without losing backwards compatibility. There are no decisions yet, but it is an active discussion inside the WebGL working group.
		
### Does Vulkan support multiple GPUs? Is there any native Vulkan support for multiple GPU acceleration?
There is no multi GPU support in version 1.0. That was unfortunately a feature we had to cut in order to preserve our schedule. We do expect it to be near the top of the list for stuff we address in Vulkan 1.1. It is perfectly possible for a Vulkan implementation to expose multiple GPUs. What we cannot currently do is allow resource sharing between them. So from a point of view of, for example, a windows system manager, its perfectly possible to recognise that I have multiple ways to render to a surface and then can use operating system hooks to transfer that to the screen. What we don't have is the ability to share a texture or a render target between multiple GPUs. We expect to add that in the next version, it’s a high priority but we don't have that today.
		
### Can 2D graphics be done in Vulkan?
Vulkan is a very low-level API. If your GPU is capable of it, you can draw with it. At the moment it exposes pretty much the set of primitives that core OpenGL does, so if you're talking about drawing lines and screen-line, co-ads, and things like that, sure. If IHVs have support for real, actual hardware that accelerates 2D better than you could do it with a 3D engine, then I'm sure those things will probably show up as extensions, and I expect on not too distant future.
		
### What about Vulkan enables good performance on mobile GPUs as well as the desktop?
Vulkan is unique among modern APIs in terms of treating mobile and desktop equally. It is possible to write paths in a Vulkan application which will suffer no penalty on a desktop architecture but will equally exploit all the capabilities which are offered by a mobile architecture. This is primarily through the render paths and the command buffer structure of the API.
		
### Would Vulkan be directed towards web rendering and have bindings for JS etc?
We are not aware of any particular deep interest in developing direct Vulkan bindings from Javascript. There is no barrier to it, we certainly wont stop it, but Khronos is not working on it. Also, it is considered in the design of Vulkan that not so much Javascript bindings, but more the question of the WebGL working group, many of whose members are also in Vulkan's, we did consider the needs of a broswer. One of the features of Vulkan is that support for optium robustness is a required feature, all implementations must support it and that is there specifically to support among other things, writing Vulkan back-ends to browser for any 3D API such 3.js or WebGL.
		
### What are some of the reasons behind making the WSI KHR extensions?
We are very aware of the interface problems that were created between the OpenGL family APIs and platform APIs due to the fact that we delegated windows system integration to external forces. We made a conscious decision in Vulkan that we would bring these things to the surface so the Vulkan loader is very visible and explicit and endorsed by the whole working group. Our hope is that by claiming explicity that solving platform integration is part of our problem which we have to solve, as opposed to OpenGL which says it's someone else’s problem. We have presented the best solution that we are aware of based on variations of the kinds of things people have done with OpenGL in the past. If you’re not happy with it, we have projects on Github that we encourage you to post issues to and complain about things that don't work. Point out issues and we will do our best to address them over time.
		
### Does Vulkan use hardware-specific extensions?
Yes, and that's important because that's one of the innovation factors. It lets people experiment quickly at their own pace.
		
### Does Vulkan offer anything to an application model that is limited to a single thread?
You should not underestimate the impact of the fact that once your application is debugged, the driver has no native checking. The only validation it does is that it absolutely does, has to do to pass, to pack driver structured ... data structures. The other is that because it strongly encourages/requires you to build things ahead of time, the driver doesn't have to make guesses about your intent at one time. That also has a huge impact, because the driver is doing much less dynamic resource tracking and checking. You will still get a significant improvement in performance, unless you are GPU limited already. In OpenGL, something might happen deferred and it surprises you, so Vulkan improves on that. That's really important for real-world applications. In the OpenGL development cycle, time is spent on dealing with driver variation, and with hitching, and just quirks of individual drivers, and if Vulkan smooths over a lot of that, which we hope and expect it to, then in the long-term Vulkan can actually be a more productive API to develop on than OpenGL. Kind of for initially writing or reporting an application, there is more code to write for Vulkan than for OpenGL, but in terms of a big application, the overall effort could still be less for Vulkan.

## Vulkan Where/How/When

### When I heard of Vulkan I thought of Spock. Why Vulkan?
Vulkan was originally based off of a now defunct AMD graphics API called Mantle (named after the layer in the Earth's crust).  The logo of Mantle was an erupting volcano.  Vulkan is named after the Roman god of the same name who was thought to be responsible for volcanoes.

### Why the name Vulkan instead of nextGL? Just curious.
This was in part due to the fact that Vulkan is a different API and has no backwards compatibility with existing GL applications, which the name GLnext/nextGL may imply.

### Will the upcoming Vulkan Programming Guide be more of a reference or a tutorial?
One observation about Vulkan is that you can use it in a wide variety of ways. We are concerned that it may be used incorrectly by developers who are used to an API that is more normative and gives you more advice about how to use it. So the intent of the programmer’s guide is to identify best practices. For example, Vulkan places responsibility for memory allocation in the hands of the application for the most part. We’re somewhat afraid that many developers will be tempted to say, "I need to make a texture so I will create a texture and then I will allocate some memory and then I will attach the memory to the texture." We intend a much richer and more complex interaction. For example, we might expect an application to make a small number of large memory allocations and to suballocate memory for that individual object. That is exactly what an OpenGL driver does when you use it. In the case of Vulkan, we expect the application to do that work because we think the application has more information about what’s appropriate.

## Web Vulkan		
### How can Vulkan be used to create web applications? Will there be a WebVulkan?
Vulkan's and WebGL's design goals are somewhat different. The primary goal of WebGL is to enable portable, secure, and high-performance applications. Vulkan's primary goal is to expose all of the mechanism of the GPU to the developer to achieve the highest possible performance. Vulkan does incorporate key features in the core API, like robustness, which are essential for ultimately providing a secure and performant API on top of it. However, the feeling of the WebGL and Vulkan working groups is Vulkan is too low-level to expose directly to the web in its raw form.

That having been said, both working groups also recognize that it is essential to provide the radical performance gains offered by Vulkan to WebGL developers. Key features in Vulkan like pre-validation of pipeline states enable tremendous improvements in draw call performance, since validation is done once ahead of time, rather than during each draw call. This is a structural improvement that's easiest to deliver if built on top of an API like Vulkan rather than OpenGL or OpenGL ES.

The working groups' current plan is that a future version of WebGL will build on top of Vulkan, and aim to provide a low level API in its style, without exposing all of its mechanism, and still delivering the majority of the possible performance gains, while making security and portability the top priorities.

[1]: https://vulkan.lunarg.com
[2]: https://lunarg.com/vulkan-sdk
[3]: https://www.khronos.org/vulkan/
