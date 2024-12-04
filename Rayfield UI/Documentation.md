# Rayfield UI
This documentation is for Rayfield Credit To Sirius And shlexware

## Booting the Rayfield Library
```lua
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
```




## Creating a Rayfield Window
```lua
local Window = Rayfield:CreateWindow({
   Name = "Rayfield Example Window",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "Rayfield Interface Suite",
   LoadingSubtitle = "by Sirius",
   Theme = "Default", -- Check https://docs.sirius.menu/rayfield/configuration/themes

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },

   Discord = {
      Enabled = false, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})
```

## Creating a Tab
```lua
local Tab = Window:CreateTab("Tab Example", 4483362458) -- Title, Image
```
*Lucide Icon Support*

**You can now also use Lucide Icons with Rayfield. To do so, replace the Image Id above 4483362458 with a string value of an icon name in Lucide Icons.**

```lua
local Tab = Window:CreateTab("Tab Example", "rewind")
```

**This will set the Tab icon to a rewind symbol from Lucide Icons.**

**All Lucide Icons Supported Lucide Icons**

**Credit to Lucide and Latte Softworks**

## Creating a Section
```lua
local Section = Tab:CreateSection("Section Example")
```

## Notifying the user
```lua
Rayfield:Notify({
   Title = "Notification Title",
   Content = "Notification Content",
   Duration = 6.5,
   Image = 4483362458,
   Actions = { -- Notification Buttons
      Ignore = {
         Name = "Okay!",
         Callback = function()
         print("The user tapped Okay!")
      end
   },
},
})
```
*Lucide Icon Support*

**You can now also use Lucide Icons with Rayfield. To do so, replace the Image Id above 4483362458 with a string value of an icon name in Lucide Icons.**

```lua
Rayfield:Notify({
   Title = "Notification Title",
   Content = "Notification Content",
   Duration = 6.5,
   Image = "rewind",
})
```

**This will set the icon to a rewind symbol from Lucide Icons.**

**All Lucide Icons Supported Lucide Icons**

**Credit to Lucide and Latte Softworks**

## Creating a Button
```lua
local Button = Tab:CreateButton({
   Name = "Button Example",
   Callback = function()
   -- The function that takes place when the button is pressed
   end,
})  
```

## Creating a toggle
```lua
local Toggle = Tab:CreateToggle({
   Name = "Toggle Example",
   CurrentValue = false,
   Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
   -- The function that takes place when the toggle is pressed
   -- The variable (Value) is a boolean on whether the toggle is true or false
   end,
})
```

## Creating a Color Picker
```lua
local ColorPicker = Tab:CreateColorPicker({
    Name = "Color Picker",
    Color = Color3.fromRGB(255,255,255),
    Flag = "ColorPicker1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        -- The function that takes place every time the color picker is moved/changed
        -- The variable (Value) is a Color3fromRGB value based on which color is selected
    end
})
```

## Creating a Slider
```lua
local Slider = Tab:CreateSlider({
   Name = "Slider Example",
   Range = {0, 100},
   Increment = 10,
   Suffix = "Bananas",
   CurrentValue = 10,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
   -- The function that takes place when the slider changes
   -- The variable (Value) is a number which correlates to the value the slider is currently at
   end,
})
```

## Creating An Adaptive Input (Textbox)
```lua
local Input = Tab:CreateInput({
   Name = "Input Example",
   PlaceholderText = "Input Placeholder",
   RemoveTextAfterFocusLost = false,
   Callback = function(Text)
   -- The function that takes place when the input is changed
   -- The variable (Text) is a string for the value in the text box
   end,
})
```

## Creating a Dropdown menu
```lua
local Dropdown = Tab:CreateDropdown({
   Name = "Dropdown Example",
   Options = {"Option 1","Option 2"},
   CurrentOption = {"Option 1"},
   MultipleOptions = false,
   Flag = "Dropdown1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Option)
   -- The function that takes place when the selected option is changed
   -- The variable (Option) is a table of strings for the current selected options
   end,
})
```

## Creating a Keybind
```lua
local Keybind = Tab:CreateKeybind({
   Name = "Keybind Example",
   CurrentKeybind = "Q",
   HoldToInteract = false,
   Flag = "Keybind1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Keybind)
   -- The function that takes place when the keybind is pressed
   -- The variable (Keybind) is a boolean for whether the keybind is being held or not (HoldToInteract needs to be true)
   end,
})
```

## Creating a Label (Rayfield)
```lua
local Label = Tab:CreateLabel("Label Example")
```
*Lucide Icon Support*

**You can now also use Lucide Icons with Rayfield. To do so, replace the Image Id above 4483362458 with a string value of an icon name in Lucide Icons.**

```lua
local Label = Tab:CreateLabel("Label Example", "rewind")
```
**This will set the icon to a rewind symbol from Lucide Icons.**

**All Lucide Icons Supported Lucide Icons**

**Credit to Lucide and Latte Softworks**

### Creating a paragraph (Rayfield)
```lua
local Paragraph = Tab:CreateParagraph({Title = "Paragraph Example", Content = "Paragraph Example"})
```

## Destroying the Interface
```lua
Rayfield:Destroy()
```

# NEW FEATURES

