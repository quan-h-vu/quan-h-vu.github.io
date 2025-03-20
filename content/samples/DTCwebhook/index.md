+++
date = '2025-03-20T12:58:25-07:00'
draft = true
title = 'API Documentation: DTC Webhook Reference'
type = 'post'
description = 'This is one of my first pieces of API documentation. This provides an overview of available webhooks including details on authentication and payload delivery.'
tags = ['API documentation','Git','Markdown']
weight = 11
showTableOfContents = true
+++

## About This Sample

The sample below is a companion to [one of my first pieces of API documentation](/samples/webhooks), which provides an overview of available webhooks. This sample is a reference page for a specific webhook providing vehicle diagnostic trouble code (DTC) data.

| Data | Description                           |
|----------|---------------------------------------|
| Tools    | Markdown, Git                       |
| SMEs     | multiple engineers, product manager |
| Others   | none                                  |

The source document is available [here](https://lytxdeveloperportal.redoc.ly/docs/webhook_dtc/). It has been reproduced below to preserve my contributions. The sample begins below the line.

---

The DTC webhook integration allows clients to bring DTC data from Lytx® devices into a 3rd-party system. Clients can leverage this data to power robust maintenance solutions to help keep their vehicles in top condition.

## Sample Payload

```
[
  {
    "vehicleId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "vehicleName": "TestVehicle123",
    "groupId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "groupName": "Fleet Manager",
    "serialNumber": "MV20231122",
    "vin": "1M8GDM9AXKP042788",
    "code": "P0068",
    "description": "MAP/MAF - Throttle Position Correlation",
    "source": "OBD2",
    "sourceId": "2024",
    "active": true
  }
]
```

| Data         | Type    | Description                                                                                               |
|--------------|---------|-----------------------------------------------------------------------------------------------------------|
| vehicleId    | guid    | ID of the vehicle.                                                                                        |
| vehicleName  | string  | Name of the vehicle.                                                                                      |
| groupId      | string  | ID of the vehicle's group.                                                                                |
| groupName    | string  | Name of the vehicle's group.                                                                              |
| serialNumber | string  | Serial number of the Lytx device.                                                                         |
| vin          | string  | Vehicle Identification Number.                                                                            |
| code         | string  | Code of the issue detected.                                                                               |
| description  | string  | Short description of the issue detected.                                                                  |
| source       | string  | ECM type (e.g. J1939, OBD2).                                                                              |
| sourceId     | string  | ECU source address.                                                                                       |
| active       | boolean | Indicates if the DTC is still active. After the issue is resolved, the DTC is returned as `active:false`. |

## Delivery

Multiple messages will be sent every 5 seconds containing a list of vehicle names and their respective DTCs. Each message can have up to 500 DTCs from any combination of vehicles.