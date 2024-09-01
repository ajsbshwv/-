local OrionLib = loadstring(game:HttpGet("https://pastebin.com/raw/jrdKakD6"))()

local Window = OrionLib:MakeWindow({Name = "通用脚本", HidePremium = false, SaveConfig = false, IntroText = "注入器："..identifyexecutor(), ConfigFolder = "通用脚本"})

OrionLib:MakeNotification({
    Name = "脚本中心",
    Content = "作者:小小鱼",
    Image = "rbxassetid://4483345998",
    Time = 6
})

local player = Window:MakeTab({
    Name = "你好",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

player:AddTextbox({
    Name = "移动速度",
    Default = "",
    TextDisappear = true,
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
    end
})

player:AddTextbox({
    Name = "跳跃高度",
    Default = "",
    TextDisappear = true,
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.JumpPower = Value
    end
})

player:AddToggle({
    Name = "穿墙",
    Default = false,
    Callback = function(Value)
        if Value then
            Noclip = true
            Stepped = game.RunService.Stepped:Connect(function()
                if Noclip == true then
                    for a, b in pairs(game.Workspace:GetChildren()) do
                        if b.Name == game.Players.LocalPlayer.Name then
                            for i, v in pairs(game.Workspace[game.Players.LocalPlayer.Name]:GetChildren()) do
                                if v:IsA("BasePart") then
                                    v.CanCollide = false
                                end
                            end
                        end
                    end
                else
                    Stepped:Disconnect()
                end
            end)
        else
            Noclip = false
        end
    end
})

player:AddButton({
    Name = "飞行",
    Callback = function()
          loadstring(game:HttpGet("https://pastebin.com/raw/U27yQRxS"))()
      end
})

player:AddButton({
    Name = "偷别人物品栏",
    Callback = function()
          --Copy And Paste:
    for i,v in pairs (game.Players:GetChildren()) do
    wait()
    for i,b in pairs (v.Backpack:GetChildren()) do
    b.Parent = game.Players.LocalPlayer.       Backpack
    end
    end
      end
})

local other = Window:MakeTab({
    Name = "其他",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

other:AddButton({
    Name = "跟踪玩家",
    Callback = function()
          loadstring(game:HttpGet("https://pastebin.com/raw/F9PNLcXk"))()
      end
})

other:AddToggle({
    Name = "夜视",
    Default = false,
    Callback = function(Value)
        if Value then
            game.Lighting.Ambient = Color3.new(1, 1, 1)
        else
            game.Lighting.Ambient = Color3.new(0, 0, 0)
        end
    end
})


local about = Window:MakeTab({
    Name = "教学",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

other:AddButton({
    Name = "动感星期五",
    Callback = function()
          loadstring(game:HttpGet("https://scriptblox.com/raw/XMAS-Event-or-Funky-Friday-Auto-Player-Mobile-6721"))()
      end
})

local about = Window:MakeTab({
    Name = "关于",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

OrionLib:Init()
