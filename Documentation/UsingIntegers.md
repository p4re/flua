# flua Documentation || Using Integers

## written by miller

Integer settings allow you to modify properties of scripts. These options will prompt you to change the value on execution. If no input is provided, the default integer will be used.

## Example: Changing WalkSpeed and JumpPower

```lua
local flua_setting_Speed = {"int", 69} --Speed defaults to 69. You can adjust it when the script is executed.
local flua_setting_JumpPower = {"int", 50} -- JumpPower defaults to 50. Adjust it similarly upon execution.

game:GetService("Players").LocalPlayer.Character.Humanoid.WalkSpeed = flua_setting_Speed[2] -- gets int value
game:GetService("Players").LocalPlayer.Character.Humanoid.JumpPower = flua_setting_JumpPower[2] -- gets int value
```
