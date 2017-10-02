---
title: FitRankings API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - curl

toc_footers:
  - <a href='mailto:support@fitrankings.com'>Request a Developer Key</a>

includes:
  - activities
  - users
  - groups
  - errors

search: true
---

# Introduction

FitRankings provides a simple and powerful REST API to authenticate, integrate and consume 3rd party fitness application data. 

This API reference provides information on available endpoints and how to interact with the FitRankings API.

<aside class="success">
<strong>IMPORTANT</strong> - There are two ways of interacting with the FitRankings API. The first is the Standard OAuth Flow, the other is a Custom OAuth Flow. The custom flow is used to provide streamlined turn-key integration through an embeddable. The Standard flow provides more setup but offers more flexibility. For more information on each method and which is right for you, contact support@fitrankings.com.
</aside>

## Supported App/Device Integrations
- Fitbit
- MapMyFitness/Under Armour
- Polar
- Garmin
- Google Fit
- RunKeeper
- Jawbone
- Moves
- Misfit
- Apple HealthKit (Coming Soon)

## Developer Registration


# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

To access to the FitRankings OAuth2 API, contact support@fitrankings.com. Upon approval, you will be given a client id and client secret to use with each API request. We will also require you provide us with a title, description, and callback uri as a part of your registration process.

In order to access resources (activities, users, etc.), an application must be granted permission by the resource owner. To do so, the client application must direct the owner to our authorization endpoint. We recommend doing so in a 400x600 popup. Below, you will find the request data to include for a successful authentication process. Once the owner has authorized the client application, (s)he will be given the opportunity to connect with a selection of 3rd party fitness devices. After doing so, (s)he will be returned to the callback_uri provided by the client. If the owner has successfully authorized the client, the callback_uri will contain a unique identifier and access token for the client to use in subsequent requests for the owner’s resources.

`Authorization: Bearer YOUR_TOKEN`

<aside class="notice">
You must replace <code>YOUR_TOKEN</code> with your developer API key.
</aside>

