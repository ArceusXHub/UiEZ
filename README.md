local WarpNero = Instance.new("ScreenGui")
local MODILEGUISOMEXHUB = Instance.new("TextButton")
local MODILEGUISOMEXHUBHUI = Instance.new("UICorner")
local MODILEMAGE = Instance.new("ImageLabel")
MODILEGUISOMEXHUBHUI.Name = "MODILEGUISOMEXHUBHUI"
MODILEGUISOMEXHUBHUI.Parent = MODILEGUISOMEXHUB
MODILEMAGE.Name = "MODILEMAGE"
MODILEMAGE.Parent = MODILEGUISOMEXHUB
MODILEMAGE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
MODILEMAGE.BackgroundTransparency = 1.000
MODILEMAGE.BorderSizePixel = 0
MODILEMAGE.Position = UDim2.new(0.234619886, 0, 0.239034846, 0)
MODILEMAGE.Size = UDim2.new(0, 30, 0, 30)
MODILEMAGE.Image = "rbxassetid://7743870134"
WarpNero.Name = "WarpNero"
WarpNero.Parent = game.CoreGui
WarpNero.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
MODILEGUISOMEXHUB.Name = "MODILEGUISOMEXHUB"
MODILEGUISOMEXHUB.Parent = WarpNero
MODILEGUISOMEXHUB.BackgroundColor3 = Color3.fromRGB(30,20,20)
MODILEGUISOMEXHUB.BackgroundTransparency = 0.1
MODILEGUISOMEXHUB.BorderSizePixel = 0
MODILEGUISOMEXHUB.Position = UDim2.new(0.120833337, 0, 0.0952890813, 0)
MODILEGUISOMEXHUB.Size = UDim2.new(0, 55, 0, 55)
MODILEGUISOMEXHUB.Font = Enum.Font.SourceSans
MODILEGUISOMEXHUB.Text = "MTX"
MODILEGUISOMEXHUB.TextColor3 = Color3.fromRGB(153, 51, 255)
MODILEGUISOMEXHUB.TextSize = 20.000
MODILEGUISOMEXHUB.Draggable = true
MODILEGUISOMEXHUB.MouseButton1Click:Connect(function()
Fluent.Window:Minimize()
setfpscap(500)
end)
local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/SaveManager.lua"))()
local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/InterfaceManager.lua"))()
loadstring(game:HttpGet("https://pastebin.com/raw/Ht5HtN4Z"))()
local notif = loadstring(game:HttpGet("https://raw.githubusercontent.com/C7Metatron/MetatronX-Project/main/NotificationUI"))()
function notify(MetatronX,title,description,icon,color)
  notif:message {
      Title = MetatronX.."<font color='rgb(".. color ..")'>"..title.."</font>",
      Description = description,
      Icon = icon
  }
end
notify("MTX Hub  ","  Initiating","Loading MTX Hub!",7743870134,"99, 0, 255")
local Window = Fluent:CreateWindow({
  Title = "๐ฅ MTX HUB | Blox Fruit V1 ๐‘‘ ",
  SubTitle = "๐‘พ By > Metatron | Mark: MARK ๐ป#8145",
  TabWidth = 160,
  Size = UDim2.fromOffset(500, 320),
  Acrylic = false, -- The blur may be detectable, setting this to false disables blur entirely
  Theme = "Amethyst",
  MinimizeKey = Enum.KeyCode.K -- Used when theres no MinimizeKeybind
})
local Tabs = {
  Farm = Window:AddTab({ Title = "Farm", Icon = "rbxassetid://10734975486" }),
  Items = Window:AddTab({ Title = "Item Quest", Icon = "rbxassetid://10723396107" }),
  SFarm = Window:AddTab({ Title = "Settings Farm", Icon = "rbxassetid://7743870134" }),
  Stats = Window:AddTab({ Title = "Stats", Icon = "rbxassetid://10734951847" }),
  Raid = Window:AddTab({ Title = "Raid", Icon = "rbxassetid://10723345749" }),
  Warp = Window:AddTab({ Title = "Warp", Icon = "rbxassetid://10734886202" }),
  Misc = Window:AddTab({ Title = "Misc", Icon = "rbxassetid://10723376114" }),
  Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
}
--// FINAL
local Options = Fluent.Options

InterfaceManager:SetLibrary(Fluent)

SaveManager:SetIgnoreIndexes({})

InterfaceManager:SetFolder("FluentScriptHub")
SaveManager:SetFolder("MTX Hub")

InterfaceManager:BuildInterfaceSection(Tabs.Settings)

Window:SelectTab(1)
------// BLOX FRUIT
--// Sea world
World1 = false
World2 = false
World3 = false
local placeId = game.PlaceId
if placeId == 2753915549 then
World1 = true
elseif placeId == 4442272183 then
World2 = true
elseif placeId == 7449423635 then
World3 = true
end
--// Select Area
if World1 then
    AreaList = {
    'Jungle', 'Buggy', 'Desert', 'Snow', 'Marine', 'Sky', 'Prison', 'Colosseum', 'Magma', 'Fishman', 'Sky Island', 'Fountain'
    } elseif World2 then
    AreaList = {
    'Area 1', 'Area 2', 'Zombie', 'Marine', 'Snow Mountain', 'Ice fire', 'Ship', 'Frost', 'Forgotten'
    } elseif World3 then
    AreaList = {
    'Pirate Port', 'Amazon', 'Marine Tree', 'Deep Forest', 'Haunted Castle', 'Nut Island', 'Ice Cream Island', 'Cake Island', 'Choco Island', 'Candy Island'
    }
    end

