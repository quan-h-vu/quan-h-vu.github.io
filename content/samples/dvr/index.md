+++
date = '2025-02-18T16:34:47-08:00'
draft = false
title = 'Procedure: Retrieving DVR footage'
type = 'post'
description = 'This sample was written about a fictional dashcam product, showing users how to retrieve DVR video via an online portal.'
tags = ['procedure','Madcap Flare']
weight = 25
showTableOfContents = true
+++

## About This Sample

The sample below was written about a fictional dashcam product, showing users how to retrieve DVR video via an online portal. The product is based on a real product I have documented, though many details have been changed in this document.

| Criteria | Description                  |
|----------|------------------------------|
| Tools    | Madcap Flare                 |
| SMEs     | product manager, UX designer |
| Others   | none                         |

The original includes an image showing the equivalent to the Video Retrieval page but that has not been reproduced. Links in the sample are blank cross-references.

The sample begins below the line.

---

The Video Retrieval portal lets you search for footage from your cameras’ DVR storage and save it to the cloud for future use. When your camera’s DVR storage reaches its limit, the oldest video gets overwritten by new video. You must retrieve any desired footage before this occurs.

## Before You Begin

To access a camera's storage, it must be connected to a Wi-Fi network. For more detail, refer to [Configuring Wi-Fi Networks on the Device](/samples/dvr).

## Instructions

1. Go to the Vehicle Connect page. Search for the desired vehicle using the available search filters.
2. Press **Connect** for the desired vehicle. This opens the Video Retrieval page to access the vehicle’s available DVR footage.
3. On the Video Retrieval page, search for desired footage using the available playback tools.
	- **Zoom**: Each camera can hold up to 200 hours of footage. Use the timeline’s zoom options to focus on specific 24-hr, 4-hr, or 1-hr sections for playback.
	- **Speed**: Video playback speed can be adjusted for easier review from 0.25x up to 8x speed.
	- **Map**: The map shows segments representing available video based on the vehicle’s location. Select a segment from the map to queue up footage from there. If multiple segments are available at a location, right-click on the location and select from the list.
	- **Tags**: Tags are recorded for certain events including ignition on/off, door open/closed, and ramp/lift usage. These are displayed over the timeline. Use these as context clues to find the desired footage.
4. After you’ve identified the desired footage, press **Clip**. Drag the markers to the start and end of the footage to be saved (maximum: 300 seconds per clip). If desired, you can edit the Clip Name from the default.
5. Press **Save**.

After the clip is saved, it’s stored in the Video Library. It can be viewed and downloaded for 90 days after retrieval. For more detail, go to [Managing the Video Library](/samples/dvr).