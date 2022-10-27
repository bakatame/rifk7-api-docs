# Events

## Function:

### on\_lua\_unload

**`hooks.on_lua_unload(function)`** <mark style="color:purple;">`:Void`</mark>

|              | Type           | Description                 |
| ------------ | -------------- | --------------------------- |
| **function** | **`function`** | Functions to trigger unload |

<pre class="language-lua"><code class="lang-lua"><strong>//Example #1
</strong><strong>
</strong><strong>function Unload()
</strong><strong>    menu_antiaim.set_pitch(0)
</strong><strong>end
</strong><strong>
</strong><strong>hooks.on_lua_unload(Unload)
</strong><strong>
</strong>//Example #2

hooks.on_lua_unload(function()
    menu_antiaim.set_pitch(0)
end)</code></pre>

### add\_hook

**`hooks.add_hook(event name, function)`** <mark style="color:purple;">`:Void`</mark>

|                | Type           | Description                 |
| -------------- | -------------- | --------------------------- |
| **event name** | **`string`**   | Name of the trigger event   |
| **function**   | **`function`** | Functions to trigger events |

```lua
//Example #1

function test() 
    if (engine.is_ingame() and engine.is_connected()) then         
        renderer.draw_text(renderer.get_center().x, renderer.get_center().y + 15, "choke me daddy", 255, 255, 255, 255, font_flags.centered_x); 
    end 
end 

hooks.add_hook("on_draw", test)

//Example #2

hooks.add_hook("on_draw", function()
    if (engine.is_ingame() and engine.is_connected()) then         
        renderer.draw_text(renderer.get_center().x, renderer.get_center().y + 15, "choke me daddy", 255, 255, 255, 255, font_flags.centered_x); 
    end
end)
```

## is\_button\_activeList of game events:

{% embed url="https://wiki.alliedmods.net/Counter-Strike:_Global_Offensive_Events" %}
Official CS:GO events
{% endembed %}

```lua
function test(event) 
    if(event ~= nil) then 
        print(event:get_name()); 
    end 
end 
  
hooks.add_hook("on_event", test);
```

## List of events:

### on\_draw

Fired every frame. Most functions from the renderer namespace can only be used here

```lua
function test() 
    if (engine.is_ingame() and engine.is_connected()) then         
        renderer.draw_text(renderer.get_center().x, renderer.get_center().y + 15, "choke me daddy", 255, 255, 255, 255, font_flags.centered_x); 
        renderer.draw_line_multicolored(renderer.get_center().x, renderer.get_center().y + 35, renderer.get_center().x + 40 * clientstate.get_choked_ticks() / 15.0, renderer.get_center().y + 35, 255, 255, 255, 255, 255, 255, 255, 0); 
        renderer.draw_line_multicolored(renderer.get_center().x, renderer.get_center().y + 35, renderer.get_center().x - 40 * clientstate.get_choked_ticks() / 15.0, renderer.get_center().y + 35, 255, 255, 255, 255, 255, 255, 255, 0);         
    end 
end 

hooks.add_hook("on_draw", test)
```

### on\_paint

Fired every frame.&#x20;

### on\_frame\_end

Fired every frame.&#x20;

### on\_level\_clear

on\_level\_init\_pre\_entity

### on\_event

Fired game events

#### 🔗 struct <mark style="color:blue;">`c_game_event`</mark>

|             | Type   | Description                            |
| ----------- | ------ | -------------------------------------- |
| get\_name   | string | Returns the name string of the event.  |
| get\_bool   | bool   | Returns the bool value of the event.   |
| get\_int    | int    | Returns the int value of the event.    |
| get\_float  | float  | Returns the float value of the event.  |
| get\_string | string | Returns the string value of the event. |
| set\_bool   | void   | Set the bool value of the event        |
| set\_int    | void   | Set the int value of the event         |
| set\_float  | void   | Set the float value of the event       |
| set\_string | void   | Set the string value of the event      |