-----//// Script
loadstring(game:HttpGet("https://raw.githubusercontent.com/C7Metatron/MetatronX-Project/main/Quests%20MTXHub"))()

Tabs.Farm:AddParagraph({
    Title = "Farm Options",
    Content = ""
})

local Dropdown = Tabs.Farm:AddDropdown("Select Weapon", {
    Title = "Select Weapon",
    Values = {"Melee", "Sword",},
    Multi = false,
    Default = 1,
})

Dropdown:SetValue("Melee")

Dropdown:OnChanged(function(value)
    _G.SelectWeapon = value
end)
task.spawn(function()
	while wait() do
		pcall(function()
			if _G.SelectWeapon == "Melee" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Melee" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.SelectWeapon = v.Name
						end
					end
				end
			elseif _G.SelectWeapon == "Sword" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Sword" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.SelectWeapon = v.Name
						end
					end
				end
			elseif _G.SelectWeapon == "Gun" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Gun" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.SelectWeapon = v.Name
						end
					end
				end
			elseif _G.SelectWeapon == "Fruit" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Blox Fruit" then
						if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
							_G.SelectWeapon = v.Name
						end
					end
				end
			end
		end)
	end
    end)

local Dropdown = Tabs.Farm:AddDropdown("Farm Mode", {
    Title = "Farm Mode",
    Values = {"Auto Farm Level", "No Quest", "Near Farm", "Fast Farm Lv.1-300"},
    Multi = false,
    Default = 1,
})

Dropdown:SetValue("Normal")

Dropdown:OnChanged(function(value)
    _G.FarmMode = value
    FarmMode = value
end)
spawn(function()
    while wait() do
        if FarmMode == "Auto Farm Level" and _G.AutoFarm then
            pcall(function()
                local QuestTitle = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
                if not string.find(QuestTitle, NameMon) then
                    StartMagnet = false
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                end
                if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                    StartMagnet = false
                    CheckQuest()
                    if BypassTP then
                    if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - CFrameQuest.Position).Magnitude > 1500 then
                    BTP(CFrameQuest)
                    elseif (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - CFrameQuest.Position).Magnitude < 1500 then
                    TP1(CFrameQuest)
                    end
                else
                    TP1(CFrameQuest)
                end
                if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - CFrameQuest.Position).Magnitude <= 5 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQuest,LevelQuest)
                    end
                elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                    CheckQuest()
                    if game:GetService("Workspace").Enemies:FindFirstChild(Mon) then
                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                                if v.Name == Mon then
                                    if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
                                        repeat task.wait()
                                            EquipWeapon(_G.SelectWeapon)
                                            AutoHaki()                                            
                                            PosMon = v.HumanoidRootPart.CFrame
                                            TP1(v.HumanoidRootPart.CFrame * Pos)
                                            v.HumanoidRootPart.CanCollide = false
                                            v.Humanoid.WalkSpeed = 0
                                            v.Head.CanCollide = false
                                            v.HumanoidRootPart.Size = Vector3.new(70,70,70)
                                            StartMagnet = true
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                        until not _G.AutoFarm or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                    else
                                        StartMagnet = false
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                                    end
                                end
                            end
                        end
                    else
                        TP1(CFrameMon)
                        UnEquipWeapon(_G.SelectWeapon)
                        StartMagnet = false
                        if game:GetService("ReplicatedStorage"):FindFirstChild(Mon) then
                         TP1(game:GetService("ReplicatedStorage"):FindFirstChild(Mon).HumanoidRootPart.CFrame * CFrame.new(15,10,2))
                        end
                    end
                end
            end)
        end
    end
end)

spawn(function()
    while wait() do
        if FarmMode == "No Quest" and _G.AutoFarm then
            pcall(function()
                local QuestTitle = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
                if not string.find(QuestTitle, NameMon) then
                    StartMagnet = false
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                end
                if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                    StartMagnet = false
                    CheckQuest()
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQuest,LevelQuest)
                    if BypassTP then
                    if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - CFrameMon.Position).Magnitude > 1500 then
                    BTP(CFrameMon)
                    elseif (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - CFrameMon.Position).Magnitude < 1500 then
                    TP1(CFrameMon)
                    end
                else
                    TP1(CFrameMon)
                end
                elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                    CheckQuest()
                    if game:GetService("Workspace").Enemies:FindFirstChild(Mon) then
                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                                if v.Name == Mon then
                                    if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
                                        repeat task.wait()
                                            EquipWeapon(_G.SelectWeapon)
                                            AutoHaki()                                            
                                            PosMon = v.HumanoidRootPart.CFrame
                                            TP1(v.HumanoidRootPart.CFrame * Pos)
                                            v.HumanoidRootPart.CanCollide = false
                                            v.Humanoid.WalkSpeed = 0
                                            v.Head.CanCollide = false
                                            v.HumanoidRootPart.Size = Vector3.new(70,70,70)
                                            StartMagnet = true
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                        until not _G.AutoFarm or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                    else
                                        StartMagnet = false
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                                    end
                                end
                            end
                        end
                    else
                        TP1(CFrameMon)
                        UnEquipWeapon(_G.SelectWeapon)
                        StartMagnet = false
                        if game:GetService("ReplicatedStorage"):FindFirstChild(Mon) then
                         TP1(game:GetService("ReplicatedStorage"):FindFirstChild(Mon).HumanoidRootPart.CFrame * CFrame.new(15,10,2))
                        end
                    end
                end
            end)
        end
    end
