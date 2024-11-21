## Examples Booleans

# written by miller

```lua
local flua_setting_Enabled = {"bool", true}
--                              ^       ^ default value
-- Boolean, true/false statements are used primarily i dunno if you can do text ill check ltr
```

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

### No-Clip Example

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
