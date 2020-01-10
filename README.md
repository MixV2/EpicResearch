# 1. EpicResearch
A compilation of research dedicated to the internal workings of Epic's services.

## 1.1 Contents

- [1. EpicResearch](#1-epicresearch)
  - [1.1 Contents](#11-contents)
  - [1.2 Authentication](#12-authentication)

## 1.2 Authentication
Authentication related requests use both `https://www.epicgames.com` and `https://account-public-service-prod.ol.epicgames.com`.

### 1.2.1 Account Public Service
  The base URL for this service is `https://account-public-service-prod.ol.epicgames.com`. Other URLs include `https://account-public-service-prod03.ol.epicgames.com` and `https://account-public-service-stage.ol.epicgames.com`.

  ### Authorization Header
  For the first service request, `/account/api/oauth/token`, requires an `Authorization` header to determine which game an authentication token should be generate for. The value passed in the header is formatted as `client_id:secret` and then encoded in Base64.

For example, say `TestGame` has client id `72f83226ab664739b635b1e318a635bc` and secret `ec684b8c687f479fadea3cb2ad83f5c6` - both these tokens would be put together as `72f83226ab664739b635b1e318a635bc:ec684b8c687f479fadea3cb2ad83f5c6` and then encoded to Base64, which gives `NzJmODMyMjZhYjY2NDczOWI2MzViMWUzMThhNjM1YmM6ZWM2ODRiOGM2ODdmNDc5ZmFkZWEzY2IyYWQ4M2Y1YzY=`. The result can then be used as an Authorization header, `Basic NzJmODMyMjZhYjY2NDczOWI2MzViMWUzMThhNjM1YmM6ZWM2ODRiOGM2ODdmNDc5ZmFkZWEzY2IyYWQ4M2Y1YzY=`.

  | Game | Client ID | Secret |
  | - | - | - |
  | Fortnite PC | ec684b8c687f479fadea3cb2ad83f5c6 | e1f31c211f28413186262d37a13fc84d |

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