end)

spawn(function()
	while wait() do
		if FarmMode == "Near Farm" and _G.AutoFarm then
			for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                if v.Name and v:FindFirstChild("Humanoid") then
			        if v.Humanoid.Health > 0 then
			            repeat wait()
			              EquipWeapon(_G.SelectWeapon)
			                if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
			                	local args = {
				                	[1] = "Buso"
			                	}
			                	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			               	end
			                topos(v.HumanoidRootPart.CFrame * Pos)
			                v.HumanoidRootPart.CanCollide = false
			                Fastattack = true
			                v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
						    game:GetService("VirtualUser"):CaptureController()
				       	    game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 672), game.Workspace.CurrentCamera.CFrame)
				       	    AutoFarmNearestMagnet = true
				       	    PosMon = v.HumanoidRootPart.CFrame
			            until not _G.AutoFarmNearest or not v.Parent or v.Humanoid.Health <= 0 
			            AutoFarmNearestMagnet = false
			            Fastattack = false
			        end
			    end
			end
		end
	end
    end)
    spawn(function()
        while wait() do
            if FarmMode == "Fast Farm Lv.1-300" and _G.AutoFarm then
                pcall(function()
                if game.Players.LocalPlayer.Data.Level.Value >= 10 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if v.Name == "Shanda" then
                                if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                                    repeat task.wait()
                                        AutoHaki()
                                        EquipWeapon(_G.SelectWeapon)
                                        v.HumanoidRootPart.CanCollide = false
                                        v.Humanoid.WalkSpeed = 0
                                        StardMag = true
                                        FastMon = v.HumanoidRootPart.CFrame
                                        v.HumanoidRootPart.Size = Vector3.new(80,80,80)                             
                                        TP1(v.HumanoidRootPart.CFrame * Pos)
                                        game:GetService("VirtualUser"):CaptureController()
                                        game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
                                    until not _G.Farmfast or not v.Parent or v.Humanoid.Health <= 0
                                    StardMag = false
                                    TP1(CFrame.new(-7678.48974609375, 5566.40380859375, -497.2156066894531))
                                    UnEquipWeapon(_G.SelectWeapon)
                                end
                            end
                        end
                    else
                        if game:GetService("ReplicatedStorage"):FindFirstChild("Shanda") then
                            TP1(game:GetService("ReplicatedStorage"):FindFirstChild("Shanda").HumanoidRootPart.CFrame * CFrame.new(5,10,2))
                        end
                    end
                end)
            end
        end
    end)
local Toggle = Tabs.Farm:AddToggle("Auto Farm Level", {Title = "Auto Farm Level", Default = false })

Toggle:OnChanged(function(value)
    _G.AutoFarm = value
    _G.RemoveHit = value
    StopTween(_G.AutoFarm)
end)
spawn(function()
    game:GetService("RunService").RenderStepped:Connect(function()
        if _G.RemoveHit == true then
            game:GetService("ReplicatedStorage").Effect.Container.LevelUp:Destroy()
            game:GetService("ReplicatedStorage").Util.Sound:Destroy()
            game:GetService("ReplicatedStorage").Util.Sound.Storage.Other:FindFirstChild("LevelUp_Proxy"):Destroy()
            game:GetService("ReplicatedStorage").Util.Sound.Storage.Other:FindFirstChild("LevelUp"):Destroy()
            game:GetService("ReplicatedStorage").Effect.Container.Respawn:Destroy()        
        end
    end)
end)

Tabs.SFarm:AddParagraph({
    Title = "Farm Setings",
    Content = ""
})

local Slider = Tabs.SFarm:AddSlider("Distance Farm", {
    Title = "Y Distance Farm ",
    Description = "Distance Farm",
    Default = 35,
    Min = 10,
    Max = 100,
    Rounding = 1,
    Callback = function(value)
        PosY = value
    end
})

Slider:OnChanged(function(Value)
    PosY = value
end)

Slider:SetValue(25)

local Toggle = Tabs.SFarm:AddToggle("Auto Haki", {Title = "Auto Haki", Default = true })

Toggle:OnChanged(function(value)
    _G.AUTOHAKI = value
end)
spawn(function()
    while wait(.1) do
        if _G.AUTOHAKI then 
            if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                local args = {
                    [1] = "Buso"
                }
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end
        end
    end
end)

local Toggle = Tabs.SFarm:AddToggle("Bring Mob", {Title = "Bring Mob", Default = true })

