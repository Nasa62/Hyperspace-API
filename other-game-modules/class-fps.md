---
description: An in-game class managing game frame timing speeds & simulation rate.
---

# Class FPS

### Class `FPS`

Global game timing information

Provides the global timing information. Primarily used for adjusting values to happen once per unit of time rather than once per frame which may be variable.

#### Usage:

* ```
  myOncePerSecondValue = 128
  myOncePerFrameStepValue = FPS.SpeedFactor * myOncePerSecondValue
  print(myOncePerFrameStepValue)
  ```

### [Fields](broken-reference)

| [FPS.float](broken-reference)       |                             |
| ----------------------------------- | --------------------------- |
| [FPS.OldTime](broken-reference)     |                             |
| [FPS.LastTime](broken-reference)    |                             |
| [FPS.SpeedFactor](broken-reference) | 1/fps inverse of framerate. |
| [FPS.NumFrames](broken-reference)   |                             |
| [FPS.Frames](broken-reference)      |                             |
| [FPS.speedLevel](broken-reference)  | Game simulation speed       |

**FPS.float**

* float RunningTime

**FPS.OldTime**

* OldTime double

**FPS.LastTime**

* LastTime double

**FPS.SpeedFactor** 1/fps inverse of framerate.

* SpeedFactor float Simulation speed of the game. Can be used to compute a stable timestep. Basically the faster the game is running the closer this number is to 0, it’s the inverse of the current framerate (1/fps) so if you have a method that runs every frame you can use this to adjust values appropriately.

**FPS.NumFrames**

* NumFrames int

**FPS.Frames**

* Frames int

**FPS.speedLevel** Game simulation speed

* speedLevel int This adjusts the game’s simulation rate, a value of 0 is normal speed. Higher values will cause the game to speedup so that 1 in-game second is faster than 1 real-world second. the console `SPEED` command sets this value and the speed hotkey just toggles this between 0 and whatever value was set. This is the only **read-write** value in this class.
