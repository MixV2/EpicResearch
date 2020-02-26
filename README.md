# 1. EpicResearch
A compilation of research dedicated to the internal workings of Epic's services.

## 1.1 Contents

- [1. EpicResearch](#1-epicresearch)
  - [1.1 Contents](#11-contents)
  - [1.2 Authentication](#12-authentication)
    - [1.2.1 Authentication Flow](#121-authentication-flow)
    - [1.2.2 Account Public Service](#122-account-public-service)
  - [1.3 Domains](#13-domains)

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
  | SF Community | b31a9e178ab84b21ad7435a53e4da4af | Not Needed |
  | udnClient | bc742d26f8314469aa997373f39c876e | Not Needed |

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

### 1.3 Domains
A list of domains for each service, with varying environments.

Base subdomains:
- prod.ol.epicgames.com
- stage.ol.epicgames.com
- gamedev.ol.epicgames.net

#### Unreal Tournament Service
- ut-public-service-ci.ol.epicgames.net
- ut-public-service-maintesting-gamedev.ol.epicgames.net
- ut-public-service-uereleasetesting-gamedev.ol.epicgames.net
- ut-public-service-gamedev.ol.epicgames.net
- ut-public-service-stage.ol.epicgames.net
- ut-public-service-publictest-prod12.ol.epicgames.com
- ut-public-service-quail-prod12.ol.epicgames.com
- ut-public-service-prod10.ol.epicgames.com

#### Fortnite Public Service
- fortnite-public-service-ci.ol.epicgames.net
- fortnite-public-service-main-gamedev.ol.epicgames.net
- fortnite-public-service-uereleasetesting-gamedev.ol.epicgames.net
- fortnite-public-service-flow-gamedev.ol.epicgames.net
- fortnite-public-service-latest-gamedev.ol.epicgames.net
- fortnite-public-service-testing-gamedev.ol.epicgames.net
- fortnite-public-service-devathena-gamedev.ol.epicgames.net
- fortnite-public-service-devathenalatest-gamedev.ol.epicgames.net
- fortnite-public-service-featurealatest-gamedev.ol.epicgames.net
- fortnite-public-service-featureblatest-gamedev.ol.epicgames.net
- fortnite-public-service-releasetesting-gamedev.ol.epicgames.net
- fortnite-public-service-stage.ol.epicgames.com
- fortnite-public-service-nscert-stage.ol.epicgames.com
- fortnite-public-service-live-stage.ol.epicgames.com
- fortnite-public-service-release-stage.ol.epicgames.com
- fortnite-public-service-dev-stage.ol.epicgames.com
- fortnite-public-service-prod11.ol.epicgames.com
- fortnite.fortnite.qq.com
- fortnite-public-service-publictest-prod12.ol.epicgames.com
- fortnite-public-service-preview-prod.ol.epicgames.com
- fortnite-public-service-events-prod.ol.epicgames.com
- fortnite-public-service-reviewcn-prod.ol.epicgames.com
- fortnite-public-service-loadtest-prod.ol.epicgames.com
- fortnite-public-service-extqadevtesting-prod.ol.epicgames.com
- fortnite-public-service-devplaytest-prod12.ol.epicgames.com
- fortnite-public-service-bacchusplaytest-prod.ol.epicgames.com
- fortnite-public-service-loctesting-prod12.ol.epicgames.com
- fortnite-public-service-extqareleasetesting-prod.ol.epicgames.com
- fortnite-public-service-extqareleasetestingb-prod.ol.epicgames.com
- fortnite-public-service-releaseplaytest-prod.ol.epicgames.com
- fortnite-public-service-predeploya-prod.ol.epicgames.com
- fortnite-public-service-predeployb-prod.ol.epicgames.com
- fortnite-public-service-livetesting-prod.ol.epicgames.com
- fortnite-service-livetesting.fortnite.qq.com
- fortnite-service-epicreleasetesting.fortnite.qq.com
- fortnite-service-tencentreleasetesting.fortnite.qq.com
- fortnite-service-securitytesting.fortnite.qq.com
- fortnite-public-service-partners-prod.ol.epicgames.com
- fortnite-public-service-partnersstable-prod.ol.epicgames.com
- fortnite-public-service-ioscert-prod.ol.epicgames.com
- fortnite-public-service-athena-prod.ol.epicgames.com

#### Account Public Service
- account-public-service-common-gamedev.ol.epicgames.net
- account-public-service-prod03.ol.epicgames.com
- account-public-service-prod.ol.epicgames.com
- account-public-service-stage.ol.epicgames.com

#### Friends Public Service
- friends-public-service-gamedev.ol.epicgames.net
- friends-public-service-prod06.ol.epicgames.com

#### Persona Public Service
- persona-public-service-gamedev.ol.epicgames.net
- persona-public-service-prod06.ol.epicgames.com

#### Entitlement Public Service
- entitlement-public-service-gamedev.ol.epicgames.net
- entitlement-public-service-prod08.ol.epicgames.com

