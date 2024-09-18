---
title: "Troubleshooting"
linkTitle: "Troubleshooting"
description: ""
date: 2024-08-19
draft: false
weight: 40
---

{{% alert %}}
Before you start troubleshooting the Android TV box and the app, the Android TV box must be connected to a screen.
{{% /alert %}}

When something happens to one of your Android TV boxes, it may be necessary to troubleshoot the device. This topic helps you troubleshoot the most common issues.

## Disconnected cables

![](../../../images/live_tv_app_troubleshooting.png)

### USB to RF/DVB-C cable disconnected

When the USB to RF/DVB-C cable is disconnected from the Android TV box \(see connection 1 in the image\), then the app loses the tuned channel, and an operator must re-tune the app to the correct channel.

Follow this procedure to solve the issue:

1.  Reconnect the USB to RF/DVB-C cable to the Android TV box.
2.  Using the remote, from the home screen, browse to **Settings \> Device Preferences \> Restart**.
3.  Select **Restart**, and wait for the Android TV box to restart.
4.  After the Android TV box has restarted, browse to the Live TV app and launch it.
5.  Browse to **TV Options \> Settings \> Channel sources**. The Setup your sources screen appears.
6.  Continue the channel setup as described in [Configure app]({{% relref "installation_process.md#configure-app" %}}) from step [4]({{% relref "installation_process.md#channel_setup" %}}).

### Modulator disconnected from USB to RF/DVB-C cable

When the modulator is disconnected from the USB to RF/DVB-C cable \(see connection 2 in the image\), but the USB to RF/DVB-C cable is still connected to the Android TV box, then an operator only needs to reconnect the modulator to the USB to RF/DVB-C cable. The app automatically reconnects to the configured network stream.

### Power cable disconnected

When the power cable is disconnected from the Android TV box \(see connection 3 in the image\), then an operator only needs to reconnect the power cable and relaunch the Live TV app. The app automatically reconnects to the configured network stream.

## Replacing an Android TV box

When one of your Android TV boxes stops working, you must replace it with a new one, and you must upload the same configuration file that was present on the Android TV box you are replacing.

Follow the same installation process as described in [Installation process]({{% relref "installation_process.md" %}}), but use the existing configuration file when you execute the steps under [Create and load configuration file]({{% relref "installation_process.md#create-and-load-configuration-file" %}}).

