+++
date = '2025-03-07T09:56:49-08:00'
draft = false
title = 'Headway Warning Identification (AM2)'
type = 'post'
description = 'This sample showcases an internal wiki I established. It documents how a fictional dashcam product detects tailgating on the road.'
tags = ['concept','reference','troubleshooting','Confluence']
weight = 6
showTableOfContents = true
+++

## About This Sample

The sample below showcases [an internal wiki I established](/samples/internalwiki "Success Story: Building an Internal Product Wiki"), using a modified version of a page template from the wiki. I have included details of a dashcam product's ability to detect tailgating on the road. This is a fictional feature based on a real feature I documented, though many details have been changed for this sample.

This was originally created in Confluence. I have recreated it here in Markdown. The original also included audio files for the alerts used but these have not been recreated. Links in the sample are blank cross-references.

The sample begins below the line.

---

## Overview

The AM2 model of hazard identification is designed to reward reactive drivers. The model integrates audio alerts and incident logs into a cohesive system of escalation. Audio alerts allow drivers to correct their own driving behavior; an incident log is only generated as the next level of escalation if they fail to react. Even further, prevention logs are generated for reactive drivers, giving managers an opportunity to recognize them.

Headway Warning (HWW) identifies instances in which drivers stay within close proximity of other vehicles for an extended duration (often known as tailgating). This article focuses on the AM2 identification of HWW. For details on AM1, go to [Headway Warning Identification (AM1)](/samples/hww).

## Key Differences: AM1 vs. AM2

- **Greater accuracy.** The AM2 model offers greater accuracy over the AM1 model. Because of AM1's limitations, additional post-incident review cycles were implemented to filter out false positives. AM2's accuracy removes the need for such review cycles. This also results in quicker user access to incident logs.
- **Shorter calibration period.** The AM2 model has a shorter calibration period than the AM1 model. Calibration of the AM1 model requires multiple vehicle trips over the span of 3 days to calibrate. The AM2 model completes calibration after driving only a short distance.
- **Automatic recalibration.** With the AM2 model, sensors are automatically recalibrated to account for changes in camera positioning caused by normal wear-and-tear. With the AM1 model, sensors should be manually recalibrated over time.

## Prerequisites

- Compatible devices
	- Megadrive-16 series cameras
	- Saturn-32 series cameras
- OBD cable connection to the vehicle network. For more detail, go to [Installations](/samples/hww).

## Expected User Experience

### Calibration

Upon activation of the AM2 model, each camera will be recalibrated automatically after driving a short distance. Calibration requires driving over 64 km/h for 2.4 km. After shutting off the vehicle, the camera restarts with the newly calibrated sensors.

After initial calibration, sensors recalibrate periodically to account for subtle shifts in camera positioning.

### Hazard Identification

1. During a trip, the camera scans the road for the object vehicle in front of the driver's vehicle. It uses the driver's vehicle speed to calculate the distance in terms of seconds.
2. The camera issues an audio alert when the HWW criteria below are met for 10 continuous seconds:
	- The driver's vehicle is going at least 40 km/h.
	- The distance between the driver's vehicle and the object vehicle is 1.0 seconds or less.
3. If the driver's vehicle continues to meet the HWW criteria, the camera repeats the audio alert every 5 seconds.
4. If the driver's vehicle meets the HWW criteria for 25 continuous seconds, an [incident log](/samples/hww "timeline of incident progression from first alert") is generated.
	- Conversely, if the driver's vehicle stops meeting the HWW criteria before the 25-second threshold, a [prevention log](/samples/hww "timeline of incident progression and resolution") is generated.
5. After generating a log, the timer for HWW identification is reset. 
6. At the end of the trip, all logs are sent to users in the Drivecast online portal.

## Known Limitations/Issues

- Many manufacturers design vehicles with native ADAS signals. Integration of these signals into the AM2 model is not yet supported. To track this, go to [KNUX-9753](/samples/hww "Jira story for ADAS API development").
- Mixed fleets are not supported. Clients must migrate to the AM2 model group-by-group.
- Automatic recalibration is designed for small shifts in camera positioning. If clients remove the camera from the windshield for any reason, the camera must be manually recalibrated. For details, go to [Maintenance](/samples/hww).
- If the vehicle is in an area with poor reception, logs may not be sent. As a workaround, the camera can be configured to connect to a Wi-Fi network to send any logs. For more detail, refer to [Configuring Wi-Fi Networks on the Device](/samples/hww).

## Enabling the Feature

| Setting           | Description                                                                                    | Default          |
|-------------------|------------------------------------------------------------------------------------------------|------------------|
| AM2 HWW velo_min  | Minimum speed (in km/h) the driver's vehicle must travel to meet HWW criteria.                 | 40 km/h |
| AM2 HWW dur_alert1 | Duration (in seconds) in which the HWW criteria are met before issuing the first alert. | 10 s    |
| AM2 HWW dur_max | Duration (in seconds) in which the HWW criteria are met before generating an incident log.         | 25 s      |