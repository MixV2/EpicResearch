# 1. EpicResearch
A compilation of research dedicated to the internal workings of Epic's services.

## 1.1 Contents

- [1. EpicResearch](#1-epicresearch)
  - [1.1 Contents](#11-contents)
  - [1.2 Authentication](#12-authentication)
    - [1.2.1 Authentication Flow](#121-authentication-flow)
    - [1.2.2 Account Public Service](#122-account-public-service)

## 1.2 Authentication
Authentication related requests use both `https://www.epicgames.com` and `https://account-public-service-prod.ol.epicgames.com`.

### 1.2.1 Authentication Flow
1. Get an XSRF token.
- Request:
```http
GET https://www.epicgames.com/id/csrf HTTP/1.1
Host: www.epicgames.com
Cookie: ...
```

- Response:
```http
HTTP/1.1 204 No Content
Access-Control-Allow-Credentials: true
Set-Cookie: ...
```
Make sure you have a cookie jar setup so the `Cookie` header carries over to every single request.

### 1.2.2 Account Public Service
  The base URL for this service is `https://account-public-service-prod.ol.epicgames.com`. Other URLs include `https://account-public-service-prod03.ol.epicgames.com`, `https://account-public-service-prod-m.ol.epicgames.com` and `https://account-public-service-stage.ol.epicgames.com`.
  
An example service request used for getting an access token:
```http
POST https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token HTTP/1.1
Authorization: basic MzhkYmZjMzE5NjAyNGQ1OTgwMzg2YTM3YjdjNzkyYmI6YTYyODBiODctZTQ1ZS00MDliLTk2ODEtOGYxNWViN2RiY2Y1
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials
```

  ### Authorization Header
  For the first service request, `/account/api/oauth/token`, requires an `Authorization` header to determine which game an authentication token should be generate for. The value passed in the header is formatted as `client_id:secret` and then encoded in Base64.
  
  | Game | Client ID | Secret |
  | - | - | - |
  | Fortnite PC | ec684b8c687f479fadea3cb2ad83f5c6 | e1f31c211f28413186262d37a13fc84d |
  | Fortnite iOS | 3446cd72694c4a4485d81b77adbb2141 | 9209d4a5e25a457fb9b07489d313b41a |
  | Fortnite Android | 3f69e56c7649492c8cc29f1af08a8a12 | b51ee9cb12234f50a69efa67ef53812e |
  | Fortnite China | efe3cbb938804c74b20e109d0efc1548 | 6e31bdbae6a44f258474733db74f39ba |
  | Kairos PC | 5b685653b9904c1d92495ee8859dcb00 | 7Q2mcmneyuvPmoRYfwM7gfErA6iUjhXr |
  | Kairos iOS | 61d2f70175e84a6bba80a5089e597e1c | FbiZv3wbiKpvVKrAeMxiR6WhxZWVbrvA |
  | Kairos Android | 0716a69cb8b2422fbb2a8b0879501471 | cGthdfG68tyE7M3ZHMu3sXUBwqhibKFp |
  | Launcher PC | 34a02cf8f4414e29b15921876da36f9a | daafbccc737745039dffe53d94fc76cf |
  | Launcher Android | 38dbfc3196024d5980386a37b7c792bb | a6280b87-e45e-409b-9681-8f15eb7dbcf5 |

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
