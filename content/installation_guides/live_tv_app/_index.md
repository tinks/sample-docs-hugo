---
title: "Live TV App Installation Guide"
linkTitle: "Live TV App"
description: ""
date: 2024-08-19
draft: false
weight: 20
---

The Live TV app is an Android TV app to be installed on Android TV boxes that sit in the distributor's headend. The Live TV app enables ad insertion into a specific network stream for a specific region.

You need one Android TV box, with the Live TV app installed, for each network stream you broadcast and each region where targeted ads are inserted. For example, if you have three networks that are served in five regions, then you need \( 3 x 5 \) = 15 Android TV boxes.

The regions are defined by you in collaboration with your ratings data provider. The regions must be closely related to how your physical video distribution is set up. The defined regions are used to target your ad campaigns.

To summarize, you need to:

* install the Live TV app on Android TV boxes, for each combination of region and network,
* place a configuration file on each Android TV box, identifying the device and the combination of network and region it serves,
* and tune the Live TV app on each Android TV box to the correct network.

## Features

The Live TV app has the following features:

* Insertion of addressable ads based on SCTE-35 cue data in the network stream. Ads inserted are based on the combination of region and network configured in the Live TV app on the Android TV box.
* Overlay the channel logo, including special time limited logos, during addressable ad playback.

  {{% alert %}}
  The channel logos must be available in the the company's systems. Contact your designate company representative, to request the upload of channel logos and special time limited channel logos.

  When making a request, channel logos must be in `.png` format and you must provide the validity dates for the special time limited logos.
  {{% /alert %}}


## Limitations

Only the following Android TV boxes are supported by the Live TV app:

* SEI Robotics 804

Other limitations:

* When the network stream is disconnected and later reconnected to the Android TV box, either due to physically disconnecting the cable or due to network stream errors, then an operator must re-tune the Android TV box to the correct network stream. See [Troubleshooting]({{% relref "troubleshooting.md" %}}) for more information.
* Installing new versions of the Live TV app must be done by an operator on site, because the company has no access to the network where the Android TV boxes are located to deliver over-the-air \(OTA\) updates.

