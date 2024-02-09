local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")


local Frame = Instance.new("Frame")
Frame.Size = UDim2.new(0, 400, 0, 300)
Frame.Position = UDim2.new(0.5, 0, 0.5, 0)
Frame.AnchorPoint = Vector2.new(0.5, 0.5)
Frame.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
Frame.BorderSizePixel = 0
Frame.Active = true
Frame.Draggable = true
Frame.Parent = ScreenGui

local FrameCorner = Instance.new("UICorner")
FrameCorner.CornerRadius = UDim.new(0, 10)
FrameCorner.Parent = Frame

local Close = Instance.new("TextButton")
Close.Size = UDim2.new(0, 40, 0, 40)
Close.Position = UDim2.new(1, -40, 0, 0)
Close.BackgroundTransparency = 1
Close.Text = "×"
Close.TextScaled = true
Close.TextColor3 = Color3.fromRGB(150, 150, 150)
Close.Parent = Frame
Close.MouseButton1Click:Connect(function()
   ScreenGui:Destroy()
end)



local SafeSpot = Instance.new("Part", workspace)

SafeSpot.Position = Vector3.new(-1860.61,-399.9,927.21)

SafeSpot.Name = "Vip"

SafeSpot.Size = Vector3.new(0,0.1,0)

SafeSpot.Anchored = true

SafeSpot.Transparency = 1


local SafeSpot = Instance.new("Part", workspace)

SafeSpot.Position = Vector3.new(-1920.71,-399.9,929.66)

SafeSpot.Name = "Laaabby"

SafeSpot.Size = Vector3.new(0,0.1,0)

SafeSpot.Anchored = true

SafeSpot.Transparency = 1


local SafeSpot = Instance.new("Part", workspace)

SafeSpot.Position = Vector3.new(-0.81,1,-7.31)

SafeSpot.Name = "Game"

SafeSpot.Size = Vector3.new(0,0.1,0)

SafeSpot.Anchored = true

SafeSpot.Transparency = 1

local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local VirtualUser = game:GetService("VirtualUser")

local LocalPlayer = Players.LocalPlayer

getgenv().Settings = {
    Win = false,
    Rebirth = false,
}

function getHash()
    for _, v in pairs(game:GetService("Workspace").PlayerTycoons:GetDescendants()) do
        if v:IsA("ObjectValue") and v.Name == "Owner" then
            if tostring(v.Value) == game.Players.LocalPlayer.Name then
                return (v.Parent.Parent.Name)
            end
        end
    end
end

local Settings = {
    Names = false,
}
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local Camera = game:GetService("Workspace").CurrentCamera
local Players = game:GetService("Players")
local Player = Players.LocalPlayer
local Mouse = Player:GetMouse()

local msg = Instance.new("Message",workspace)
msg.Text = "欢迎使用龙脚本付费版本！"
wait(1.8)
msg:Destroy()

local msg = Instance.new("Message",workspace)
msg.Text = "制作者:龙叔 支持60款游戏"
wait(1.8)
msg:Destroy()

local msg = Instance.new("Message",workspace)
msg.Text = "更新公告: 射击光束模拟器"
wait(3)
msg:Destroy()

local NotificationHolder = loadstring(game:HttpGet("https://raw.githubusercontent.com/BocusLuke/UI/main/STX/Module.Lua"))() 
 local Notification = loadstring(game:HttpGet("https://raw.githubusercontent.com/BocusLuke/UI/main/STX/Client.Lua"))() 

 wait(1) 
 Notification:Notify( 
     {Title = "龙叔", Description = "正在加载"}, 
     {OutlineColor = Color3.fromRGB(80, 80, 80),Time = 5, Type = "image"}, 
     {Image = "http://www.roblox.com/asset/?id=4335482575", ImageColor = Color3.fromRGB(255, 84, 84)} 
 ) 
 wait(2) 
 Notification:Notify( 
     {Title = "龙叔", Description = "准备好了！"}, 
     {OutlineColor = Color3.fromRGB(80, 80, 80),Time = 5, Type = "image"}, 
     {Image = "http://www.roblox.com/asset/?id=4335482575", ImageColor = Color3.fromRGB(255, 84, 84)} 
 )
 wait(0.4)

