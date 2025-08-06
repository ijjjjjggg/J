Load WindUI
Load WindUI with loadstring
Load latest version Recommended



local WindUI = loadstring(game:HttpGet("https://github.com/Footagesus/WindUI/releases/latest/download/main.lua"))()
Load selected version



local Version = "1.6.31"
local WindUI = loadstring(game:HttpGet("https://github.com/Footagesus/WindUI/releases/download/" .. Version .. "/main.lua"))()
Setting Library Optional

Set Notification Lower



WindUI:SetNotificationLower(true)
Set Font



WindUI:SetFont("rbxassetid://font-id-here")
Set Theme



WindUI:SetTheme("Dark")
Add Theme



WindUI:AddTheme({
    Name = "Dark",
    Accent = "#18181b",
    Dialog = "#18181b",
    Outline = "#FFFFFF",
    Text = "#FFFFFF",
    Placeholder = "#999999",
    Background = "#0e0e10",
    Button = "#52525b",
    Icon = "#a1a1aa",
})
Other

Get Themes



WindUI:GetThemes()
Get Current Theme



WindUI:GetCurrentTheme()
Get Window Transparency (true or false)



WindUI:GetTransparency()
Get Window Size (UDim2)



WindUI:GetWindowSize()

Window
Creating Window and Editing it
Creating Window



local Window = WindUI:CreateWindow({
    Title = "UI Title",
    Icon = "door-open",
    Author = "Example UI",
    Folder = "CloudHub",
    Size = UDim2.fromOffset(580, 460),
    Transparent = true,
    Theme = "Dark",
    Resizable = true,
    SideBarWidth = 200,
    Background = "", -- rbxassetid only
    BackgroundImageTransparency = 0.42,
    HideSearchBar = true,
    ScrollBarEnabled = false,
    User = {
        Enabled = true,
        Anonymous = true,
        Callback = function()
            print("clicked")
        end,
    },
    KeySystem = { -- <- ↓ remove this all, if you dont neet the key system
        Key = { "1234", "5678" },
        Note = "Example Key System.",
        Thumbnail = {
            Image = "rbxassetid://",
            Title = "Thumbnail",
        },
        URL = "https://github.com/Footagesus/WindUI",
        SaveKey = true,
    },
})
Set Background Image



Window:SetBackgroundImage("rbxassetid://id-here")
Set Background Image Transparency



Window:SetBackgroundImageTransparency(value: number) -- from 0  to 1
Set Toggle Key



Window:SetToggleKey(Enum.KeyCode.H)
Set Transparency



Window:ToggleTransparency(true)
Set Resizable



Window:IsResizable(false)
Edit OpenButton



Window:EditOpenButton({
    Title = "Open Example UI",
    Icon = "monitor",
    CornerRadius = UDim.new(0,16),
    StrokeThickness = 2,
    Color = ColorSequence.new( -- gradient
        Color3.fromHex("FF0F7B"), 
        Color3.fromHex("F89B29")
    ),
    OnlyMobile = false,
    Enabled = true,
    Draggable = true,
})
Edit Topbar Buttons

Disable Topbar Buttons



Window:DisableTopbarButtons({
    "Close", 
    "Minimize", 
    "Fullscreen",
})
Create Custom Topbar Buttons



--                        | Special name     | Icon     | Callback                         | Order
Window:CreateTopbarButton("MyCustomButton1", "bird",    function() print("clicked!") end,  990)

API

Window Options

Prop	Type	Default
KeySystem?	table	{}
User?	table	{}
ScrollBarEnabled?	boolean	false
HideSearchBar?	boolean	false
BackgroundImageTransparency?	number	0
Background?	string	nil
SideBarWidth?	number	200
Resizable?	boolean	true
Theme?	string	Dark
Transparent?	boolean	false
Size?	UDim2	UDim2.new(0,580,0,460)
Folder	string	nil
Author?	string	nil
IconThemed?	boolean	false
Icon?	string	nil
Title	string	UI Library
User Options

Prop	Type	Default
Callback?	function	nil
Anonymous?	boolean	false
Enabled	boolean	false
KeySystem Options

Prop	Type	Default
SaveKey?	boolean	false
URL?	string	nil
Thumbnail?	table	{}
Note?	string	nil
Key	table	{}
Thumbnail Options (inside KeySystem)

Prop	Type	Default
Title?	string	nil
Image	string	nil


Tab Section
Creating Section for the Tabs and Editing it
Creating Section for the Tabs



local Section = Window:Section({
    Title = "Section for the tabs",
    Icon = "bird",
    Opened = true,
})
How can I make it open/close?


API

Section Options

Prop	Type	Default
Opened?	boolean	false
IconThemed?	boolean	false
Icon?	string	nil
Title	string	Section


Tab
Creating Tab
Creating Tab



local Tab = Window:Tab({
    Title = "Tab Title",
    Icon = "bird",
    Locked = false,
})
Select Tab



Window:SelectTab(2) -- Number of Tab

