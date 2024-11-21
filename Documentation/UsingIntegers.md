# Using Integers

---

````markdown
# Using Integer Settings

Integer settings allow you to modify properties of scripts.

### Example

```lua
local flua_setting_Speed = {"int", 69}
local flua_setting_JumpPower = {"int", 50} -- these options will be prompted to change on execution, if no input provided, will use the default int

game:GetService("Players").LocalPlayer.Character.Humanoid.WalkSpeed = flua_setting_Speed[2]
game:GetService("Players").LocalPlayer.Character.Humanoid.JumpPower = flua_setting_JumpPower[2]
```
````
