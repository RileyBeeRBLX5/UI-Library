# MySploit UI

## Booting the Library
```lua
local UILibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/wuhaz/UI-Librarys/main/MySploit.lua"))()
```

## Creating a Window
```lua
local MainUI = UILibrary.Load("MySploit")
```

## Creating a Tab
```lua
local FirstPage = MainUI.AddPage("Home")
```

## Creating a Section
```lua
local FirstSection = FirstPage.AddSection("Section 1")
```

## Creating a Label
```lua
local FirstLabel = FirstPage.AddLabel("this is a label")
```

## Creating a Button
```lua
local FirstButton = FirstPage.AddButton("Button", function()
print("Hello")
end)
```

## Creating a Toggle
```lua
local FirstToggle = FirstPage.AddToggle("Toggle", false, function(Value)
print(Value)
end)
```

## Creating a Slider
```lua
local FirstSlider = FirstPage.AddSlider("Slider", {Min = 0, Max = 255, Def = 50}, function(Value)
print(Value)
end)
```

## Creating a Color Picker
```lua
local FirstPicker = FirstPage.AddColourPicker("Colorpicker", "white", function(Value)
print(Value)
end)
```

## Creating a Keybind
```lua
local FirstKeybind = FirstPage.AddKeybind("Keybind", "E", function()
    print("Hello")
end)
```

## Creating a Textbox
```lua
local FirstInput = FirstPage.AddInput("Textbox", "Hi", function(text)
    print("User entered: " .. text)
end)
```

## Creating a Dropdown
```lua
local FirstDropdown = FirstPage.AddDropdown("Dropdown", {"Hello","Goodbye"}, function(Value)
print(Value)
end)
```