API

Tab Options

Prop	Type	Default
Locked?	boolean	false
IconThemed?	boolean	false
Icon?	string	nil
Title	string	Tab



Dialog
Dialog component for WindUI
Creating Dialog



local Dialog = Window:Dialog({
    Icon = "bird",
    Title = "Dialog Title",
    Content = "Content Text",
    Buttons = {
        {
            Title = "Confirm",
            Callback = function()
                print("Confirmed!")
            end,
        },
        {
            Title = "Cancel",
            Callback = function()
                print("Cancelled!")
            end,
        },
    },
})
Show Dialog



Dialog:Show()
Close Dialog



Dialog:Close()

API

Dialog Options

Prop	Type	Default
Buttons	table	{}
Content	string	nil
Title	string	Dialog
Button Options (inside dialog)

Prop	Type	Default
Callback?	function	nil
Variant?	string	Primary
Icon?	string	nil
Title	string	Button



Popup
Creating Popup
Creating Popup



WindUI:Popup({
    Title = "Popup Title",
    Icon = "info",
    Content = "Popup content",
    Buttons = {
        {
            Title = "Cancel",
            Callback = function() end,
            Variant = "Tertiary",
        },
        {
            Title = "Continue",
            Icon = "arrow-right",
            Callback = function() end,
            Variant = "Primary",
        }
    }
})

API

Popup Options

Prop	Type	Default
Buttons	table	{}
Content	string	Content
IconThemed?	boolean	false
Icon?	string	nil
Title	string	Popup
Button Options (inside Popup)

Prop	Type	Default
Callback?	function	nil
Variant	string	Primary
Icon?	string	nil
Title	string	Button

Dialog

Button
Creating Button and Editing it
Creating Button



local Button = Tab:Button({
    Title = "Button",
    Desc = "Test Button",
    Locked = false,
    Callback = function()
        print("clicked")
    end
})
Set Title



Button:SetTitle("Title Example")
Set Description



Button:SetDesc("Description Example")
Lock Element



Button:Lock()
Unlock Element



Button:Unlock()
Destroy Element



Button:Destroy()

API

Button Options

Prop	Type	Default
Callback?	function	nil
Locked?	boolean	false
Desc?	string	nil
Title	string	Button


Code
Creating Code and Editing it
Creating Code



local Code = Tab:Code({
    Title = "Code",
    Code = [[print("Hello World!")]]
})
Set Code



Code:SetCode([[print("New code!")]])

API

Code Options

Prop	Type	Default
Code	string	nil
Title	string	Code


Colorpicker
Creating Colorpicker and Editing it
Creating Colorpicker



local Colorpicker = Tab:Colorpicker({
    Title = "Colorpicker",
    Desc = "Colorpicker Description",
    Default = Color3.fromRGB(0, 255, 0),
    Transparency = 0,
    Locked = false,
    Callback = function(color) 
        print("Background color: " .. tostring(color))
    end
})
Set Title



Colorpicker:SetTitle("Title Example")
Set Description



Colorpicker:SetDesc("Description Example")
Lock Element



Colorpicker:Lock()
Unlock Element



Colorpicker:Unlock()
Destroy Element



Colorpicker:Destroy()

API

Colorpicker Options

Prop	Type	Default
Callback?	function	nil
Locked?	boolean	false
Transparency	number	nil
Default	Color3	nil
Desc?	string	nil
Title	string	Colorpicker



Dropdown
Creating Dropdown and Editing it
Creating Dropdown

Multi Dropdown



local Dropdown = Tab:Dropdown({
    Title = "Dropdown (Multi)",
    Values = { "Category A", "Category B", "Category C" },
    Value = { "Category A" },
    Multi = true,
    AllowNone = true,
    Callback = function(option) 
        print("Categories selected: " .. game:GetService("HttpService"):JSONEncode(option)) 
    end
})
No multi Dropdown



local Dropdown = Tab:Dropdown({
    Title = "Dropdown (Multi)",
    Values = { "Category A", "Category B", "Category C" },
    Value = "Category A",
    Callback = function(option) 
        print("Category selected: " .. option) 
    end
})
Set Title



Dropdown:SetTitle("Title Example")
Set Description



Dropdown:SetDesc("Description Example")
Select value

* For default Dropdown 
* Dropdown:Select("Category B") 
*   
* For Multi Dropdown 
* Dropdown:Select({"Category B"}) 
*   
Refresh Values (Update)



Dropdown:Refresh({ "New Category A", "New Category B" })
Lock Element



Dropdown:Lock()
Unlock Element



Dropdown:Unlock()
Destroy Element



Dropdown:Destroy()

API

Dropdown Options

Prop	Type	Default
Callback?	function	nil
Locked?	boolean	false
Multi?	boolean	false
AllowNone?	boolean	false
Values	table	{}
Value	string or table (for multi)	nil
Desc?	string	nil
Title	string	Dropdown




Input
Creating Input and Editing it
Creating Input



