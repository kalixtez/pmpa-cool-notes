## Android is actually Linux

One thing to keep in mind is that the Android operating system is based on the Linux kernel. It is akin to a desktop Linux distribution, which package their own utilities (desktop environments, shells, filesystem explorers, etc...) and other binaries along side with a Linux kernel to act as the backbone above which all of the userland is supported.

## Android runtime (ART)

Sometimes referred to as "Dalvik runtime" (legacy name, as this was the mechanism used in the past), is the one of the few actually native userland applications. Most other userland applications run on top of it, translating byte code to native machine code instructions at runtime. Applications run sandboxed, and a provisional, dedicated and ephemeral user is created to run the application.

## Android system architecture

![../Android-architecture.png](.)

## HAL

The hardware abstraction layer (HAL) is used by the ART and native C/C++ libraries to communicate with hardware, so these libraries can communicate in a transparent manner to the underlying hardware.

## Java API Framework

It is used to develop GUI applications. It also allows  for app to expose `Content Providers`, which are directories publicly accessible by other applications, as a way of IPC.

## Compilation process of an Android app

![[Pasted image 20250630164845.png]]

## Signing

Android applications are signed by both the developer and Google using asymmetric cryptography (public and private keys). Apps must be signed BEFORE they can be executed on an Android device.
