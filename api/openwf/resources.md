# OpenWF Resources

## This Working Group is currently inactive

We believe the true usefulness of OpenWF goes beyond the spec itself; it is an ecosystem of tools, documentation, and resources contributed by the community. You are encouraged to [get involved](https://github.com/KhronosGroup/Khronosdotorg)!

* [OpenWF Sample Implementations](https://www.khronos.org/registry/OpenWF/) Source codes of the OpenWF Composition and Display API sample implementations. The implementations and example applications are compilable and runnable under linux and win32/cygwin.
* [OpenWF Whitepaper](https://www.khronos.org/assets/uploads/apis/OpenWF_Whitepaper_Dec_2011.pdf) Technical whitepaper giving an introduction to the OpenWF Composition and Display APIs.

## Commercial and Open Source Implementations
* [OpenWF Sample Implementations](https://www.khronos.org/registry/OpenWF/) Source codes of the OpenWF Composition and Display API sample implementations. The implementations and example applications are compilable and runnable under linux and win32/cygwin.

## Tutorials, Technical Whitepapers and How to Guides
* [OpenWF Whitepaper](https://www.khronos.org/assets/uploads/apis/OpenWF_Whitepaper_Dec_2011.pdf) Technical whitepaper giving an introduction to the OpenWF Composition and Display APIs.

## Presentations & Videos
* [OpenWF Overview](https://www.khronos.org/assets/uploads/developers/library/overview/OpenWF-Overview_v1_0.pdf)
Embedded devices are increasingly expected to offer sophisticated user interfaces that combine rich graphics with multimedia content. Graphics and display hardware technologies have evolved to achieve these visuals with significantly higher efficiency than traditional CPUs, delivering greater performance, decreasing memory bandwidth usage and increasing battery life. Making use of this variety of hardware introduces fragmentation as software needs to be adapted to each hardware configuration.

A platform’s Hardware Abstraction Layer (HAL) for display and graphics technology allows the applications and middleware layers above to be deployed across a range of hardware without costly porting activities. OpenGL is an example of a graphics HAL that allows portable software to take advantage of a wide range of 3D hardware accelerators.

Windowing systems allow screens to be shared by multiple applications, ensuring that the graphics provided for each application’s window is sensibly merged onto the screen. This requires the graphics and display drivers to respect the intentions of the windowing system, which commonly means considerable OS-specific porting work on the part of the device manufacturer when moving to new hardware.

The OpenWF APIs provide an OS-independent and hardware-neutral foundation for building compositing systems, particularly suited to implementing windowing systems. OpenWF acts as a HAL to achieve composition of content and configuration of display devices. The interfaces are designed for use by a single user which could be a central windowing system or, in an application-specific system, may be the application itself.
