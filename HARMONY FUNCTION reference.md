# WELCOME TO FUNCTION REFERENCES:
This page will work very similarly to the official bloxd.io api,and will be formatted the same way.

All functions will be in alphabetical order,use Ctrl f(or cmd f) to find them.

Use harmony.(function) to call a function(in the same way you would call an API function)

ex: harmony.setPlayerDbValueH(myId,"Speed",4) would set the db value Speed to 4
   ## calculateDiskPlayTimeH:
This calculates the Play Time of your disks with the formula 

-------------------------------------------------------

PlayTime= all Intervals(minus the last note)/1000

-------------------------------------------------------

See createDiskH to see how to create the "disks"

Also,see the music reference for more info
### Parameters:
| Parameter | Type | Description |
|-----------|------|-------------|
| disk | `object[]` |Disk you're checking the length of|
  ## createDiskH:
This creates a Disk

see the Music reference for more info
### Parameters:
| Parameter | Type | Description |
|-----------|------|-------------|
| groups | `object[]` |One object value in an array,formatted like { count: 125, note: "step_stone2", interval: 250,volume:1,pitch:1},see the music reference for more info|
  ## getLobbyDbValueH:
This is a modified version of api.getLobbyDbValue.

The main difference is that you can pass any value object type you want instead of just strings and numbers

See setLobbyDbValueP for how to set the value
### Parameters:
| Parameter | Type | Description |
|-----------|------|-------------|
| key | `string` | The name of the value you want to get|

   ## getPlayerDbValueH:
This is a modified version of api.getPlayerDbValue.

The main difference is that you can pass any value object type you want instead of just strings and numbers

See setPlayerDbValueP for how to set the value
### Parameters:
| Parameter | Type | Description |
|-----------|------|-------------|
| playerId | `string` |This is the Id of the player your value is associated with|
| key | `string` | The name of the value you want to get |

  ## isAliveH:
This is a modified version of api.isAlive.

The main difference is that it returns false if it cannot find your id,while in normal API it would crash

### Parameters:
| Parameter | Type | Description |
|-----------|------|-------------|
| id | `string` |This is the Id of the thing you're checking|
  ## playDiskForAllH:
This plays a Disk for all players in the server.

See the music references for more info
### Parameters:
| Parameter | Type | Description |
|-----------|------|-------------|
| disk | `object[]` |One object value in an array,formatted like { count: 125, note: "step_stone2", interval: 250,volume:1,pitch:1},see the music reference for more info|

## respawnMultiPlayersH:
This allows you to respawn multiple players in groups instead of 1 by 1
### Parameters:
| Parameter | Type | Description |
|-----------|------|-------------|
| respawnPos | `number[]` |Position of the players you are respawning|
| playersRespawned | `number` | The amount of players you want to respawn |

 ## setLobbyDbValueH:
This is a modified version of api.setLobbyDbValue.

The main difference is that you can pass any value object type you want instead of just strings and numbers

See getLobbyDbValueP for how to get the value
### Parameters:
| Parameter | Type | Description |
|-----------|------|-------------|
| key | `string` | The name of the value you want to get|

## setPlayerDbValueH:
This is a modified version of api.setPlayerDbValue.

The main difference is that you can pass any value object type you want instead of just strings and numbers

See setPlayerDbValueP for how to get the value
### Parameters:
| Parameter | Type | Description |
|-----------|------|-------------|
| playerId | `string` |This is the Id of the player your value is associated with|
| key | `string` | The name of the value you want to get|



