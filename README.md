--carregar biblioteca


local Window = Fluent:CreateWindow({
    Title = "Baruk " .. Fluent.Version,
    TabWidth = 160, Size = UDim2.fromOffset(580, 460), Theme = "Dark"
})

local Tabs = {
    Main = Window:AddTab({ Title = "Scripts" }),
    Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
}
--paragráfos
Tabs.Main:AddParagraph({ Title = "Baruk o mais belo", Content = "This is a paragraph.\nSecond line!" })
--botôes
Tabs.Main:AddButton({ Title = "Baruk o mais belo", Callback = function()
     loadstring(game:HttpGet("https://github.com/Hosvile/InfiniX/releases/latest/download/main.lua", true)) end })
