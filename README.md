# APIP-bloxd.io-custom-API-library
Custom API library for the bloxd.io game engine.The goal of this is to add features that are lacking rework certain API statements

# HOW TO INSTALL IT:
  # index.js
  First,open up your world code,go to index.js and copy and paste this here:
  <img width="1365" height="753" alt="image" src="https://github.com/user-attachments/assets/b2545be2-0bc3-4dea-99f6-cd12e0f75b3d" />

  `import {ApiPClass} from './apip.js';const apip = new ApiPClass();`
  # apip.js
  Once you're done with the first step,make a new file called "apip.js"
  <img width="1365" height="753" alt="image" src="https://github.com/user-attachments/assets/8400d573-d921-4ede-9300-f540151f2461" />

  Copy and paste the code below into that file
 <details>
<summary>Click here to view the code</summary>

```python
export class ApiPClass { constructor() { } setLobbyDbValueP(key, value) { try { if (typeof value === "object" || Array.isArray(value) || typeof value === "boolean") { api.setLobbyDbValue(key, JSON.stringify(value)); } else if (typeof value === "string" || typeof value === "number") { api.setLobbyDbValue(key, value); } else if (typeof value === "bigint") { api.setLobbyDbValue(key, String(value)); } } catch (err) { throw new Error(err.message); } } getLobbyDbValueP(key) { try { const value = api.getLobbyDbValue(key); if (typeof value === "object" || Array.isArray(value) || typeof value === "boolean") { return JSON.parse(api.getLobbyDbValue(key)); } else if (typeof value === "string" || typeof value === "number") { return JSON.parse(api.getLobbyDbValue(key)); } else if (typeof value === "bigint") { return Number(api.getLobbyDbValue(key)); } } catch (err) { throw new Error(err.message); } } setPlayerDbValueP(playerId, key, value) { try { if (typeof value === "object" || Array.isArray(value) || typeof value === "boolean") { api.setPlayerDbValue(playerId, key, JSON.stringify(value)); } else if (typeof value === "string" || typeof value === "number") { api.setPlayerDbValue(playerId, key, value); } else if (typeof value === "bigint") { api.setPlayerDbValue(playerId, key, String(value)); } } catch (err) { throw new Error(err.message); } } getPlayerDbValueP(playerId, key) { try { const value = api.getPlayerDbValue(playerId, key); if (typeof value === "object" || Array.isArray(value) || typeof value === "boolean") { return JSON.parse(api.getPlayerDbValue(playerId, key)); } else if (typeof value === "string" || typeof value === "number") { return JSON.parse(api.getPlayerDbValue(playerId, key)); } else if (typeof value === "bigint") { return Number(api.getPlayerDbValue(playerId, key)); } } catch (err) { throw new Error(err.message); } } isAliveP(lifeformId) { try { return api.isAlive(lifeformId); } catch (err) { if (err.message.includes("Expected type: valid lifeform ID string")) { return false; } else { throw new Error(err.message); } } } respawnMultiPlayersP(respawnPos, playersRespawned) { try { for (let i = 0; i < playersRespawned; i++) { let pId = api.getPlayerIds()[i]; if (api.isAlive(pId) === false) { api.forceRespawn(pId, respawnPos); } } } catch (err) { throw new Error(err.message); } } }
```

</details>
should look something like this:
<img width="1365" height="753" alt="image" src="https://github.com/user-attachments/assets/b3490399-f71c-4048-89b2-350f7e7c71f7" />

Voila,now your ready to use it,go to API references to see how to use the library
