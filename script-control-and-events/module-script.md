# module script

### Module `script`

Functions for script execution control

Functions related to script execution control

#### Info:

* **Release**: 1.1.0
* **Author**: Mr. Doom

### [Functions](broken-reference)

| [on\_load (callback)](broken-reference)                   | Register a function to call upon loading your script                    |
| --------------------------------------------------------- | ----------------------------------------------------------------------- |
| [on\_init (callback)](broken-reference)                   | Register a function to call upon starting a run                         |
| [on\_internal\_event (event, callback)](broken-reference) | Register a function to call upon a specific internal event being called |

**on\_load (callback)**Register a function to call upon loading your script

#### Parameters:

*   callback function Callback function to register

    Your function will be called once upon loading the game (not upon starting a new run use on\_init for that)

    Functions will be called in the order they are registered, lua entry scripts are executed in the order they are defined in the hyperspace.xml, so if your mod was defined before another in Slipstream it'll load before the other mod.

    **Warning:** you can accidentally register your function multiple times and it will be called multiple times!

    Actually currently runs on `AcheivementTracker::LoadAchievementDescriptions` (right after most of Hyperspace initalizes XML stuff)

#### Usage:

* ```
  function myModInitializationCode()
    log("My code was run after the game started")
    if not _G["myModLoaded"] then
      _G["myModLoaded"] = true
    end
          if not _G["otherModLoaded"] then
      warningWindow("Warning! MyMod depends on OtherMod!")
    end
  end

  script.on_load(myModInitializationCode)
  ```

**on\_init (callback)**Register a function to call upon starting a run

#### Parameters:

*   callback function Callback function to register

    Your function will be called once upon starting a new run (and/or loading a run)

    Functions will be called in the order they are registered, lua entry scripts are executed in the order they are defined in the hyperspace.xml, so if your mod was defined before another in Slipstream it'll load before the other mod.

    **Warning:** you can accidentally register your function multiple times and it will be called multiple times!

    Currently happens on `ScoreKeeper::LoadGame` so you might need to check if your values are already initialized in your code

**on\_internal\_event (event, callback)**Register a function to call upon a specific internal event being called

#### Parameters:

* event [string](https://www.lua.org/manual/5.3/manual.html#6.4) Event name/identifier to hook, see ??? table for a full list of currently supported events.
*   callback function Callback function to register

    Your function will be called upon the specified event being triggered inside the game **These are internal events** not events as described in XML files, so these are events like functions internal to the game (like ship loading) and not events as in popups or encounters in the game. You can think of these as game engine events. See ??? for hooking gameplay events.

    Functions will be called in the order they are registered. **Warning:** you can accidentally register your function multiple times and it will be called multiple times!
