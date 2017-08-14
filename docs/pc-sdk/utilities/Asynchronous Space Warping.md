
### Asynchronous Space Warping

<br>

#### Introduction

Asynchronous Space Warping (ASW) is a frame-rate smoothing technology that is able to track the animation and movement within the scene and generates extrapolated frames from previous frames generated by the VR application accordingly. ASW is automatic and enabled in Hypereal VR Runtime without any additional effort from developers.

#### ASW vs. ATW

ASW sounds a bit like ATW (Asynchronous Time Warping) since ATW is capable of generating new frames from previous frames to smooth VR experience as well. The difference is ATW can only track the user's head rotation while ASW goes beyond this and tracks animation and movement within the scene, which including character movement, camera movement, touch controller movement, and the player's own positional movement.

ASW is not conflicting with ATW, actually ASW is building on top of ATW where ASW is responsible for movement tracking and ATW is responsible for head rotation tracking. By combining ASW and ATW together, we are able to smooth over the whole VR experience, not only for static scene but also for the scenes with animation and movement.

#### ASW Benefits

With ASW, even the application rendering speed falls behind the display's refresh rate, the VR experience typically remains smooth and enjoyable, which allows us to reduce the system hardware requirement while maintaining content quality across a wider array of hardware. VR-ready PC is more affordable.

#### Supported Platform

ASW is introduced into Hypereal VR Runtime since 0.4 Release.
  - NVIDIA: GTX 900/1000 series
  - AMD: RX 400/500 series, R9 Fury/390/290 series
  - NVIDIA Display Driver: 372.90 and later
  - AMD Display Driver: Crimson ReLive Edition 16.12.1 and later (RX series), Crimson ReLive Edition 17.4.1 and later (R9 series)
  - Operating System: Windows 8 / Windows 8.1 / Windows 10, Windows 7 is NOT supported

#### How to enable/disable ASW

ASW is enabled by default since 1.0 Release. It is very easy and convenient for users to contrl ASW enablement/disablement.
  - Enable ASW
    1.  Change "EnableAsw" value to 1 in Data/HVRSDKConfig.cfg
    2.  Restart Hypereal VR Runtime
    3.  ASW is enabled in auto mode (kick in if FPS < 90 and quit otherwise)
  - ASW mode switch. For debugging and comparing purpose, we provided several ASW modes for selection, which is very convenient to switch by the following hot key at anytime when ASW is enabled in Hypereal VR runtime.
    1.  CTRL + NUMPAD 1: Disable ASW
    2.  CTRL + NUMPAD 2: Disable ASW but limit application rendering speed to 45fps
    3.  CTRL + NUMPAD 3: Force enabling ASW no matter what FPS is.
    4.  CTRL + NUMPAD 4: Auto ASW based on application real time FPS (Default mode)
  - Disable ASW
    1.  Change "EnableAsw" value to 0 in Data/HVRSDKConfig.cfg and restart Hypereal VR Runtime
    3.  OR by hot key CTRL + NUMPAD 1

Notes: ASW is global setting in Hypereal VR Runtime across all VR Clients, which means its state will keep until Runtime is restarted or a new setting is applied by hot key.