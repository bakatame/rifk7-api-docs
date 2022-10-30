# 🏸 c\_cs\_player

## Example：

```lua
local local_player = engine.get_local_player()
local weapon = local_player:get_active_weapon()
```

## Table：

| Name                   | function parameter                                             | Return type                                 | Description |
| ---------------------- | -------------------------------------------------------------- | ------------------------------------------- | ----------- |
| is\_enemy              |                                                                | bool                                        |             |
| get\_abs\_origin       |                                                                | [c\_vector3d](c\_vector3d.md)               |             |
| get\_abs\_angles       |                                                                | [c\_vector3d](c\_vector3d.md)               |             |
| get\_active\_weapon    |                                                                | [c\_client\_entity\*](c\_client\_entity.md) |             |
| get\_inventory\_weapon | `int` index                                                    | [c\_client\_entity\*](c\_client\_entity.md) |             |
| get\_armor             |                                                                | int                                         |             |
| get\_defusing          |                                                                | bool                                        |             |
| get\_duck\_amount      |                                                                | float                                       |             |
| get\_duck\_speed       |                                                                | float                                       |             |
| get\_flag              | ``[`player_flags`](../enumerations/player\_flags.md) flag      | bool                                        |             |
| get\_health            |                                                                | int                                         |             |
| has\_defuser           |                                                                | bool                                        |             |
| is\_scoped             |                                                                | bool                                        |             |
| has\_helmet            |                                                                | bool                                        |             |
| has\_heavy\_armor      |                                                                | bool                                        |             |
| get\_pose\_parameter   | ``[`poses`](../enumerations/poses.md) parameter                | float                                       |             |
| set\_pose\_parameter   | ([`poses`](../enumerations/poses.md) parameter  `float` value) | float                                       |             |
| get\_velocity          |                                                                | [c\_vector3d](c\_vector3d.md)               |             |
| get\_place\_name       |                                                                | std::string                                 |             |
