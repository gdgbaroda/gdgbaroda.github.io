---
layout: post
title: "Stock Android Distribution And Project Treble"
categories: ["Technical Knowledge"]
tags: ["Stock Android Distribution","Project Treble"]
author: Rushi M Thakker
assets: "/assets/2018-07/stock-android-project-treble"
---

## <center>  STOCK ANDROID DISTRIBUTION AND PROJECT TREBLE </center>

We all have Android phones in our hand and still we all have different features based on OS because of the customizations [ *OEMs(Original Equipment Manufacturers)* ](https://en.wikipedia.org/wiki/Original_equipment_manufacturer)  make to devices before launching them. For those new to the term, in simple language, OEMs are companies that manufacture Android powered devices, for eg.Samsung, OnePlus, Motorola etc. All these companies modify the actual source code of Android framework according to their need.
But in some cases, companies tie up with Google and Silicon manufacturers to run pure Android framework as released by Google without any modification.

---
#### WHAT IS STOCK ANDROID? ####

The pure Android Framework or the pure Android OS which we talked about is nothing but **"Stock Android"**. Many of you would be now thinking as to what happens to the Android which we receive in our phones? Is it not the same as released by Google? Also why does it take so much time for their devices to get the latest Android OS update? All your questions will be answered. Keep reading.

Now to understand when a new Android release is determined, we need to understand Stock Android OS distribution cycle.

---
#### STOCK ANDROID DISTRIBUTION ####


![Stock Android Distribution Cycle](/assets/2018-07/stock-android-project-treble/stock_android_distribution_cycle.png){:class="img-responsive" : .center-image }


To better understand the process of stock android distribution, let's break down the whole process in steps:

**1. The Android team publishes the open-source code for the latest release to the world** :
 Whenever Google has a finalized an *RC(Release Candidate)* for new release it contacts OEMs and Silicon chip makers(Qualcomm, MediaTek etc) and informs them regarding the same.Release Candidate is nothing but the version of Android OS that has been ready after going through several Alpha, Beta phases of testing and bug fixes and is considered to be good for release.

**2. Silicon manufacturers, the companies that make the chips that power Android devices, modify the new release for their specific hardware** :
 They create a [ *BSP(Board Support Package)* ](https://whatis.techtarget.com/definition/board-support-package) for their particulat hardware. In simple words, if a silicon maker like Qualcomm has created a Snapdragon 650 processor to work with Android Nougat then it will create a BSP which will contain the code of Android Nougat bundled with Snapdragon 650 specific code which will allow Android Nouget to be run on Snapdragon 650.

**3. Silicon manufacturers pass the modified new release to device makers — the companies that design and manufacture Android devices** :
 Device makers modify the new release again as needed for their devices. Here, as discussed in the very first article companies add their code and propriety apps or features to Android OS as they want.

**4. Device makers work with carriers to test and certify the new release. After all those coding and integrations are completed** :
 After everything is ready it is the job of OEMs and carriers to look to it that the device that has been ready has properly been certified to be released. For this, they have to see that the device meets all the expected standards of WiFi, Bluetooth, Telephony etc. Google also issues a certificate for installed Google play services and apps.

**5. Device makers and carriers make the new release available to users** :
Finally, this is the time, new device/update of the latest Android OS reaches the end user.

This is just too much work in too less time for OEMs to make new release available in their flagship devices. Often OEMs target that the latest BSPs and OS updates are available to them during holiday times, but unfortunately due to such a lengthy process they often have to use old [ *SoC(Silicon on Chip)* ](https://en.wikipedia.org/wiki/System_on_a_chip) to support their devices.

**P.S.:** There is one final step too. In general scenario, after the official launch of Android OS which is ~2-3 weeks after RC has been finalized, Google releases the full source code of new Android OS through [ **Android Open Source Project(AOSP)** ](https://source.android.com/). That is the reason Android is an *"Open Source Platform"*.

---
#### PROJECT TREBLE ####


![Project Treble](/assets/2018-07/stock-android-project-treble/project_treble.jpg){:class="img-responsive" : .center-image }


Project Treble is launched as a part of Android Oreo. The main intention behind project Treble is to reduce the lengthy process of distributing Android OS which required interference of SoC makers everytime to define their implementations for their specific chip.

![BSP Eliminated](/assets/2018-07/stock-android-project-treble/bsp_eliminated.png){:class="img-responsive" : .center-image }

Here, as we have seen before, it was the vendor implementation of hardware which was packaged as BSP and sent to OEMs for their furthur modifications. Here is where project Treble stepped in to separate vendor implementations from AOSP frameworks.

Google has released a set of guidelines for Vendor Implementations and a *Vendor Test Suite(VTS)* which standardises the format for vendor interfaces and removes the need of BSP being made after completely new Android AOSP ROM is ready. With this approach newer Android AOSP ROMs can work on older vendor implementations too.

![OS VTS CTS Relation](/assets/2018-07/stock-android-project-treble/os_vts_cts.png){:class="img-responsive" : .center-image }

To give you an analogy of project Treble with real world:

Imagine if we lived in a world where every car manufacturer decided to design their steering wheels or re-arrange their brakes in a completely different way. If you put a driver in a new car, they may be confused with how to initially handle the vehicle. But thanks to standards, every driver should be familiar with how to operate a steering wheel and brakes on almost any car. Further, driving school teaches all drivers the proper way to operate a vehicle. In this analogy, the vehicle standards are Project Treble.

Before the introduction of project Treble scenario was something like this:

![Distribution Before Treble](/assets/2018-07/stock-android-project-treble/before_treble.png){:class="img-responsive" : .center-image }

After the introduction of project Treble scenario has changed to this:

![Distribution After Treble](/assets/2018-07/stock-android-project-treble/with_treble.png){:class="img-responsive" : .center-image }

---
#### BENEFITS OF PROJECT TREBLE ####

**1. Faster Adoption of new Android OS on devices**:
First and foremost, this solves what it is made to do so. Solving the rate of adoption which has been a great problem of Android  since long. Unlike Apple, very few percentage of devices in market were actually running the latest version of Android. With Project Treble, OEMs have started pushing latest OS updates to their phones. Also, it has been very easy for Google devices or devices running pure stock Android to push their updates.As of now, many devices have already started supporting Android P Beta version even before it has been released. You can use this [**Treble Check**](https://play.google.com/store/apps/details?id=com.kevintresuelo.treble) application to know if your device is supporting Project Treble or not.

**2. Solving timing issue**:
With project Treble in action, BSPs are ready at a much accelerated schedule and OEMs just have to wait for the latest release. They could then step in and deliver their flagship phones or other phones at their point of convenience without much hussle and also provide new AOSP ROM support for their older Treble supported phones. Here is a general scenario of what used to happen before Treble and after Treble:

Before Treble:
![Timing Issue Before Treble](/assets/2018-07/stock-android-project-treble/timing_issue_before_treble.png){:class="img-responsive" : .center-image }
After Treble:
![Timing Issue After Treble](/assets/2018-07/stock-android-project-treble/timing_issue_after_treble.png){:class="img-responsive" : .center-image }

**3. Easier Custom ROM Development**:
Prior to project Treble, if I wanted to use a stock Android(AOSP ROM) on my Samsung device having TouchWiz OS, I would have to mess around a lot of kernel code and get involved in a lot of [HAL(Hardware Abstraction Layer)](https://source.android.com/devices/architecture/hal) hacking. But according to new *VTS standards* it is mandatory that every Treble enable device must be able to build a raw, generic AOSP build. Due to this, it becomes very easy to port latest AOSP ROMs on non-Google Treble enabled devices.

---
#### SOME NOTABLE LINKS TO REFER ####

**1. Treble Official Blog** : [https://android-developers.googleblog.com/2017/05/here-comes-treble-modular-base-for.html](https://android-developers.googleblog.com/2017/05/here-comes-treble-modular-base-for.html)

**2. Faster Adoption with Project Treble** : [https://android-developers.googleblog.com/2018/05/faster-adoption-with-project-treble.html](https://android-developers.googleblog.com/2018/05/faster-adoption-with-project-treble.html)

**3. How Project Treble Revolutionizes Custom ROM Development** :
[https://www.xda-developers.com/how-project-treble-revolutionizes-custom-roms-android-oreo/](https://www.xda-developers.com/how-project-treble-revolutionizes-custom-roms-android-oreo/)

---
#### REFERENCES ####
**1.** : [https://android-developers.googleblog.com/2017/05/here-comes-treble-modular-base-for.html](https://android-developers.googleblog.com/2017/05/here-comes-treble-modular-base-for.html)

**2.** : [https://android-developers.googleblog.com/2018/05/faster-adoption-with-project-treble.html](https://android-developers.googleblog.com/2018/05/faster-adoption-with-project-treble.html)

**3.** : [https://www.xda-developers.com/how-project-treble-revolutionizes-custom-roms-android-oreo/](https://www.xda-developers.com/how-project-treble-revolutionizes-custom-roms-android-oreo/)

**4.** : [https://www.xda-developers.com/stock-android-oreo-huawei-mate-9-project-treble/](https://www.xda-developers.com/stock-android-oreo-huawei-mate-9-project-treble/)

**5.** : [https://www.xda-developers.com/project-treble-google-pixel-2-graphics-drivers/](https://www.xda-developers.com/project-treble-google-pixel-2-graphics-drivers/)

**6.** : [https://www.xda-developers.com/how-android-software-update-sony/](https://www.xda-developers.com/how-android-software-update-sony/)

**7.** : [https://www.xda-developers.com/project-treble-custom-rom-development/](https://www.xda-developers.com/project-treble-custom-rom-development/)
