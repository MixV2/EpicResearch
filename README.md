# 1. FortniteResearch
A compilation of research dedicated to the internal workings of Fortnite.

## 1.1 Contents

- [1. FortniteResearch](#1-fortniteresearch)
  - [1.1 Contents](#11-contents)
  - [1.2 Authentication](#12-authentication)

## 1.2 Authentication
Authentication related requests use both `https://www.epicgames.com` and `https://account-public-service-prod.ol.epicgames.com`.

### 1.2.1 Account Public Service
  The base URL for this service is `https://account-public-service-prod.ol.epicgames.com`. Other URLs include `https://account-public-service-prod03.ol.epicgames.com` and `https://account-public-service-stage.ol.epicgames.com`.

  ### Grant Types
  Grant types are used to determine what type of authentication request is being sent. The most used and useful grant types are 
  `exchange_code`, `refresh_token` and `client_credentials`.
  
  List of grant types:
    - `password`, takes username & password (deprecated)
    - `external_auth`, takes external auth type (defaults to internal) and an external auth token
    - `device_auth`, takes account id, device id & secret
    - `authorization_code`, takes a code
    - `exchange_code`, takes an exchange code
    - `refresh_token`, takes a refresh token
    - `otp`, takes a two factor auth challenge
    - `client_credentials`