Toggle:OnChanged(function(Mag)
    _G.BringMonster = Mag
end)
spawn(function()
    while task.wait() do
        pcall(function()
            if _G.BringMonster then
                CheckQuest()
                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                    if _G.AutoFarm and StartMagnet and v.Name == Mon and (Mon == "Factory Staff [Lv. 800]" or Mon == "Monkey [Lv. 14]" or Mon == "Dragon Crew Warrior [Lv. 1575]" or Mon == "Dragon Crew Archer [Lv. 1600]") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 220 then
                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                        v.HumanoidRootPart.CFrame = PosMon
                        v.Humanoid:ChangeState(14)
                        v.HumanoidRootPart.CanCollide = false
                        v.Head.CanCollide = false
                        if v.Humanoid:FindFirstChild("Animator") then
                            v.Humanoid.Animator:Destroy()
                        end
                        sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                    elseif _G.AutoFarm and StartMagnet and v.Name == Mon and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= _G.BringMode then
                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                        v.HumanoidRootPart.CFrame = PosMon
                        v.Humanoid:ChangeState(14)
                        v.HumanoidRootPart.CanCollide = false
                        v.Head.CanCollide = false
                        if v.Humanoid:FindFirstChild("Animator") then
                            v.Humanoid.Animator:Destroy()
                        end
                        sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                    end
                end
            end
        end)
    end
end)
local Dropdown = Tabs.SFarm:AddDropdown("Bring Mob Mode", {
    Title = "Bring Mob Mode",
    Values = {"Low", "Normal", "Super Bring"},
    Multi = false,
    Default = 1,
})

Dropdown:SetValue("Low")

Dropdown:OnChanged(function(value)
    _G.BringMode = value
end)
spawn(function()
    while wait(.1) do
        if _G.BringMode then
            pcall(function()
                if _G.BringMode == "Low" then
                    _G.BringMode = 250
                elseif _G.BringMode == "Normal" then
                    _G.BringMode = 300
                elseif _G.BringMode == "Super Bring" then
                    _G.BringMode = 350
                end
            end)
        end
    end
end)

local Toggle = Tabs.SFarm:AddToggle("Fast Attack", {Title = "Fast Attack", Default = true })

Toggle:OnChanged(function(value)
    _G.FastAttack = value
end)
local CameraShaker = require(game.ReplicatedStorage.Util.CameraShaker)
CombatFrameworkR = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
y = debug.getupvalues(CombatFrameworkR)[2]
spawn(function()
    game:GetService("RunService").RenderStepped:Connect(function()
        if _G.FastAttack then
            if typeof(y) == "table" then
                pcall(function()
                    CameraShaker:Stop()
                    y.activeController.timeToNextAttack = (math.huge^math.huge^math.huge)
                    y.activeController.timeToNextAttack = 0
                    y.activeController.hitboxMagnitude = 60
                    y.activeController.active = false
                    y.activeController.timeToNextBlock = 0
                    y.activeController.focusStart = 1655503339.0980349
                    y.activeController.increment = 1
                    y.activeController.blocking = false
                    y.activeController.attacking = false
                    y.activeController.humanoid.AutoRotate = true
                end)
            end
        end
    end)
end)
spawn(function()
    game:GetService("RunService").RenderStepped:Connect(function()
        if _G.FastAttack or _G.FastAttackCambodiakak == true then
            game.Players.LocalPlayer.Character.Stun.Value = 0
            game.Players.LocalPlayer.Character.Busy.Value = false        
        end
    end)
end)
    local CamShake = require(game.ReplicatedStorage.Util.CameraShaker)
    CamShake:Stop()
    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
    spawn(function()
        while task.wait() do
            pcall(function()
                if not shared.orl then shared.orl = STOPRL.wrapAttackAnimationAsync end
                if not shared.cpc then shared.cpc = STOP.play end
                    STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                    local Hits = STOPRL.getBladeHits(b,c,d)
                    if Hits then
                        if _G.FastAttack then
                            STOP.play = function() end
                            a:Play(0.01,0.01,0.01)
                            func(Hits)
                            STOP.play = shared.cpc
                            wait(a.length * 0.5)
                            a:Stop()
                        else
                            a:Play()
                        end
                    end
                end
            end)
        end
    end)

    local Dropdown = Tabs.SFarm:AddDropdown("Fast Attack Delay", {
        Title = "Fast Attack Delay",
        Values = {"Super Fast (0)", "Fast (0.1)", "Recomended (0.15)"},
        Multi = false,
        Default = 1,
    })

    Dropdown:SetValue("Fast (0.1)")

    Dropdown:OnChanged(function(MakoGay)
        _G.FastAttackDelay = MakoGay
    end)
    spawn(function()
        while wait(.1) do
            if _G.FastAttackDelay then
                pcall(function()
                    if _G.FastAttackDelay == "Super Fast (0)" then
                        _G.FastAttackDelay = 0
                    elseif _G.FastAttackDelay == "Fast (0.1)" then
                        _G.FastAttackDelay = 0.1
                    elseif _G.FastAttackDelay == "Recomended (0.15)" then
                        _G.FastAttackDelay = 0.15
                    elseif _G.FastAttackDelay == "0.155" then
                        _G.FastAttackDelay = 0.155
                    elseif _G.FastAttackDelay == "0.16" then
                        _G.FastAttackDelay = 0.16
                    elseif _G.FastAttackDelay == "0.165" then
                        _G.FastAttackDelay = 0.165
                    elseif _G.FastAttackDelay == "0.17" then
                        _G.FastAttackDelay = 0.17
                    elseif _G.FastAttackDelay == "Normal (0.175)" then
                        _G.FastAttackDelay = 0.175
                    elseif _G.FastAttackDelay == "0.18" then
                        _G.FastAttackDelay = 0.18
                    elseif _G.FastAttackDelay == "0.185" then
                        _G.FastAttackDelay = 0.185
                    end
                end)
            end
        end
    end)
    
    function GetBladeHit()
        local CombatFrameworkLib = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework))
        local CmrFwLib = CombatFrameworkLib[2]
        local p13 = CmrFwLib.activeController
        local weapon = p13.blades[1]
        if not weapon then 
            return weapon
        end
        while weapon.Parent ~= game.Players.LocalPlayer.Character do
            weapon = weapon.Parent 
        end
        return weapon
    end
    function AttackHit()
        local CombatFrameworkLib = debug.getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework))
        local CmrFwLib = CombatFrameworkLib[2]
        local plr = game.Players.LocalPlayer
        for i = 1, 1 do
            local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(plr.Character,{plr.Character.HumanoidRootPart},60)
            local cac = {}
            local hash = {}
            for k, v in pairs(bladehit) do
                if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                    table.insert(cac, v.Parent.HumanoidRootPart)
                    hash[v.Parent] = true
                end
            end
            bladehit = cac
            if #bladehit > 0 then
                pcall(function()
                    CmrFwLib.activeController.timeToNextAttack = 1
                    CmrFwLib.activeController.attacking = false
                    CmrFwLib.activeController.blocking = false
                    CmrFwLib.activeController.timeToNextBlock = 0
                    CmrFwLib.activeController.increment = 3
                    CmrFwLib.activeController.hitboxMagnitude = 60
                    CmrFwLib.activeController.focusStart = 0
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetBladeHit()))
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "")
                end)
            end
        end
    end
    spawn(function()
        while wait(.1) do
            if _G.FastAttack then
                pcall(function()
                    repeat task.wait(_G.FastAttackDelay)
                        AttackHit()
                    until not _G.FastAttack
                end)
            end
        end
    end)

    Tabs.Stats:AddParagraph({
        Title = "Stats Points",
        Content = ""
    })
    
    local Toggle = Tabs.Stats:AddToggle("Melee", {Title = "Melee", Default = false })

    Toggle:OnChanged(function(value)
        _G.Auto_Stats_Melee = value 
    end)
    spawn(function()
        while wait() do
            if _G.Auto_Stats_Melee then
                local args = {
                    [1] = "AddPoint",
                    [2] = "Melee",
                    [3] = _G.Point
                }
                            
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end
        end
       end)
    local Toggle = Tabs.Stats:AddToggle("Defense", {Title = "Defense", Default = false })

    Toggle:OnChanged(function(value)
        _G.Auto_Stats_Defense = value
    end)
    
