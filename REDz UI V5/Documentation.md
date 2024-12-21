# Redz UI V5
This documentation is for Redz UI V5 Credit To REDzHub

## Booting the Redz UI V5 Library
```lua
local redzlib = loadstring(game:HttpGet("https://raw.githubusercontent.com/RileyBeeRBLX5/UI-Library/refs/heads/main/REDz%20UI%20V5/Library.lua"))()
```




## Creating a Redz UI V5 Window
```lua
local Window = redzlib:MakeWindow({ Title = "Test", SubTitle = "hi",SaveFolder = "Redz UI V5" })
```

## Creating a Minimize Button
```lua
Window:AddMinimizeButton({
  Button = { Image = redzlib:GetIcon("rbxassetid://"),
    Size = UDim2.fromOffset(60, 60),
    BackgroundTransparency = 0 },
  Corner = { CornerRadius = UDim.new(0, 6) }
})
```

## Creating a Tab
```lua
local Tab = Window:MakeTab({"Example", "home"})
```

## Creating a Section
```lua
local Section = Tab:AddSection({"Section"})
```

## Creating a Button
```lua
Tab:AddButton({"test", function()
print("hi")
end})
```

## Creating a Toggle
```lua
local Toggle = Tab:AddToggle({
  Name = "Toggle",
  Default = false,
  Callback = function(Value)
  print("hello")
  end
})
```
With description
```lua
local Toggle = Tab:AddToggle({
  Name = "Toggle",
  Default = false,
  Description = "This is a <font color='rgb(88, 101, 242)'>Toggle</font>",
  Callback = function(Value)
  print("hello")
  end
})
```

## Creating a Paragraph
```lua
local Paragraph = Tab:AddParagraph({"Paragraph", "This is a Paragraph\nSecond Line"})
```

## Creating a Dialog
```lua
local Dialog = Window:Dialog({
    Title = "Dialog",
    Text = "This is a Dialog",
    Options = {
      {"Confirm", function()
        
      end},
      {"Maybe", function()
        
      end},
      {"Cancel", function()
        
      end}
    }
  })
end})
```

## Creating a Another Button
```lua
local Button = Tab:AddButton({
  Name = "Invisible Toggle",
  Description = "Makes the Toggles Invisible"
})
```
```lua
Button:Callback(Toggle1.Visible)
```
```lua
Button:Callback(Toggle2.Visible)
```

## Creating a Toggle 2
```lua
local Toggle = Tab:AddToggle({
  Name = "Toggle 1",
  Description = "This is a <font color='rgb(88, 101, 242)'>Toggle</font> Example",
  Default = false
})
```
```lua
local Toggle1 = Tab2:AddToggle({
  Name = "Toggle 1",
  Default = true
})
```
```lua
Toggle1:Callback(function(Value)
  Toggle2:Set(false)
end)
```
```lua
Toggle2:Callback(function(Value)
  Toggle1:Set(false)
end)
```
## Creating a Slider
```lua
Tab2:AddSlider({
  Name = "Slider",
  Min = 1,
  Max = 10,
  Increase = 1,
  Default = 5,
  Callback = function(Value)
  -- Your Script Here
  end
})
```
## Creating A Dropdown
```lua
local Dropdown = Tab:AddDropdown({
  Name = "Dropdown",
  Description = "Select The <font color='rgb(88, 101, 242)'>Number</font>",
  Options = {"one", "two", "three"},
  Default = "two",
  Flag = "DropdownTest",
  Callback = function(Value)
  print("choosed an number!")
  end
})
```

## Creating A Textbox
```lua
Tab:AddTextBox({
  Name = "Textbox",
  Description = "This Is A Textbox",
  Default = "Text",
  Callback = function(Value)
  -- Your Script Here
  end
})
```

## Select Tab
```lua
Window:SelectTab(Tab)
```

## Creating A Discord Invite
```lua
Tab:AddDiscordInvite({
  Name = "test",
  Logo = "rbxassetid://15298567397",
  Invite = "hi"
})
```
