# Flua
Flua is a Roblox scripting CLI tool

# FLua Documentation
## written by miller 
(better docs soon when home...)

FLua provides a way to configure scripts before full execution using Booleans or Integers.

## Setting Format

Each FLua setting is defined using the following format:

```lua
local flua_setting_<SettingName> = {"<Type>", <DefaultValue>}
```

### Example Settings

#### 1. Integer Settings

```lua
local flua_setting_Speed = {"int", 69} -- Changing these will be prompted on execution.
local flua_setting_JumpPower = {"int", 50} -- Changing these will be prompted on execution.
```

#### 2. Boolean Settings

```lua
local flua_setting_Enabled = {"bool", true}
```

**Note:** The data must be stored in tables, such as {"bool", true}. Not expressions/functions.

## Example Usage

### Integer Settings

Use integer settings to modify properties of scripts:

```lua
local flua_setting_Speed = {"int", 69}
local flua_setting_JumpPower = {"int", 50}

game:GetService("Players").LocalPlayer.Character.Humanoid.WalkSpeed = flua_setting_Speed[2]
game:GetService("Players").LocalPlayer.Character.Humanoid.JumpPower = flua_setting_JumpPower[2]
```

### Boolean Settings

Boolean settings can toggle features. If you execute a script that has a changeable value after execution, you can re-run the script to change the value; true becomes false and vice versa.

## Examples

### Printing Boolean Settings

```lua
-- Example for using and printing the FLua function.
local flua_setting_Enabled = {"bool", true}

print("Enabled:", flua_setting_Enabled[2]) -- Output: Enabled: true
```

```lua
local flua_setting_Enabled = {"bool", false}

print("Enabled:", flua_setting_Enabled[2]) -- Output: Enabled: false
```

### No-Clip Toggle Example

```lua
local flua_setting_Enabled = {"bool", true}

_G.__noclipToggleFlua = flua_setting_Enabled[2]

if not _G.__NOCLIPfluaEnabled then
_G.__NOCLIPfluaEnabled = true
local noclipParts = {}

    game:GetService("RunService").Stepped:Connect(function()
        for _, child in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
            if child:IsA("BasePart") then
                if child.CanCollide == true and not noclipParts[child] then
                    noclipParts[child] = true
                end

                if _G.__noclipToggleFlua then
                    child.CanCollide = false
                else
                    if noclipParts[child] then
                        child.CanCollide = true
                    end
                end
            end
        end
    end)
end
```
