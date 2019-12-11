# 1. FortniteResearch
A compilation of research dedicated to the internal workings of Fortnite.

## 1.1 Contents

- [1. FortniteResearch](#1-fortniteresearch)
  - [1.1 Contents](#11-contents)
  - [1.2 Launch Parameters](#12-launchparameters)
  - [1.3 AntiCheats](#13-anticheats)

## 1.2 Launch Parameters
| Launch Parameter | Function |
| - | - |
| -skippatchcheck | Function unknown, could be related to checking for hotfixes. |
| -buildidoverride | Sets the build ID used for matchmaking. |
| -MCPRegion | Overrides the MCP region used for matchmaking (e.g NA-EAST). |
| -windowed | Starts the game in windowed mode. |
| -fullscreen | Starts the game in fullscreen mode. |
| -setres | Sets the resolution of the client. |
| -AUTH_LOGIN | Logs in with username (and password). Deprecated in recent versions. |
| -AUTH_PASSWORD | Logs in with password (and username). Deprecated in recent versions. |
| -AUTH_TYPE | Sets the type of authentication (e.g password, client_credentials). Deprecated in recent versions. |
| -noepicportal | Passed to the game if Fortnite wasn't started from the launcher. |
| -epicportal | Passed to the game if Fortnite was started from the launcher. |
| -epicapp | Defines the environment Fortinte should use (e.g. Prod, DevPlaytest, PublicTest). |
| -epicenv | Function unknown, related to networking. |
| -nomcp | Disables MCP. |

> Not all of these values will work on the latest build of Fortnite.

## 1.3 AntiCheats
Disclaimer: No help will be given with trying to bypass anticheat to use on Fortnite production, so don't bother asking.

Fortnite uses two anticheats (one at a time, though) - EasyAntiCheat and BattlEye. EasyAntiCheat can be forced by setting date and time ahead, whilst BattlEye can be forced by starting the game with `-noeac -fromfl=be`.

On versions before 11.00, anticheat can be entirely bypassed by using an old version of `FortniteLauncher.exe` and starting the game with `-ForceACP=0`. With anticheat bypassed (not on production), you can do very useful things such as directly read/writing to memory aswell as modifying INI files.