spawn(function()
    while wait() do
        if _G.Auto_Stats_Defense then
            local args = {
                [1] = "AddPoint",
                [2] = "Defense",
                [3] = _G.Point
            }
                        
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end
    end
   end)
    local Toggle = Tabs.Stats:AddToggle("Sword", {Title = "Sword", Default = false })

    Toggle:OnChanged(function(value)
        _G.Auto_Stats_Sword = value
    end)
    spawn(function()
        while wait() do
            if _G.Auto_Stats_Sword then
                local args = {
                    [1] = "AddPoint",
                    [2] = "Sword",
                    [3] = _G.Point
                }
                            
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end
        end
       end)
    local Toggle = Tabs.Stats:AddToggle("Gun", {Title = "Gun", Default = false })

    Toggle:OnChanged(function(value)
        _G.Auto_Stats_Gun = value
    end)
    spawn(function()
        while wait() do
            if _G.Auto_Stats_Gun then
                local args = {
                    [1] = "AddPoint",
                    [2] = "Gun",
                    [3] = _G.Point
                }
                            
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end
        end
       end)
       
    local Toggle = Tabs.Stats:AddToggle("Devil Fruit", {Title = "Devil Fruit", Default = false })

    Toggle:OnChanged(function(value)
        _G.Auto_Stats_Devil_Fruit = value
    end)
    

spawn(function()
    while wait() do
        if _G.Auto_Stats_Devil_Fruit then
            local args = {
                [1] = "AddPoint",
                [2] = "Demon Fruit",
                [3] = _G.Point
            }
                        
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end
    end
   end)

    local Slider = Tabs.Stats:AddSlider("Slider", {
        Title = "Point",
        Description = "",
        Default = 3,
        Min = 3,
        Max = 100,
        Rounding = 1,
        Callback = function(value)
            _G.Point = value
        end
    })

    Tabs.Raid:AddParagraph({
        Title = "Raid Options",
        Content = ""
    })
    local Toggle = Tabs.Raid:AddToggle("Auto Farm Dungeon", {Title = "Auto Farm Dungeon", Default = false })

    Toggle:OnChanged(function(value)
        _G.Auto_Dungeon = value
        StopTween(_G.Auto_Dungeon)
    end)
    
    spawn(function()
		while wait() do
			if _G.Auto_Dungeon then
				if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true and game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
					if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
						topos(game:GetService("Workspace")["_WorldOrigin"].Locations["Island 5"].CFrame * CFrame.new(4, 65, 10))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
						topos(game:GetService("Workspace")["_WorldOrigin"].Locations["Island 4"].CFrame *  CFrame.new(4, 65, 10))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
						topos(game:GetService("Workspace")["_WorldOrigin"].Locations["Island 3"].CFrame * CFrame.new(4, 65, 10))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
						topos(game:GetService("Workspace")["_WorldOrigin"].Locations["Island 2"].CFrame * CFrame.new(4, 65, 10))
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						topos(game:GetService("Workspace")["_WorldOrigin"].Locations["Island 1"].CFrame * CFrame.new(4, 65, 10))
					end
				end
			end
		end
	end)

