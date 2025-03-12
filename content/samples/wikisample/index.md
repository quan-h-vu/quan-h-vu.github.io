+++
date = '2025-03-07T09:56:49-08:00'
draft = true
title = 'Headway Warning Detection (AM2)'
type = 'post'
description = 'This site was built with Hugo, a static site generator. This sample documents how I created and deployed this site.'
tags = ['Hugo','Git','SSG']
weight = 6
showTableOfContents = true
+++

## About This Sample

The sample below uses a modified version of a template from an internal wiki I established. I have added a fictional feature based on a real feature I documented, though many details have been changed for this sample.

The sample begins below the line.

---

## Overview

## Available Options

## Prerequisites

- Compatible devices
	- Megadrive-16 series cameras
	- Saturn-32 series cameras
	- Saturn-R satellite cameras
- 

## Expected User Experience

### Calibration

Upon activation of the AM2 model, each camera will be recalibrated automatically after driving a short distance. Calibration requires driving over 64 km/h for 2.4 km. After shutting off the vehicle, the camera restarts with the newly calibrated sensors.

After initial calibration, sensors recalibrate periodically to account for subtle shifts in camera positioning.

### Detection of Risk

1. During a trip, the camera scans the road for the object vehicle in front of the driver's vehicle. It uses the driver's vehicle speed to calculate the distance in terms of seconds.
2. The camera issues an audio alert when the HWW criteria below are met:
	- The driver's vehicle is going at least 40 km/h.
	- The distance between the driver's vehicle and the object vehicle is 1.0 seconds or less for 10 continuous seconds.
3. If the driver's vehicle repeatedly meets the HWW criteria, the camera repeats the audio alert up to 3 times in a 5-minute window.
4. If the driver's vehicle continues to meet the HWW criteria after the last alert, an Incident Log is generated. The log shows a timeline of the vehicle trip with tags indicating audio alerts issued along with other relevant trip data.
5. After the last alert is issued or if no repeat alerts are issued for 5 minutes, the alert count is reset.
6. At the end of the trip, if any Incident Logs were recorded, they are sent to your online portal.

When reviewing Incident Logs, you can access video recording for the incident, if available. For more details, go to Incident Logs.

## Key Differences: AM1 vs. AM2

- The AM2 model integrates audio alerts and incident logs into a cohesive system of escalation. Audio alerts allow drivers to correct their own driving behavior; if they don't, an Incident Log is generated and sent to their manager as the next level of escalation. With AM1, audio alerts and incident logs are configured separately. This can result in unexpected scenarios where audio alerts are not issued for an incident log.
- The AM2 model offers greater accuracy over the AM1 model. Because of AM1's limitations, additional post-incident review cycles were implemented to filter out false positives. AM2's accuracy removes the need for such review cycles. This results in quicker user access to Incident Logs.
- The AM2 model has a shorter calibration period than the AM1 model. Calibration of the AM1 model requires multiple trips over the span of 3 days to calibrate whereas the AM2 model completes calibration after driving only a short distance.
- With the AM2 model, sensors are automatically recalibrated to account for changes in camera positioning caused by normal wear-and-tear. With the AM1 model, sensors should be manually recalibrated over time.

## Considerations for Optional Features

3rd party ADAS - API integration?
Video Retrieval

## Known Limitations/Issues

Calibration?
Other features that don't work?

## Enabling the Feature

## SMEs

## Additional Resources



I should write about AI. Definitely.
Can talk about Following Distance using the industry-standard verbiage, Headway Warning (HWW).