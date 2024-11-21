# FLua Documentation || Setting Formats

## written by miller

FLua provides a way to configure scripts before full execution using Booleans or Integers.

## Setting Format

Each FLua setting is defined using the following format:

```lua
local flua_setting_<SettingName> = {"<Type>", <DefaultValue>}
```

### Example Settings

#### 1. Integer Settings

```lua
                     -- these numbers can be big, though not recomdended
local flua_setting_ANYNAME = {"int", 618157} -- Changing these will be prompted on execution.
local flua_setting_ANYNAME = {"int", 256} -- Changing these will be prompted on execution.
--                                    ^
--                              Default value if not changed
```

#### 2. Boolean Settings

```lua
local flua_setting_Enabled = {"bool", true}
```

**Note:** The data **must** be stored in tables, such as {"bool", true}. **Not** expressions/functions.

---
