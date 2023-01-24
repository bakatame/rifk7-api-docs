# 🚑 c\_client\_entity

## Example：

```lua
local local_player = engine.get_local_player()
local local_player_alive = local_player:get_netvar_int("m_lifeState") ~= 0
```

## Table：

|                          | Function Parameter                                   | Return Type                        | Description |
| ------------------------ | ---------------------------------------------------- | ---------------------------------- | ----------- |
| get\_netvar\_int         | `string` var                                         | `int`                              |             |
| get\_netvar\_float       | `string` var                                         | `float`                            |             |
| get\_netvar\_bool        | `string` var                                         | `bool`                             |             |
| get\_netvar\_string      | `string` var                                         | `string`                           |             |
| get\_netvar\_c\_vector3d | `string` var                                         | ``[`c_vector3d`](c\_vector3d.md)`` |             |
| get\_netvar\_handle      | `string` var                                         | `c_base_handle`                    |             |
| set\_netvar\_int         | (`string` var, `int` value)                          | `void`                             |             |
| set\_netvar\_float       | (`string` var, `float` value)                        | `void`                             |             |
| set\_netvar\_bool        | (`string` var, `bool` value)                         | `void`                             |             |
| set\_netvar\_string      | (`string` var, `string` value)                       | `void`                             |             |
| set\_netvar\_c\_vector3d | (`string` var, [`c_vector3d`](c\_vector3d.md) value) | `void`                             |             |
| is\_dormant              | `void`                                               | `bool`                             |             |
| get\_class\_id           | `void`                                               | `int`                              |             |
| get\_class\_name         | `void`                                               | `string`                           |             |
| is\_player               | `void`                                               | `bool`                             |             |
| is\_weapon               | `void`                                               | `bool`                             |             |
| get\_render\_origin      | `void`                                               | [`c_vector3d`](c\_vector3d.md)``   |             |
| get\_index               | `void`                                               | `int`                              |             |
