local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/0x00A/Kavo-UI-Library/main/source.lua"))()
local window = library.CreateLib("Key System", "DarkTheme")

local correctKey = "Nerd Supported"  -- Ganti dengan kunci yang diinginkan
local accessGranted = false

local keyTab = window:NewTab("Key System")
local keySection = keyTab:NewSection("Enter Key to Access")

keySection:NewTextBox("Enter Key", "Input the key here", function(inputKey)
    if inputKey == correctKey then
        accessGranted = true
        library:Notify("Access Granted!", "Success")
    else
        library:Notify("Invalid Key!", "Try Again")
    end
end)


local mainTab = window:NewTab("Main")
local mainSection = mainTab:NewSection("Main Features")

if accessGranted then
    mainSection:NewButton("Secret Button", "This is a hidden feature", function()
        print("Secret Feature Activated!")
    end)
else
    mainSection:NewLabel("Access Denied. Enter the correct key first!")
end