### on\_drawmodel&#x20;

on drawing model&#x20;

#### 🔗 struct <mark style="color:blue;">`lua_dme`</mark>

|                  | Type                                            | Description |
| ---------------- | ----------------------------------------------- | ----------- |
| get\_entity      | [c\_client\_entity](class/c\_client\_entity.md) |             |
| get\_model\_name | string                                          |             |
| should\_override | bool                                            |             |
| get\_matrix      | [matrix3x4](class/c\_matrix3x4.md)              |             |

### on\_createmove

start of createmove

#### 🔗 struct <mark style="color:blue;">`c_user_cmd`</mark>

|                      | Type                                                | Description |
| -------------------- | --------------------------------------------------- | ----------- |
| get\_command\_number | int                                                 |             |
| get\_tick\_count     | int                                                 |             |
| get\_viewangles      | [c\_vector3d](class/c\_vector3d.md)                 |             |
| get\_forwardmove     | float                                               |             |
| get\_sidemove        | float                                               |             |
| get\_upmove          | float                                               |             |
| get\_buttons         | buttons                                             |             |
| add\_button          | function([buttons](enumerations/buttons.md) button) |             |
| remove\_button       | function([buttons](enumerations/buttons.md) button) |             |
| is\_button\_active   | function([buttons](enumerations/buttons.md) button) |             |
| get\_weaponselect    | int                                                 |             |
| get\_weaponsubtype   | int                                                 |             |
| get\_mousedx         | int                                                 |             |
| get\_mousedy         | int                                                 |             |

### on\_createmove\_pre\_antiaim

before antiaim

#### 🔗 struct <mark style="color:blue;">`lua_createmove`</mark>

|                   | Type                                          | Description |
| ----------------- | --------------------------------------------- | ----------- |
| cmd               | [c\_user\_cmd](events.md#struct-c\_user\_cmd) |             |
| ragebot\_shooting | bool                                          |             |

### on\_override\_view

override view - every frame

### on\_render\_view&#x20;

render view - every frame&#x20;

#### 🔗 struct <mark style="color:blue;">`c_view_setup`</mark>

|                     | Type                                | Description |
| ------------------- | ----------------------------------- | ----------- |
| get\_origin         | [c\_vector3d](class/c\_vector3d.md) |             |
| get\_angles         | [c\_vector3d](class/c\_vector3d.md) |             |
| get\_fov            | float                               |             |
| get\_fov\_viewmodel | float                               |             |

### on\_shot\_info&#x20;

on ragebot shot

🔗 struct <mark style="color:blue;">**`lua_shot_info`**</mark>

|                       | Type                                | Description |
| --------------------- | ----------------------------------- | ----------- |
| get\_start            | [c\_vector3d](class/c\_vector3d.md) |             |
| get\_end              | [c\_vector3d](class/c\_vector3d.md) |             |
| get\_target           | bool                                |             |
| get\_damage           | float                               |             |
| get\_damage\_override | float                               |             |
| get\_backtrack        | int                                 |             |
| get\_hitbox           | [hitbox](enumerations/hitbox.md)    |             |

### on\_hitscan&#x20;

on ragebot hitbox selection

🔗 struct <mark style="color:blue;">**`lua_hitscan`**</mark>

|                  | Type                                            | Description |
| ---------------- | ----------------------------------------------- | ----------- |
| get\_player      | [c\_client\_entity](class/c\_client\_entity.md) |             |
| should\_override | bool                                            |             |

### on\_multipoints&#x20;

on ragebot multipoint setup

🔗 struct <mark style="color:blue;">**`lua_multipoints`**</mark>

|                            | Type                                            | Description |
| -------------------------- | ----------------------------------------------- | ----------- |
| get\_player                | [c\_client\_entity](class/c\_client\_entity.md) |             |
| hitbox                     | [hitbox](enumerations/hitbox.md)                |             |
| should\_multipoint\_hitbox | bool                                            |             |
| should\_override           | bool                                            |             |
