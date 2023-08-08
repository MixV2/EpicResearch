# List of MCPs
Quite a few games by Epic (and other companies) use the MCP in their game. They can then be used to complete operations such as getting the player's current level.

| Game | URL |
| - | - |
| Fortnite | https://fortnite-public-service-prod11.ol.epicgames.com/fortnite |
| Borderlands 3 | https://oak-public-service-prod.ol.epicgames.com/oak |

When the documentation shows an endpoint as containing `:namespace`, it means you need to combine the URLs by replacing `:namespace` in the endpoint URL with the MCP URL for your chosen MCP.

For example, combining [Get MCP Version](https://github.com/MixV2/EpicResearch/blob/master/docs/mcp/endpoints/get_mcp_version.md) for `Fortnite` with this would look like:
1) MCP Domain Name: https://fortnite-public-service-prod11.ol.epicgames.com/fortnite
2) Get MCP Version Endpoint: /:namespace/api/version
3) Final URL: https://fortnite-public-service-prod11.ol.epicgames.com/fortnite/api/version
