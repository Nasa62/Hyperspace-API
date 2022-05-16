# Events

### Module `Events`

Event names (in the table) and event callback methods & their arguments

From this you can see what events to reference in the script.on\_internal\_event callback registration function

### [Tables](broken-reference)

| [SDLKey](broken-reference) |   |
| -------------------------- | - |

### [Registerable Internal Events](broken-reference)

| [CApp::OnKeyDown (key)](broken-reference)                   | Called upon any keypress                     |
| ----------------------------------------------------------- | -------------------------------------------- |
| [CrewEquipBox::RemoveItem ()](broken-reference)             |                                              |
| [game\_tick (tickCount)](broken-reference)                  | Called every game tick.                      |
| [PlayerShip\_HullDamage (shipId, damage)](broken-reference) | Called upon hull damage to the player’s ship |

### Tables <a href="#tables" id="tables"></a>

**SDLKey**

#### Remarks:

* Move to defines module

#### Fields:

* UNKNOWN 0
* 0 30
* 1 31
* 2 32
* 3 33
* 4 34
* 5 35
* 6 36
* 7 37
* 8 38
* 9 39
* AT 40
* AMPERSAND 26
* ASTERISK 2A
* BACKQUOTE 60
* BACKSLASH 5C
* BACKSPACE 8
* BREAK 13E
* CAPSLOCK 12D
* CARET 5E
* CLEAR C
* COLON 3A
* COMMA 2C
* COMPOSE 13A
* DELETE 7F
* DOLLAR 24
* DOWN 112
* END 117
* EQUALS 3D
* ESCAPE 1B
* EURO 141
* EXCLAIM 21
* F1 11A
* F10 123
* F11 124
* F12 125
* F13 126
* F14 127
* F15 128
* F2 11B
* F3 11C
* F4 11D
* F5 11E
* F6 11F
* F7 120
* F8 121
* F9 122
* GREATER 3E
* HASH 24
* HELP 13B
* HOME 116
* INSERT 115
* KP0 100
* KP1 101
* KP2 102
* KP3 103
* KP4 104
* KP5 105
* KP6 106
* KP7 107
* KP8 108
* KP9 109
* KP\_PERIOD 10A
* KP\_DIVIDE 10B
* KP\_MULTIPLY 10C
* KP\_MINUS 10D
* KP\_PLUS 10E
* KP\_ENTER 10F
* KP\_EQUALS 110
* LALT 134
* LCTRL 132
* LEFT 114
* LEFTBRACKET 5B
* LEFTPAREN 28
* LESS 3C
* LMETA 136
* LSHIFT 130
* LSUPER 137
* MENU 13F
* MINUS 2D
* MODE 139
* NUMLOCK 12C
* PAGEDOWN 119
* PAGEUP 118
* PAUSE 13
* PERIOD 2E
* PLUS 2B
* POWER 140
* PRINTSCREEN 13C
* QUESTION 3F
* QUOTEDBL 22
* QUOTE 27
* RALT 133
* RCTRL 131
* RETURN D
* RIGHT 113
* RIGHTBRACKET 5D
* RIGHTPAREN 29
* RMETA 135
* RSHIFT 12F
* RSUPER 138
* SCROLLOCK 12E
* SEMICOLON 3B
* SLASH 2F
* SPACE 20
* SYSREQ 13D
* TAB 9
* UNDERSCORE 5F
* UNDO 142
* UP 111
* a 61
* b 62
* c 63
* d 64
* e 65
* f 66
* g 67Reference
* h 68
* i 69
* j 6A
* k 6B
* l 6C
* m 6D
* n 6E
* o 6F
* p 70
* q 71
* r 72
* s 73
* t 74
* u 75
* v 76
* w 77
* x 78
* y 79
* z 7A
* LAST 143

#### Usage:

* ```
  function MyCallback(key)
      if key == Defines.SDLKey.DELETE then
          print("Delete was pressed")
      end
  end

  script.on_internal_event("CApp::OnKeyDown", MyCallback)
  ```

### Registerable Internal Events <a href="#registerable_internal_events" id="registerable_internal_events"></a>

The functions below may be registered to script.on\_internal\_event by using the function’s name (in this documentation) as the event name but you name your actual handling function whatever you want.

#### Usage:

```
-- The CApp::OnKeyDown function in this documentation
-- shows us to expect a SDLKey entry as input and to
-- not return any value from this callback function.
-- It does not matter what we name the arguments.
function myCallback(keyPressed)
    if keyPressed == Defines.SDLKey.BACKSPACE then
        log("We saw them do it, they hit backspace")
    end
end
script.on_internal_event("CApp::OnKeyDown", myCallback)
```

**CApp::OnKeyDown (key)**Called upon any keypress across the entire game, but may not be specific to a certain window or input.

#### Parameters:

* key SDLKey

#### Returns:

1. nothing

**CrewEquipBox::RemoveItem ()**

#### Returns:

1. nothing

**game\_tick (tickCount)**Called every game tick. Probably a terrible idea for _**EVERYTHING EVER**_, will probably remove or never implement.

#### Parameters:

* tickCount uint64\_t

#### Returns:

1. nothing

**PlayerShip\_HullDamage (shipId, damage)**Called upon hull damage to the player’s ship

#### Parameters:

* shipId int the ID of the ship for now…
* damage int intended hull damage, negative values infer healing

#### Returns:

1. uint value of the hull, 0 and the ship explodes.