spawn(function()
    pcall(function()
        while wait() do
            if _G.Auto_Dungeon and game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
                local attackRadius = 250  -- เธเธฃเธฑเธเธฃเธฐเธขเธฐเธเธฒเธฃเธ—เธณเธฅเธฒเธขเธ•เธฒเธกเธ•เนเธญเธเธเธฒเธฃ
                sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
                for _, v in pairs(game:GetService("Workspace").Enemies:GetDescendants()) do
                    if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                        pcall(function()
                            if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= attackRadius then
                                v.Humanoid.Health = 0
                                v.HumanoidRootPart.CanCollide = false
                            end
                        end)
                    end
                end
            end
        end
    end)
end)
	game:GetService("RunService").RenderStepped:Connect(function()
		if _G.autoraid then
			game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
		end
	end)
    local Dropdown = Tabs.Raid:AddDropdown("Chip Select", {
        Title = "Chip Select",
        Values = {"Flame", "Ice", "Quake", "Light", "Dark", "String", "Rumble", "Magma", "Human: Buddha", "Sand", "Bird: Phoenix", "Dough"},
        Multi = false,
        Default = 1,
    })

    Dropdown:SetValue("Flame")

    Dropdown:OnChanged(function(value)
        _G.SelectChip = value
    end)
    
    local Toggle = Tabs.Raid:AddToggle("Buy Chip Select", {Title = "Buy Chip Select", Default = false })

    Toggle:OnChanged(function()
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc","Select",_G.SelectChip)
    end)
    spawn(function()
        while wait() do
            if _G.AutoSelectDungeon then
                pcall(function()
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flame-Flame") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flame-Flame") then
                        _G.SelectChip = "Flame"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Ice-Ice") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Ice-Ice") then
                        _G.SelectChip = "Ice"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Quake-Quake") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Quake-Quake") then
                        _G.SelectChip = "Quake"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Light-Light") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Light-Light") then
                        _G.SelectChip = "Light"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dark-Dark") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dark-Dark") then
                        _G.SelectChip = "Dark"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("String-String") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("String-String") then
                        _G.SelectChip = "String"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rumble-Rumble") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rumble-Rumble") then
                        _G.SelectChip = "Rumble"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Magma-Magma") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Magma-Magma") then
                        _G.SelectChip = "Magma"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Human-Human: Buddha Fruit") then
                        _G.SelectChip = "Human: Buddha"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sand-Sand") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sand-Sand") then
                        _G.SelectChip = "Sand"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird-Bird: Phoenix") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird-Bird: Phoenix") then
                        _G.SelectChip = "Bird: Phoenix"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dough") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dough") then
                        _G.SelectChip = "Dough"
                    else
                        _G.SelectChip = "Flame"
                    end
                end)
            end
        end
    end)
    
    local Toggle = Tabs.Raid:AddToggle("Auto Start Go To Dungeon", {Title = "Auto Start Go To Dungeon", Default = false })

    Toggle:OnChanged(function(value)
        _G.Auto_StartRaid = value
    end)

    spawn(function()
        while wait(.1) do
            pcall(function()
                if _G.Auto_StartRaid then
                    if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
                        if not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") then
                            if World2 then
                                fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
                            elseif World3 then
                                fireclickdetector(game:GetService("Workspace").Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
                            end
                        end
                    end
                end
            end)
        end
    end)
    
    local Toggle = Tabs.Raid:AddToggle("Kill Aura", {Title = "Kill Aura", Default = false })

    Toggle:OnChanged(function(vu)
        _G.KillAura = vu
    end)
    spawn(function()
        pcall(function() 
        while wait() do
            if _G.KillAura then
                for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
                    if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                        pcall(function()
                            repeat wait()
                                sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                                v.Humanoid.Health = 0
                                v.HumanoidRootPart.CanCollide = false
                                v.HumanoidRootPart.Size = Vector3.new(80,80,80)
                                v.HumanoidRootPart.Transparency = 1
                            until not _G.KillAura or not v.Parent or v.Humanoid.Health <= 0
                        end)
                    end
                end
            end
        end
        end)
        end)

        Tabs.Warp:AddParagraph({
            Title = "Island Warp",
            Content = ""
        })


        Tabs.Warp:AddButton({
            Title = "Stop All Tween",
            Description = "Stop Tween",
            Callback = function()
                topos(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
                _G.Clip = false
                StopTween(_G.AutoFarm)
            end
        })
        if World1 then
        local Dropdown = Tabs.Warp:AddDropdown("Select Island", {
            Title = "Select Island",
            Values = {"WindMill", "Marine", "Middle Town", "Jungle", "Pirate Village", "Desert", "Snow Island", "MarineFord", "Colosseum", "Sky Island 1", "Prison", "Magma Village", "thirteen", "Under Water Island", "Fountain City"},
            Multi = false,
            Default = 1,
        })
        
    Dropdown:SetValue("Jungle")

    Dropdown:OnChanged(function(value)
        _G.SelectIsland = value
    end)
end

    if World2 then
    local Dropdown = Tabs.Warp:AddDropdown("Select Island", {
        Title = "Select Island",
        Values = {"The Cafe", "Frist Spot", "Dark Area", "Flamingo Mansion", "Flamingo Room", "Green Zone", "Factory", "Colossuim", "Zombie Island", "Two Snow Mountain", "Punk Hazard", "Cursed Ship", "Ice Castle", "Forgotten Island", "Ussop Island", "Mini Sky Island"},
        Multi = false,
        Default = 1,
    })

    
Dropdown:SetValue("The Cafe")

Dropdown:OnChanged(function(value)
    _G.SelectIsland = value
end)
end

if World3 then
local Dropdown = Tabs.Warp:AddDropdown("Select Island", {
    Title = "Select Island",
    Values = {"Mansion", "Port Town", "Great Tree", "Castle On The Sea", "MiniSky", "Hydra Island", "Floating Turtle", "Haunted Castle", "Ice Cream Island", "Peanut Island", "Cake Island",  "Cocoa Island", "Candy Island Newโ"},
    Multi = false,
    Default = 1,
})

Dropdown:SetValue("Mansion")

Dropdown:OnChanged(function(Value)
    _G.SelectIsland = value
end)
end

local Toggle = Tabs.Warp:AddToggle("Teleport", {Title = "Teleport", Default = false })

Toggle:OnChanged(function(value)
    _G.TeleportIsland = value
    if _G.TeleportIsland == true then
        repeat wait()
            if _G.SelectIsland == "WindMill" then
                topos(CFrame.new(979.79895019531, 16.516613006592, 1429.0466308594))
            elseif _G.SelectIsland == "Marine" then
                topos(CFrame.new(-2566.4296875, 6.8556680679321, 2045.2561035156))
            elseif _G.SelectIsland == "Middle Town" then
                topos(CFrame.new(-690.33081054688, 15.09425163269, 1582.2380371094))
            elseif _G.SelectIsland == "Jungle" then
                topos(CFrame.new(-1612.7957763672, 36.852081298828, 149.12843322754))
            elseif _G.SelectIsland == "Pirate Village" then
                topos(CFrame.new(-1181.3093261719, 4.7514905929565, 3803.5456542969))
            elseif _G.SelectIsland == "Desert" then
                topos(CFrame.new(944.15789794922, 20.919729232788, 4373.3002929688))
            elseif _G.SelectIsland == "Snow Island" then
                topos(CFrame.new(1347.8067626953, 104.66806030273, -1319.7370605469))
            elseif _G.SelectIsland == "MarineFord" then
                topos(CFrame.new(-4914.8212890625, 50.963626861572, 4281.0278320313))
            elseif _G.SelectIsland == "Colosseum" then
                topos( CFrame.new(-1427.6203613281, 7.2881078720093, -2792.7722167969))
            elseif _G.SelectIsland == "Sky Island 1" then
                topos(CFrame.new(-4869.1025390625, 733.46051025391, -2667.0180664063))
            elseif _G.SelectIsland == "Sky Island 2" then  
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
            elseif _G.SelectIsland == "Sky Island 3" then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
            elseif _G.SelectIsland == "Prison" then
                topos( CFrame.new(4875.330078125, 5.6519818305969, 734.85021972656))
            elseif _G.SelectIsland == "Magma Village" then
                topos(CFrame.new(-5247.7163085938, 12.883934020996, 8504.96875))
            elseif _G.SelectIsland == "Under Water Island" then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
            elseif _G.SelectIsland == "Fountain City" then
                topos(CFrame.new(5127.1284179688, 59.501365661621, 4105.4458007813))
            elseif _G.SelectIsland == "Shank Room" then
                topos(CFrame.new(-1442.16553, 29.8788261, -28.3547478))
            elseif _G.SelectIsland == "Mob Island" then
                topos(CFrame.new(-2850.20068, 7.39224768, 5354.99268))
            elseif _G.SelectIsland == "The Cafe" then
                topos(CFrame.new(-380.47927856445, 77.220390319824, 255.82550048828))
            elseif _G.SelectIsland == "Frist Spot" then
                topos(CFrame.new(-11.311455726624, 29.276733398438, 2771.5224609375))
            elseif _G.SelectIsland == "Dark Area" then
                topos(CFrame.new(3780.0302734375, 22.652164459229, -3498.5859375))
            elseif _G.SelectIsland == "Flamingo Mansion" then
                topos(CFrame.new(-483.73370361328, 332.0383605957, 595.32708740234))
            elseif _G.SelectIsland == "Flamingo Room" then
                topos(CFrame.new(2284.4140625, 15.152037620544, 875.72534179688))
            elseif _G.SelectIsland == "Green Zone" then
                topos( CFrame.new(-2448.5300292969, 73.016105651855, -3210.6306152344))
            elseif _G.SelectIsland == "Factory" then
                topos(CFrame.new(424.12698364258, 211.16171264648, -427.54049682617))
            elseif _G.SelectIsland == "Colossuim" then
                topos( CFrame.new(-1503.6224365234, 219.7956237793, 1369.3101806641))
            elseif _G.SelectIsland == "Zombie Island" then
                topos(CFrame.new(-5622.033203125, 492.19604492188, -781.78552246094))
            elseif _G.SelectIsland == "Two Snow Mountain" then
                topos(CFrame.new(753.14288330078, 408.23559570313, -5274.6147460938))
            elseif _G.SelectIsland == "Punk Hazard" then
                topos(CFrame.new(-6127.654296875, 15.951762199402, -5040.2861328125))
            elseif _G.SelectIsland == "Cursed Ship" then
                topos(CFrame.new(923.40197753906, 125.05712890625, 32885.875))
            elseif _G.SelectIsland == "Ice Castle" then
                topos(CFrame.new(6148.4116210938, 294.38687133789, -6741.1166992188))
            elseif _G.SelectIsland == "Forgotten Island" then
                topos(CFrame.new(-3032.7641601563, 317.89672851563, -10075.373046875))
            elseif _G.SelectIsland == "Ussop Island" then
                topos(CFrame.new(4816.8618164063, 8.4599885940552, 2863.8195800781))
            elseif _G.SelectIsland == "Mini Sky Island" then
                topos(CFrame.new(-288.74060058594, 49326.31640625, -35248.59375))
            elseif _G.SelectIsland == "Great Tree" then
                topos(CFrame.new(2681.2736816406, 1682.8092041016, -7190.9853515625))
            elseif _G.SelectIsland == "Castle On The Sea" then
                topos(CFrame.new(-5074.45556640625, 314.5155334472656, -2991.054443359375))
            elseif _G.SelectIsland == "MiniSky" then
                topos(CFrame.new(-260.65557861328, 49325.8046875, -35253.5703125))
            elseif _G.SelectIsland == "Port Town" then
                topos(CFrame.new(-290.7376708984375, 6.729952812194824, 5343.5537109375))
            elseif _G.SelectIsland == "Hydra Island" then
                topos(CFrame.new(5228.8842773438, 604.23400878906, 345.0400390625))
            elseif _G.SelectIsland == "Floating Turtle" then
                topos(CFrame.new(-13274.528320313, 531.82073974609, -7579.22265625))
            elseif _G.SelectIsland == "Mansion" then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-12471.169921875, 374.94024658203, -7551.677734375))
            elseif _G.SelectIsland == "Haunted Castle" then
                topos(CFrame.new(-9515.3720703125, 164.00624084473, 5786.0610351562))
            elseif _G.SelectIsland == "Ice Cream Island" then
                topos(CFrame.new(-902.56817626953, 79.93204498291, -10988.84765625))
            elseif _G.SelectIsland == "Peanut Island" then
                topos(CFrame.new(-2062.7475585938, 50.473892211914, -10232.568359375))
            elseif _G.SelectIsland == "Cake Island" then
                topos(CFrame.new(-1884.7747802734375, 19.327526092529297, -11666.8974609375))
            elseif _G.SelectIsland == "Cocoa Island" then
                topos(CFrame.new(87.94276428222656, 73.55451202392578, -12319.46484375))
            elseif _G.SelectIsland == "Candy Island Newโ" then
                topos(CFrame.new(-1014.4241943359375, 149.11068725585938, -14555.962890625))
            end
        until not _G.TeleportIsland
    end
    StopTween(_G.TeleportIsland)
end)

