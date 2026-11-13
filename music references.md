# Welcome to the Music references.

This will tackle how disks work, how to make them,how to play them,and how to make songs out of them.

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

So instead of :

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

You can do this:
```javascript
const disk1 = harmony.createDiskH([
  { count: 7, note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
]);
```
Which would return the same thing but is shorted and takes much less time to write.

If you do want to append a disk after you used createDiskH,just add to the end of an object like you normally would (Add up all
the count values,then add 1.That is your key).

```javascript
const disk1 = harmony.createDiskH([
  { count: 7, note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
]);
disk[8]={note: "exp_collect", interval: 1500, volume: 1, pitch: 1 }
```
If you want to play the disk, use playDiskForAllH,playDiskForGroup,or playDiskSpaced

```javascript
  const disk1 = harmony.createDiskH([
  { count: 35, note: "step_stone2", interval: 250, volume: 1, pitch: 1 }
]);
  harmony.playDiskForAllH(disk1)
```


