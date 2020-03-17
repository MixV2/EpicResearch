# 1. EpicResearch
A compilation of research dedicated to the internal workings of Epic's services.

## 1.1 Contents

- [1. EpicResearch](#1-epicresearch)
  - [1.1 Contents](#11-contents)
  - [1.2 Authentication](#12-authentication)
    - [1.2.1 Authentication Flow](#121-authentication-flow)
    - [1.2.2 Account Public Service](#122-account-public-service)
  - [1.3 MCP](#13-mcp)

## 1.2 Authentication
Authentication related requests use both `https://www.epicgames.com` and `https://account-public-service-prod.ol.epicgames.com`.

### 1.2.1 Authentication Flow
TODO! For now, I recommend you check out these implementations on how to authenticate:
- [C# Auth Flow by iXyles](https://gist.github.com/iXyles/ec40cb40a2a186425ec6bfb9dcc2ddda)
- [Python Auth Flow by Terbau](https://gist.github.com/Terbau/9a07849fb30c0232af730265c327e27c)
- [JavaScript Auth Flow by MixV2](https://gist.github.com/MixV2/8483cc20ba2055e78fa72336da1e0bf7)

### 1.2.2 Account Public Service
  The base URL for this service is `https://account-public-service-prod.ol.epicgames.com`. Other URLs include `https://account-public-service-prod03.ol.epicgames.com`, `https://account-public-service-prod-m.ol.epicgames.com` and `https://account-public-service-stage.ol.epicgames.com`.
  
An example service request used for getting an access token:
```http
POST https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token HTTP/1.1
Authorization: basic MzhkYmZjMzE5NjAyNGQ1OTgwMzg2YTM3YjdjNzkyYmI6YTYyODBiODctZTQ1ZS00MDliLTk2ODEtOGYxNWViN2RiY2Y1
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials&token_type=eg1
```

`token_type` with value `eg1` can be appended to return a [JWT token](https://jwt.io/introduction/) - or, you can optionally not append `token_type` and receive a 32 character token that works in the same way.

  ### Authorization Header
  For the first service request, `/account/api/oauth/token`, requires an `Authorization` header to determine which game an authentication token should be generate for. The value passed in the header is formatted as `client_id:secret` and then encoded in Base64.
  
  | Client Name | Client ID | Secret |
  | - | - | - |
  | fortnitePCGameClient | ec684b8c687f479fadea3cb2ad83f5c6 | e1f31c211f28413186262d37a13fc84d |
  | fortniteIOSGameClient | 3446cd72694c4a4485d81b77adbb2141 | 9209d4a5e25a457fb9b07489d313b41a |
  | fortniteAndroidGameClient | 3f69e56c7649492c8cc29f1af08a8a12 | b51ee9cb12234f50a69efa67ef53812e |
  | fortniteCNGameClient | efe3cbb938804c74b20e109d0efc1548 | 6e31bdbae6a44f258474733db74f39ba |
  | KairosPC | 5b685653b9904c1d92495ee8859dcb00 | 7Q2mcmneyuvPmoRYfwM7gfErA6iUjhXr |
  | Kairos iOS | 61d2f70175e84a6bba80a5089e597e1c | FbiZv3wbiKpvVKrAeMxiR6WhxZWVbrvA |
  | Kairos Android | 0716a69cb8b2422fbb2a8b0879501471 | cGthdfG68tyE7M3ZHMu3sXUBwqhibKFp |
  | launcherAppClient2 | 34a02cf8f4414e29b15921876da36f9a | daafbccc737745039dffe53d94fc76cf |
  | androidPortal | 38dbfc3196024d5980386a37b7c792bb | a6280b87-e45e-409b-9681-8f15eb7dbcf5 |
  | launcherServiceClient | f3e80378aed4462498774a7951cd263f | Unknown |
  | utClient | 1252412dc7704a9690f6ea4611bc81ee | Unknown |
  | wexIOSGameClient | ec813099a59f48d4a338f1901c1609db | 72f6db62-0e3e-4439-97df-ee21f7b0ae94 |
  | utDedicatedServerEpicTrusted | ad8def9ae6b84360b6c9b358aba06262 | Unknown |
  | utDedicatedServerEpicHosted | e0aca23dfb7348d6bad648bbe175a6e6 | Unknown |
  | Google (YouTube) | fa39ae1203b5438280f515f38a50f08e | 1564071012329 |
  | merch-sso (Retail Row) | 9427129c087d4049886d3b47349d1aad | 95ba71fc75198ebce22b69dc89e5b27adcf78ec1 |
  | SF Community | b31a9e178ab84b21ad7435a53e4da4af | Not Applicable |
  | udnClient | bc742d26f8314469aa997373f39c876e | Not Applicable |
  | dieselWebsite | 875a3b57d3a640a6b7f9b4e883463ab4 | Not Applicable |
  | fortniteComClient | cd2b7c19c9734a2ab98dc251868d7724 | Not Applicable |
  | affiliateWeb | 4d9a4e9e568a40faa77b9757b4fac210 | Not Applicable |
  | egstoreContentService | a472abd3e5ad4d90a0549213906dcf3f | Not Applicable |
  | creativeModeWebsite | 7de9f4b799d3470984093b218287dc72 | Not Applicable |

  ### Grant Types
  - Grant types are used to determine what type of authentication request is being sent. The most used and useful grant types are `exchange_code`, `refresh_token` and `client_credentials`.
  
  - List of grant types:
    - `password`, takes username & password (deprecated)
    - `external_auth`, takes external auth type (defaults to internal) and an external auth token
    - `device_auth`, takes account id, device id & secret
    - `authorization_code`, takes a code
    - `exchange_code`, takes an exchange code
    - `refresh_token`, takes a refresh token
    - `otp`, takes a two factor auth challenge
    - `client_credentials`
    - `token_to_token` (thanks Jaren)

## 1.3 MCP
In the words of Epic Games, Fortnite has a service called the MCP which players contact in order to retrieve game profiles, statistics, items, matchmaking info and more.

  ### Profile Commands
  Here is a list of commands that can be using to retreive information about a profile.
  All profile command based requests must be formatted as `https://fortnite-public-service-prod11.ol.epicgames.com/fortnite/api/game/v2/profile/{accountId}/client/{command}?profileId={profileId}&rvn={revision}`.
 
  - `QueryProfile` - queries a profile