Tabs.Misc:AddParagraph({
    Title = "Misc Options",
    Content = ""
})

   Tabs.Misc:AddButton({
        Title = "Stop All Tween",
        Description = "Stop Tween",
        Callback = function()
            topos(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
            _G.Clip = false
            StopTween(_G.AutoFarm)
        end
    })

    local Toggle = Tabs.Misc:AddToggle("Auto SetSpawn Point", {Title = "Auto SetSpawn Point", Default = false })

    Toggle:OnChanged(function(value)
        _G.Set = value
    end)
    spawn(function()
        while wait() do
           if _G.Set then
              pcall(function()
              local args = {
              [1] = "SetSpawnPoint"
              }
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
           end)
         end
       end
     end)

    local Toggle = Tabs.Misc:AddToggle("Auto Rejoin", {Title = "Auto Rejoin", Default = true })

    Toggle:OnChanged(function(value)
        _G.AutoRejoin = value
    end)
    spawn(function()
        while wait() do
            if _G.AutoRejoin then
                    getgenv().rejoin = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(child)
                        if child.Name == 'ErrorPrompt' and child:FindFirstChild('MessageArea') and child.MessageArea:FindFirstChild("ErrorFrame") then
                            game:GetService("TeleportService"):Teleport(game.PlaceId)
                        end
                     end)
                end
            end
        end)

    local Toggle = Tabs.Misc:AddToggle("Anti AFK", {Title = "Anti AFK", Default = true })

    Toggle:OnChanged(function()
        local vu = game:GetService("VirtualUser")
        repeat wait() until game:IsLoaded() 
        game:GetService("Players").LocalPlayer.Idled:connect(function()
        game:GetService("VirtualUser"):ClickButton2(Vector2.new())
            vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
            wait(1)
            vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
        end)
    end)

    local Toggle = Tabs.SFarm:AddToggle("Anti Cheat Bypass", {Title = "Anti Cheat Bypass Activated โ…", Default = true })

    Toggle:OnChanged(function(value)
        CheckAntiCheatBypass() 
        _G.SafeFarm = value
        CheckAntiCheatBypass() 
    end)
    function CheckAntiCheatBypass()
        for i,v in pairs(game:GetService("Players").LocalPlayer.Character:GetDescendants()) do
            if v:IsA("LocalScript") then
                if v.Name == "General" or v.Name == "Shiftlock"  or v.Name == "FallDamage" or v.Name == "4444" or v.Name == "CamBob" or v.Name == "JumpCD" or v.Name == "Looking" or v.Name == "Run" then
                    v:Destroy()
                end
            end
         end
         for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerScripts:GetDescendants()) do
            if v:IsA("LocalScript") then
                if v.Name == "RobloxMotor6DBugFix" or v.Name == "Clans"  or v.Name == "Codes" or v.Name == "CustomForceField" or v.Name == "MenuBloodSp"  or v.Name == "PlayerList" then
                    v:Destroy()
                end
            end
         end
        end
       CheckAntiCheatBypass()
