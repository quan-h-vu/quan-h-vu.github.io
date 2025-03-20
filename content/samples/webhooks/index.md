+++
date = '2025-03-20T09:55:03-07:00'
draft = false
title = 'API Documentation: Webhooks'
type = 'post'
description = 'This is one of my first pieces of API documentation. This provides an overview of available webhooks including details on authentication and payload delivery.'
tags = ['API documentation','Git','Markdown']
weight = 10
showTableOfContents = true
+++

## About This Sample

The sample below is one of my first pieces of API documentation. This provides an overview of available webhooks including details on authentication and payload delivery. [A companion piece](/samples/dtcwebhook) to this document provides details on a specific webhook.

| Data | Description                           |
|----------|---------------------------------------|
| Tools    | Markdown, Git                       |
| SMEs     | multiple engineers, product manager |
| Others   | Tech Support lead                                  |

The source document is available [here](https://lytxdeveloperportal.redoc.ly/docs/webhookparent/). It has been reproduced below for preservation. The sample begins below the line.

---

Webhooks allow clients to have their data automatically sent in near real-time to a desired HTTP endpoint. From there, the data can be customized as desired by the client. This gives clients more control of their data, easier access, and near real-time updates.

## Onboarding

Clients must work with Lytx Technical Support during onboarding. They must provide the following data.

| Data           | Description                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| API URL        | The client's endpoint to which they desire data sent.                                      |
| Email          | One or more email addresses to which alert messages will be sent in the event of an error. |
| Authentication | The client must specify the authentication method and provide the requisite data.          |

## Authentication

This webhook currently supports two types of client endpoint authentication: basic and token-based authentication. Clients must provide us with their endpoint and implement one of the supported types.

### Basic Authentication

For basic authentication, a username and password are encoded into the HTTP Request Header.

```
{
  "userName": "webhookuser1",
  "password": "test123!"
}
```

### Token-Based Authentication

We support three different methods of token-based authentication.

#### 1. Bearer Token

For the Bearer Token method, we will add the client’s bearer token to the HTTP POST Request headers under Authorization.

```
{
  "tokenType": "bearer",
  "tokenValue": "<TOKEN>"
}
```

#### 2. API Key

For the API Key method, we will add the client’s API key to the HTTP POST Request Headers under `apikey`.

```
{
  "tokenType": "apikey",
  "tokenValue": "<APIKEY>"
}
```

#### 3. Custom Token

The Custom Token will be added to the payload HTTP Post Request Headers under the specific `TOKEN_NAME` provided, along with the `TOKEN_VALUE`.

```
{
  "tokenType": "custom",
  "tokenName": "<TOKEN_NAME>",
  "tokenValue": "<TOKEN_VALUE>"
}
```

## Delivery

After onboarding and authentication customization, data will begin sending to the specified endpoint provided during the onboarding process. Our method and timing of delivery is as follows.

| Data | Method    | Frequency                                | Notes                                                |
|------|-----------|------------------------------------------|------------------------------------------------------|
| DTC  | HTTP POST | Every 5 seconds or every 500 DTCs.       | Each message can contain DTCs for multiple vehicles. |
| GPS  | HTTP POST | Every 5 seconds or every 500 GPS points. | There is one message per vehicle.                      |

### Unsuccessful Delivery

If the initial delivery is unsuccessful, delivery is continuously retried for up to 24 hours. During that time, an automated message will be sent every hour to the email address(es) provided during sign-up until a delivery is made successfully.

The message will inform the client that there is a problem with their endpoint. They will be instructed to reach out to Lytx Technical Support to help resolve the issue.

If issues persist after 24 hours, delivery is paused until the issue is resolved.