+++
date = '2025-03-07T09:56:49-08:00'
draft = false
title = 'Headway Warning Identification (AM2)'
type = 'post'
description = 'This site was built with Hugo, a static site generator. This sample documents how I created and deployed this site.'
tags = ['product documentation']
weight = 6
showTableOfContents = true
+++

## About This Sample

The sample below uses a modified version of a template from an internal wiki I established. I have added a fictional feature based on a real feature I documented, though many details have been changed for this sample.

The sample begins below the line.

---

## Overview

The AM2 model of hazard identification is designed to reward reactive drivers. The model integrates audio alerts and incident logs into a cohesive system of escalation. Audio alerts allow drivers to correct their own driving behavior; an incident log is only generated as the next level of escalation if they fail to react. Even further, prevention logs are generated for reactive drivers, giving managers an opportunity to recognize employees.

Headway Warning (HWW) identifies instances in which drivers stay within close proximity of other vehicles for an extended duration (often known as tailgating). This article focuses on the AM2 identification of HWW. For details on AM1, go to Headway Warning Identification (AM1).

## Key Differences: AM1 vs. AM2

- **Greater accuracy.** The AM2 model offers greater accuracy over the AM1 model. Because of AM1's limitations, additional post-incident review cycles were implemented to filter out false positives. AM2's accuracy removes the need for such review cycles. This also results in quicker user access to incident logs.
- **Shorter calibration period.** The AM2 model has a shorter calibration period than the AM1 model. Calibration of the AM1 model requires multiple vehicle trips over the span of 3 days to calibrate. The AM2 model completes calibration after driving only a short distance.
- **Automatic recalibration.** With the AM2 model, sensors are automatically recalibrated to account for changes in camera positioning caused by normal wear-and-tear. With the AM1 model, sensors should be manually recalibrated over time.

## Prerequisites

- Compatible devices
	- Megadrive-16 series cameras
	- Saturn-32 series cameras
- OBD cable connection to the vehicle network. For more detail, go to [Installations](/#).

## Expected User Experience

### Calibration

Upon activation of the AM2 model, each camera will be recalibrated automatically after driving a short distance. Calibration requires driving over 64 km/h for 2.4 km. After shutting off the vehicle, the camera restarts with the newly calibrated sensors.

After initial calibration, sensors recalibrate periodically to account for subtle shifts in camera positioning.

### Hazard Identification

1. During a trip, the camera scans the road for the object vehicle in front of the driver's vehicle. It uses the driver's vehicle speed to calculate the distance in terms of seconds.
2. The camera issues an audio alert when the HWW criteria below are met:
	- The driver's vehicle is going at least 40 km/h.
	- The distance between the driver's vehicle and the object vehicle is 1.0 seconds or less for 10 continuous seconds.
3. If the driver's vehicle repeatedly meets the HWW criteria, the camera repeats the audio alert up to 2 times in a 5-minute window.
4. If the driver's vehicle continues to meet the HWW criteria after the last alert, an [incident log](/# "timeline of incident progression from first alert") is generated.
	- Conversely, if the driver's vehicle stops meeting the HWW criteria before the last alert, a [prevention log](/# "timeline of incident progression and resolution") is generated.
5. After the last alert is issued or if no repeat alerts are issued for 5 minutes, the alert count is reset.
6. At the end of the trip, if any logs were recorded, they are sent to users in the AZEL online portal.

## Known Limitations/Issues

- Many manufacturers design vehicles with native ADAS signals. Integration of these signals into the AM2 model is not yet supported. To track this, go to KNUX-9753.
- Mixed fleets are not supported. Clients must migrate to the AM2 model group-by-group.
- Automatic recalibration is designed for small shifts in camera positioning. If clients remove the camera from the windshield for any reason, the camera must be manually recalibrated. For details, go to [Diagnostics](/#).

## Enabling the Feature

| Setting           | Description                                                                                    | Default          |
|-------------------|------------------------------------------------------------------------------------------------|------------------|
| AM2 HWW velo_min  | Minimum speed (in km/h) the driver's vehicle must travel to meet HWW criteria.                 | 40 km/h |
| AM2 HWW close_dur | Duration (in seconds) in which the driver's vehicle and object vehicle are in close proximity. | 10 s    |
| AM2 HWW alert_max | Maximum number of alerts to issue in a 5-minute period before an incident is logged.           | 3 alerts      |