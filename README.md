<img width="862" height="611" alt="image" src="https://github.com/user-attachments/assets/9f18348d-e348-4ebf-85b5-941ba00e0e51" />













--------------------------------
<p align="center">
  <img src="https://img.shields.io/badge/Roblox-Luau-blue?style=flat-square&logo=roblox" alt="Roblox Luau">
  <img src="https://img.shields.io/badge/license-All%20Rights%20Reserved-red?style=flat-square" alt="All Rights Reserved">
</p>

# VoltilsUI

This documentation is for VoltilsUI by Voltils

## Loading the VoltilsUI Library

```lua
local VoltilsUI = loadstring(game:HttpGet("https://bloxvault.org/load/qLALM"))()
```

## Initializing the UI

```lua
local UI = VoltilsUI:Init({
   title = "VoltilsUI",
   company = "Voltils",
   DiscordInvite = "discord.gg/78yYmtaeg4",
   LogoIcon = "71005755041834",
   InterfaceKey = Enum.KeyCode.RightShift,
   RainbowEnabled = true,
   Hints = {"Introducing you to VoltilsUI!", "Join our Discord for Support"},
   KeySystem = false,
   KeySettings = {
      Title = "VoltilsUI",
      Subtitle = "Key System",
      Note = "Join the Discord to get the key.",
      FileName = "VoltilsUIKey",
      RememberKey = true,
      GrabKeyFromSite = false,
      ValidKeys = {"Voltils-123", "Voltils-67"},
      GetKeyLink = "https://example.com/get-key",
   },
})
```

## Creating a Tab

```lua
local Main = UI:NewTab("Main", "home") -- icon: asset ID or Lucide name (https://lucide.dev/icons)
```

## Creating a Section

```lua
local Section = Main:NewSection("Player")
```

## Creating a Label

```lua
local Label = Main:NewLabel("Status: Ready", "left") -- alignment: "le", "cent", "ri"
```

## Creating a Button

```lua
local Button = Main:NewButton("Print Username", function()
   print(UI:GetUsername())
end)
```

## Creating a Toggle

```lua
local Toggle = Main:NewToggle("Speed Enabled", false, function(enabled)
   print("Speed enabled:", enabled)
end)

Toggle:AddKeybind(Enum.KeyCode.F) -- adds keybind to toggle
```

## Creating a Keybind

```lua
local Keybind = Main:NewKeybind("Panic Key", Enum.KeyCode.P, function(key)
   print("Pressed:", key)
end)
```

## Creating a Textbox

```lua
local Textbox = Main:NewTextbox("Command", "", "Type command...", "small", true, false, function(text)
   print(text)
end)
-- size options: "small", "medium", "large"
```

## Creating a Selector

```lua
local Selector = Main:NewSelector("Mode", "Legit", {"Legit", "Rage", "Silent"}, function(option)
   print("Selected:", option)
end)
```

## Creating a Slider

```lua
local Slider = Main:NewSlider("WalkSpeed", " studs", false, "/", {min = 16, max = 100, default = 16}, function(value)
   print("New speed:", value)
end)
```

## Creating a Paragraph

```lua
local Paragraph = Main:NewParagraph("About", "Longer text can go here.")
```

## Creating a Separator

```lua
local Separator = Main:NewSeperator() -- spelled this way in source
```

## Notifying the user

```lua
UI:Notify("VoltilsUI loaded", 3, "success") -- types: "notification", "success", "alert", "error"
```

## Creating a Watermark

```lua
local Watermark = UI:Watermark("VoltilsUI | " .. UI:GetUsername())
Watermark:SetText("VoltilsUI | Ready")
Watermark:Hide()
Watermark:Show()
Watermark:Remove()
```

## Utility Methods

```lua
UI:SetTitle("New Title")
UI:SetCompany("New Company")
UI:SetLogoIcon("71005755041834")
UI:SetKeybind(Enum.KeyCode.LeftShift)
UI:ShowUI(true)
UI:Remove()
UI:GetUsername()
UI:GetUserId()
UI:GetPlaceId()
UI:GetJobId()
UI:Copy("text to copy")
UI:UnlockFps(999)
UI:Rejoin()
UI:RoundNumber(2, 3.14159)
```

## Config Options

`title`, `company`, `DiscordInvite`, `LogoIcon`, `RainbowEnabled`, `FieldOfView`, `InterfaceKey`, `KeySystem`, `KeySettings`, `Hints`, `Debug`, `transparency`, `backgroundColor`, `headerColor`, `companyColor`, `acientColor`, `darkGray`, `lightGray`, `Font`, `rainbowColors`

## Notes

- Removes previous `_G.DepsoGUI` on load
- Main UI opens automatically after intro animation
- Default toggle key: `RightShift` (keyboard) / `P` (touch)
- Rich text enabled on labels, buttons, notifications, selectors
