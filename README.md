<img width="862" height="611" alt="image" src="https://github.com/usernamethisorthat/VoltilsUI/blob/main/image.webp?raw=true" />











--------------------------------
<p align="center">
  <img src="https://img.shields.io/badge/Roblox-Luau-blue?style=flat-square&logo=roblox" alt="Roblox Luau">
  <img src="https://img.shields.io/badge/license-All%20Rights%20Reserved-red?style=flat-square" alt="All Rights Reserved">
</p>

# VoltisUI

This documentation is for VoltisUI by Voltis

## Loading the VoltisUI Library

```lua
local VoltisUI = loadstring(game:HttpGet("https://bloxvault.org/load/qLALM"))()
```

## Initializing the UI

```lua
local UI = VoltisUI:Init({
   title = "VoltisUI",
   company = "Voltis",
   DiscordInvite = "discord.gg/78yYmtaeg4",
   LogoIcon = "93061773121162",
   IntroSoundId = "rbxassetid://12221967",
   backgroundTransparency = 0,
   SelectorUserImages = true,
   Resizable = true,
   WindowMinSize = Vector2.new(360, 300),
   WindowMaxSize = Vector2.new(900, 620),
   InterfaceKey = Enum.KeyCode.RightShift,
   RainbowEnabled = true,
   Hints = {"Introducing you to VoltisUI!", "Join our Discord for Support"},
   KeySystem = false,
   KeySettings = {
      Title = "VoltisUI",
      Subtitle = "Key System",
      Note = "Join the Discord to get the key.",
      FileName = "VoltisUIKey",
      RememberKey = true,
      GrabKeyFromSite = false,
      ValidKeys = {"Voltis-123", "Voltis-67"},
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

## Split Sections

```lua
Main:EnableSplitSections({
   Sides = 2, -- set to 1 for one scrollable side
})

Main:NewSection("Autofarming", "Left")
Main:NewToggle("Auto Farm", false, function(enabled) end)
Main:NewSlider("Farm Radius", " studs", false, "/", {min = 25, max = 250, default = 75}, function(value) end)

Main:NewSection("Targeting", "Left")
Main:NewTextbox("Target", "", "Username...", "small", true, false, function(text) end)

Main:NewSection("Flying", "Right")
Main:NewToggle("Fly", false, function(enabled) end)

Main:NewSection("Misc", "Right")
Main:NewButton("Rejoin", function()
   UI:Rejoin()
end)
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

local PlayerSelector = Main:NewSelector("Players", UI:GetUserId(), {
   UI:GetUserId(),
   {Text = UI:GetUsername(), UserId = UI:GetUserId()},
}, function(option)
   print("Selected player:", option)
end)
```

## Creating a Slider

```lua
local Slider = Main:NewSlider("WalkSpeed", " studs", false, "/", {min = 16, max = 100, default = 16}, function(value)
   print("New speed:", value)
end)
```

## Creating a Color Picker

```lua
local ColorPicker = Main:NewColorPicker("ESP Color", Color3.fromRGB(255, 255, 255), function(color, transparency)
   print("Color:", color, "Transparency:", transparency)
end, 0)

ColorPicker:Set(Color3.fromRGB(255, 0, 0))
ColorPicker:SetTransparency(0.25)
ColorPicker:SetExpanded(false)
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
UI:Notify("VoltisUI loaded", 3, "success") -- types: "notification", "success", "alert", "error"
```

## Creating a Watermark

```lua
local Watermark = UI:Watermark("VoltisUI | " .. UI:GetUsername())
Watermark:SetText("VoltisUI | Ready")
Watermark:Hide()
Watermark:Show()
Watermark:Remove()
```

## Utility Methods

```lua
UI:SetTitle("New Title")
UI:SetCompany("New Company")
UI:SetLogoIcon("93061773121162")
UI:SetBackgroundTransparency(0.25)
UI:SetKeybind(Enum.KeyCode.LeftShift)
UI:OpenDiscordInvite()
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

`title`, `company`, `DiscordInvite`, `DiscordInviteCode`, `LogoIcon`, `IntroSoundId`, `IntroSoundVolume`, `RainbowEnabled`, `FieldOfView`, `InterfaceKey`, `KeySystem`, `KeySettings`, `Hints`, `Debug`, `transparency`, `backgroundTransparency`, `SelectorUserImages`, `backgroundColor`, `headerColor`, `companyColor`, `acientColor`, `darkGray`, `lightGray`, `Font`, `rainbowColors`
