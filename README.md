# HARMONY-bloxd.io-custom-API-library
Custom API library for the bloxd.io game engine.The goal of this is to add features that are lacking rework certain API statements

# HOW TO INSTALL IT:
  # index.js
  First,open up your world code,go to index.js and copy and paste this here:


  `import {ApiPClass} from './apip.js';const harmony = new ApiPClass();`
  <img width="1365" height="767" alt="image" src="https://github.com/user-attachments/assets/1f8681e3-db7f-4273-89cb-f18ede8ab824" />
  should look something like this
  # apip.js
  Once you're done with the first step,make a new file called "apip.js"
  <img width="1365" height="753" alt="image" src="https://github.com/user-attachments/assets/8400d573-d921-4ede-9300-f540151f2461" />

  Copy and paste the code below into that file
 <details>
<summary>Click here to view the code</summary>

```javascript
import { setTimeout } from "@plugins/helpers"; export class ApiPClass { constructor() {} setLobbyDbValueH(key, value) { try { if ( typeof value === "object" || Array.isArray(value) || typeof value === "boolean" ) { api.setLobbyDbValue(key, JSON.stringify(value)); } else if (typeof value === "string" || typeof value === "number") { api.setLobbyDbValue(key, value); } else if (typeof value === "bigint") { api.setLobbyDbValue(key, String(value)); } } catch (err) { throw new Error(err.message); } } getLobbyDbValueH(key) { try { const value = api.getLobbyDbValue(key); if ( typeof value === "object" || Array.isArray(value) || typeof value === "boolean" ) { return JSON.parse(api.getLobbyDbValue(key)); } else if (typeof value === "string" || typeof value === "number") { return api.getLobbyDbValue(key); } else if (typeof value === "bigint") { return Number(api.getLobbyDbValue(key)); } } catch (err) { throw new Error(err.message); } } setPlayerDbValueH(playerId, key, value) { try { if ( typeof value === "object" || Array.isArray(value) || typeof value === "boolean" ) { api.setPlayerDbValue(playerId, key, JSON.stringify(value)); } else if (typeof value === "string" || typeof value === "number") { api.setPlayerDbValue(playerId, key, value); } else if (typeof value === "bigint") { api.setPlayerDbValue(playerId, key, String(value)); } } catch (err) { throw new Error(err.message); } } getPlayerDbValueH(playerId, key) { try { const value = api.getPlayerDbValue(playerId, key); if ( typeof value === "object" || Array.isArray(value) || typeof value === "boolean" ) { return JSON.parse(api.getPlayerDbValue(playerId, key)); } else if (typeof value === "string" || typeof value === "number") { return api.getPlayerDbValue(playerId, key); } else if (typeof value === "bigint") { return Number(api.getPlayerDbValue(playerId, key)); } } catch (err) { throw new Error(err.message); } } isAliveH(lifeformId) { try { return api.isAlive(lifeformId); } catch (err) { if (err.message.includes("Expected type: valid lifeform ID string")) { return false; } else { throw new Error(err.message); } } } respawnMultiPlayersH(respawnPos, playersRespawned) { try { for (let i = 0; i < playersRespawned; i++) { let pId = api.getPlayerIds()[i]; if (api.isAlive(pId) === false) { api.forceRespawn(pId, respawnPos); } } } catch (err) { throw new Error(err.message); } } playDiskForAllH(disk) { try { const playerIds = api.getPlayerIds(); const diskKeys = Object.keys(disk); for (let i = 0; i < playerIds.length; i++) { let pId = playerIds[i]; let totalDelay = 0; for (let j = 0; j < diskKeys.length; j++) { let key = diskKeys[j]; let diskNote = disk[key].note; let diskInterval = disk[key].interval; let diskVolume = disk[key].volume; let diskPitch = disk[key].pitch; setTimeout(() => { api.playSound(pId, diskNote, diskVolume, diskPitch); }, totalDelay); totalDelay += diskInterval; } } } catch (err) { throw new Error(err.message); } } createDiskH(groups) { try { let index = 0; return Object.fromEntries( groups.flatMap(({ count, ...config }) => Array.from({ length: count }, () => [index++, { ...config }]) ) ); } catch (err) { throw new Error(err.message); } } calculateDiskPlayerTimeH(disk) { const items = Object.values(disk); if (items.length === 0) return 0; const totalMs = items .slice(0, -1) .reduce((total, item) => total + item.interval, 0); return totalMs / 1000; } }

```

</details>
should look something like this(it'll be way longer):
<img width="1365" height="753" alt="image" src="https://github.com/user-attachments/assets/b3490399-f71c-4048-89b2-350f7e7c71f7" />

Voila,now your ready to use it,go to HARMONY FUNCTION references to see how to use the library
