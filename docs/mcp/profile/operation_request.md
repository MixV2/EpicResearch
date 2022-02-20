# Operation Request
To perform an operation, you must send a `POST` request to the MCP with the payload that the operation requires.  
You must also be authenticated with the correct client.

## Template
An operation request looks like:
- URL: `:host/:namespace/api/game/v2/profile/:accountID/client/:operation?profileId=:profile&rvn=-1`
- Method: `POST`

Some operations will also require a JSON body, which can be found in the [list of operations](https://github.com/MixV2/EpicResearch/tree/master/docs/mcp/profile/operations).  
Keep in mind that `client` is not present on all requests for some MCPs (e.g. Battle Breakers).

## Example Operation
Here's an example of the HTTP request needed to execute operation [SetMtxPlatform](https://github.com/MixV2/EpicResearch/blob/master/docs/mcp/profile/operations/SetMtxPlatform.md) for profile `athena` on Fortnite's MCP:
```http
POST https://fortnite-public-service-prod11.ol.epicgames.com/fortnite/api/game/v2/profile/0123456789abcdef/client/SetMtxPlatform?profileId=athena&rvn=-1 HTTP/1.1
Content-Type: application/json
Authorization: Bearer eg1~valid_auth_token

{
    "newPlatform": "EpicPC"
}
```
