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

To access to the FitRankings OAuth2 API, contact support@fitrankings.com. Upon approval, you will be given a client id and client secret. These credentials will be used to retrieve a master token for your application to include in subsequent requests. 

## Master Token

```shell
curl -X "POST" "https://api.fitrankings.com/iq/tokens/master-token/" \
     -d $'{ "client_id": "...", "client_secret": "..." }'
```

> The above command returns JSON structured like this:

```json
{"token": "MASTER_TOKEN"}
```

To obtain a client application’s master token, one must send a request as indicated, with the client credentials provided to you included in the request body. Thereafter this token must be stored and used with subsequent requests for application-level resources. As a rule of thumb, requests containing this token in the authorization header will grant access to the resources of all users who’ve authorized the client application. To restrict a request to the resources of a specific user, simply provide that user’s unique access token in place of the master token in the authorization header.

<aside class="notice">
Save this token and keep in a safe place!
</aside>

## User Authentication

```shell
curl "https://api.fitrankings.com/iq/oauth2/?client_id=...&callback_uri=https:%2F%2Fwww.example.com%2F"
```
> Once authorized, the user will be redirected to the callback, such as:

```
https://www.example.com/?user_id=000000&token=USER_TOKEN
``` 
> Save the credentials from the query string for subsequent requests.

In order to access resources (activities, users, etc.), an application must be granted permission by the resource owner. To do so, the client application must direct the owner to our authorization endpoint. We recommend doing so in a 400x600 popup (see example). See below for necessary query parameters to include in your request. Once the owner has authorized the client application, (s)he will be given the opportunity to connect with a selection of 3rd party fitness devices. After doing so, (s)he will be returned to the callback_uri provided by the client. If the owner has successfully authorized the client, the callback_uri will contain a unique identifier and access token for the client to use in subsequent requests for the owner’s resources.

### Query Parameters

Parameter | Description
--------- | -----------
client_id | This client_id provided to you.
callback_uri | If one isn't provided, the last one to registered will be reused.