## Create A Divider
```lua
local Divider = Tab:CreateDivider()
```

## THEMES

# Themes

*All themes are beautifully designed to both display Rayfield in its' best form and allow more personality within each script, while retaining an easy experience for the developer*

# Using Themes

*To make use of Themes, either run Window.ModifyTheme('ThemeIdentifier'), or add an argument to the CreateWindow function named Theme and set the value (string) to whichever Theme Identifier you'd like to use.*

*To make use of Themes, either run Window.ModifyTheme('ThemeIdentifier'), or add an argument to the CreateWindow function named Theme and set the value (string) to whichever Theme Identifier you'd like to use.*

## LIST OF THEMES

## Themes
```lua
Theme Name - ThemeIdentifier

Default - Default
Amber Glow - AmberGlow
Amethyst - Amethyst
Bloom - Bloom
Dark Blue - DarkBlue
Green - Green
Light - Light
Ocean - Ocean
Serenity - Serenity
```

**CUSTOM THEME**
*You can also use your own custom theme as of Rayfield 1.53.*

*To do so, replace the ThemeIdentifier above (in either ModifyTheme or CreateWindow) with a table value of a theme table. An example of a theme table is below.*

# MAKING A CUSTOM THEME
```lua
{
    TextColor = Color3.fromRGB(240, 240, 240),

    Background = Color3.fromRGB(25, 25, 25),
    Topbar = Color3.fromRGB(34, 34, 34),
    Shadow = Color3.fromRGB(20, 20, 20),

    NotificationBackground = Color3.fromRGB(20, 20, 20),
    NotificationActionsBackground = Color3.fromRGB(230, 230, 230),

    TabBackground = Color3.fromRGB(80, 80, 80),
    TabStroke = Color3.fromRGB(85, 85, 85),
    TabBackgroundSelected = Color3.fromRGB(210, 210, 210),
    TabTextColor = Color3.fromRGB(240, 240, 240),
    SelectedTabTextColor = Color3.fromRGB(50, 50, 50),

    ElementBackground = Color3.fromRGB(35, 35, 35),
    ElementBackgroundHover = Color3.fromRGB(40, 40, 40),
    SecondaryElementBackground = Color3.fromRGB(25, 25, 25),
    ElementStroke = Color3.fromRGB(50, 50, 50),
    SecondaryElementStroke = Color3.fromRGB(40, 40, 40),
            
    SliderBackground = Color3.fromRGB(50, 138, 220),
    SliderProgress = Color3.fromRGB(50, 138, 220),
    SliderStroke = Color3.fromRGB(58, 163, 255),

    ToggleBackground = Color3.fromRGB(30, 30, 30),
    ToggleEnabled = Color3.fromRGB(0, 146, 214),
    ToggleDisabled = Color3.fromRGB(100, 100, 100),
    ToggleEnabledStroke = Color3.fromRGB(0, 170, 255),
    ToggleDisabledStroke = Color3.fromRGB(125, 125, 125),
    ToggleEnabledOuterStroke = Color3.fromRGB(100, 100, 100),
    ToggleDisabledOuterStroke = Color3.fromRGB(65, 65, 65),

    DropdownSelected = Color3.fromRGB(40, 40, 40),
    DropdownUnselected = Color3.fromRGB(30, 30, 30),

    InputBackground = Color3.fromRGB(30, 30, 30),
    InputStroke = Color3.fromRGB(65, 65, 65),
    PlaceholderColor = Color3.fromRGB(178, 178, 178)
}
```

# UPDATE FUNCTIONS

## Update Section
```lua
Section:Set("Section Example")
```

## Update Button
```lua
Button:Set("Button Example")
```

## Update Toggle
```lua
Toggle:Set(false)
```

## Update Color Picker
```lua
ColorPicker:Set(Color3.fromRGB(255,255,255)
```

## Update Slider
```lua
Slider:Set(10) -- The new slider integer value
```

## Update a Dropdown
```lua
Dropdown:Set({"Option 2"}) -- The new list of options
```

## Update a Keybind
```lua
Keybind:Set("RightCtrl") -- Keybind (string)
```

## Update a Label
```lua
Label:Set("Label Example")
```
**Update a Label (NEW)**
```lua
Label:Set("Label Example", 4483362458, Color3.fromRGB(255, 255, 255), false) -- Title, Icon, Color, IgnoreTheme
```

## Update a Paragraph
```lua
Paragraph:Set({Title = "Paragraph Example", Content = "Paragraph Example"})
```

## Update A Divider
```lua
Divider:Set(false) -- Whether the divider's visibility is to be set to true or false.
```

## Update A Input (Textbox)
```lua
Input:Set("New Text") -- The new input text value
```


# Check the value of an existing element

**To check the current value of an existing element, using the variable, you can do ElementName.CurrentValue, if it's a keybind or dropdown, you will need to use KeybindName.CurrentKeybind or DropdownName.CurrentOption You can also check it via the flags from Rayfield.Flags**

# Enabling Configuration Saving

*1. Enable ConfigurationSaving in the CreateWindow function
2. Choose an appropiate FileName in the CreateWindow function
3. Choose an unique flag identifier for each supported element you create
4. Place Rayfield:LoadConfiguration() at the bottom of all your code*