local Input = Tab:Input({
    Title = "Input",
    Desc = "Input Description",
    Value = "Default value",
    InputIcon = "bird",
    Type = "Input", -- or "Textarea"
    Placeholder = "Enter text...",
    Callback = function(input) 
        print("text entered: " .. input)
    end
})
Set Title



Input:SetTitle("Title Example")
Set Description



Input:SetDesc("Description Example")
Set Input value



Input:Set("New value")
Set Input Placeholder



Input:SetPlaceholder("New Placeholder")
Lock Element



Input:Lock()
Unlock Element



Input:Unlock()
Destroy Element



Input:Destroy()

API

Input Options

Prop	Type	Default
Callback?	function	nil
Locked?	boolean	false
InputIcon?	string	nil
Type?	string	Input
Placeholder	string	nil
Value?	string	nil
Desc?	string	nil
Title	string	Input



Keybind
Creating Keybind and Editing it
Creating Keybind



local Keybind = Tab:Keybind({
    Title = "Keybind",
    Desc = "Keybind to open ui",
    Value = "G",
    Callback = function(v)
        Window:SetToggleKey(Enum.KeyCode[v])
    end
})
Set Title



Keybind:SetTitle("Title Example")
Set Description



Keybind:SetDesc("Description Example")
Lock Element



Keybind:Lock()
Unlock Element



Keybind:Unlock()
Destroy Element



Keybind:Destroy()

API

Keybind Options

Prop	Type	Default
Callback?	function	nil
Locked?	boolean	false
Value	string	F
Desc?	string	nil
Title	string	Keybind


Paragraph
Creating Paragraph and Editing it
Creating Paragraph



local Paragraph = Tab:Paragraph({
    Title = "Paragraph with Image, Thumbnail, Buttons",
    Desc = "Test Paragraph",
    Color = "Red",
    Image = "",
    ImageSize = 30,
    Thumbnail = "",
    ThumbnailSize = 80,
    Locked = false,
    Buttons = {
        {
            Icon = "bird",
            Title = "Button",
            Callback = function() print("1 Button") end,
        }
    }
})
Set Title



Paragraph:SetTitle("Title Example")
Set Description



Paragraph:SetDesc("DescriptionExample")
Destroy Element



Paragraph:Destroy()

API

Paragraph Options

Prop	Type	Default
Buttons?	table	{}
Locked?	boolean	false
ThumbnailSize?	number	80
Thumbnail?	string	nil
IconThemed?	boolean	false
ImageSize?	number	22
Image?	string	nil
Desc?	string	nil
Title	string	Paragraph
Button Options (inside paragraph)

Prop	Type	Default
Callback?	function	nil
Icon?	string	nil
Title	string	Button
Paragraph colors

Preview	Name	Hex
	Red	#e53935
	Orange	#f57c00
	Green	#43a047
	Blue	#039be5
	White	#ffffff
	Grey	#484848


Section
Creating Section and Editing it
Creating Section



local Section = Tab:Section({ 
    Title = "Section",
    TextXAlignment = "Left",
    TextSize = 17, -- Default Size
})
Set Title



Section:SetTitle("New Title Example")
Destroy Element



Section:Destroy()


Slider
Creating Slider and Editing it
Creating Slider



local Slider = Tab:Slider({
    Title = "Slider",
    
    -- To make float number supported, 
    -- make the Step a float number.
    -- example: Step = 0.1
    Step = 1,
    
    Value = {
        Min = 20,
        Max = 120,
        Default = 70,
    },
    Callback = function(value)
        print(value)
    end
})
Set Title



Slider:SetTitle("Title Example")
Set Description



Slider:SetDesc("Description Example")
Set Slider value



Slider:Set(42)
Lock Element



Slider:Lock()
Unlock Element



Slider:Unlock()
Destroy Element



Slider:Destroy()

API

Slider Options

Prop	Type	Default
Callback?	function	nil
Locked?	boolean	false
Step?	number	1
Value	table	{}
Desc?	string	nil
Title	string	Slider
Value Options (inside Slider)

Prop	Type	Default
Default	number	0
Max	number	nil
Min	number	0


Toggle
Creating Toggle and Editing it
Creating Toggle



local Toggle = Tab:Toggle({
    Title = "Toggle",
    Desc = "Toggle Description",
    Icon = "bird",
    Type = "Checkbox",
    Default = false,
    Callback = function(state) 
        print("Toggle Activated" .. tostring(state))
    end
})
Set Title



Toggle:SetTitle("Title Example")
Set Description



Toggle:SetDesc("Description Example")
Set Toggle value



Toggle:Set(true)
Lock Element



Toggle:Lock()
Unlock Element



Toggle:Unlock()
Destroy Element



Toggle:Destroy()

API

Toggle Options

Prop	Type	Default
Callback?	function	nil
Locked?	boolean	false
Icon?	string	nil
Type?	string	Toggle
Value?	boolean	false
Desc?	string	nil
Title	string	Toggle