local OrionLib = loadstring(game:HttpGet("https://shz.al/~dito-wooooooooo/Ditoo-ui/I-GOT-NO-TIME-TO-LOSE-RA-TATATA"))()
local LBLG = Instance.new("ScreenGui", getParent)
local LBL = Instance.new("TextLabel", getParent)
local player = game.Players.LocalPlayer

LBLG.Name = "LBLG"
LBLG.Parent = game.CoreGui
LBLG.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
LBLG.Enabled = true
LBL.Name = "LBL"
LBL.Parent = LBLG
LBL.BackgroundColor3 = Color3.new(1, 1, 1)
LBL.BackgroundTransparency = 1
LBL.BorderColor3 = Color3.new(0, 0, 0)
LBL.Position = UDim2.new(0.75,0,0.010,0)
LBL.Size = UDim2.new(0, 133, 0, 30)
LBL.Font = Enum.Font.GothamSemibold
LBL.Text = "TextLabel"
LBL.TextColor3 = Color3.new(1, 1, 1)
LBL.TextScaled = true
LBL.TextSize = 14
LBL.TextWrapped = true
LBL.Visible = true

local FpsLabel = LBL
local Heartbeat = game:GetService("RunService").Heartbeat
local LastIteration, Start
local FrameUpdateTable = { }

local function HeartbeatUpdate()
	LastIteration = tick()
	for Index = #FrameUpdateTable, 1, -1 do
		FrameUpdateTable[Index + 1] = (FrameUpdateTable[Index] >= LastIteration - 1) and FrameUpdateTable[Index] or nil
	end
	FrameUpdateTable[1] = LastIteration
	local CurrentFPS = (tick() - Start >= 1 and #FrameUpdateTable) or (#FrameUpdateTable / (tick() - Start))
	CurrentFPS = CurrentFPS - CurrentFPS % 1
	FpsLabel.Text = ("北京时间:"..os.date("%H").."时"..os.date("%M").."分"..os.date("%S"))
end
Start = tick()
Heartbeat:Connect(HeartbeatUpdate)
local Window = OrionLib:MakeWindow({Name = "龙脚本", IntroIcon = "rbxassetid://4335482575", HidePremium = false, SaveConfig = true,IntroText = "龙脚本", ConfigFolder = "龙脚本"})

local about = Window:MakeTab({
    Name = "公告",
    Icon = "rbxassetid://4335482575",
    PremiumOnly = false

})
about:AddParagraph("I got nothing to lose","不知不觉夏去秋来")
about:AddParagraph("作者: 猫王")
about:AddParagraph("副作者: 小天")
about:AddParagraph("制作者: 纳西妲")

local Tab = Window:MakeTab({
    Name = "通用功能",
    Icon = "rbxassetid://4335482575",
    PremiumOnly = false

})

Tab:AddButton({
	Name = "甩飞所有人",
	Callback = function()
	loadstring(game:HttpGet("https://pastefy.app/8B4iDhvf/raw"))()
	end
})

Tab:AddButton({
	Name = "后厅竞赛",
	Callback = function()
	local plr = game.Players.LocalPlayer.Character.Head
for i, v in pairs(game:GetService("Workspace"):GetDescendants()) do
        if v.Name == "TouchInterest" and v.Parent then
        firetouchinterest(plr, v.Parent, 0)
    end
end
	end
})

local plrs = game.Players

local playerNames = {}
local players = plrs:GetPlayers()

for _, player in ipairs(players) do
    table.insert(playerNames, player.Name)
end

Tab:AddDropdown({
    Name = "传送玩家",
    Default = playerNames[1] or "No Players",
    Options = playerNames,
    Callback = function(selectedplrName)
        local targetPlayer = plrs:FindFirstChild(selectedplrName)
        
        if targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("HumanoidRootPart") then
            -- Teleporting your character to the selected player's position
            local targetPosition = targetPlayer.Character.HumanoidRootPart.Position
            local localPlayerRoot = plrs.LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
            
            if localPlayerRoot then
                localPlayerRoot.CFrame = CFrame.new(targetPosition)
            end
        end
        print(selectedplrName)
    end    
})

Tab:AddTextbox({
	Name = "范围修改",
	Default = "",
	TextDisappear = true,
	Callback = function(value)
	 
