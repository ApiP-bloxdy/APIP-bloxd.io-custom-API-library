# Welcome to the Music references

This will tackle how disks work, how to make them, and how to play them.

## How do disks work?

"Disks" are an array of objects, each containing a note with instructions on how to play it.

What a disk might look like:

```javascript
const disk1=[
  0: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  1: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  2: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  3: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  4: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
]
```
However,manually writing them would take a ton of time,that's why we have createDiskH.

createDiskH allows you to dupe the same line over and over again

So instead of this

```javascript
const disk1=[
  0: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  1: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  2: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  3: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  4: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  5: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  6: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
  7: { note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
]
```

you can do this:
```javascript
const disk1 = harmony.createDiskH([
  { count: 7, note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
]);
```

