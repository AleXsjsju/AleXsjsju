repeat wait() until game:IsLoaded()
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/DevSoGod/MyScript/main/library"))()
local Window = library:CreateWindow("War Tycoon || We Love War")
local Tab = Window:CreateTab("Main")
local Sector = Tab:CreateSector("Section1", "left")
Sector:AddToggle("Full AutoRebirth", false, function(v)
    _G.AutoRebirth = v
end)
local dd1 = Sector:AddDropdown("Whitelist",{}, false ,true , function(v)
    _G.WL = v
end)
Sector:AddButton("Refresh Players", function()
    for i, v in pairs(dd1:getList()) do
        dd1:Remove(tostring(v))
    end
    for i, v in pairs(game.Players:GetChildren()) do
        if not table.find(dd1:getList(), v.Name) then
            dd1:Add(v.Name)
        end
    end
end)
Sector:AddDropdown("Select Traget",{"Players","Base Shield","AC-130 Gunship"}, false ,true , function(v)
    _G.SelectTraget = v
end)
Sector:AddToggle("Spam RPG (Very Risk)", false, function(v)
    _G.SpamRPG = v
end)




local Sector = Tab:CreateSector("Section2", "Right")

Sector:AddToggle("FarmOil (Bad and Risk)", false, function(v)
    _G.FarmOil = v
end)

Sector:AddToggle("FarmVehiclePart (Risk)", false, function(v)
    _G.FarmVehiclePart = v
end)
Sector:AddTextbox("Enter Point" , "100" , function(w)
    _G.Point = w
end)
Sector:AddButton("Get Point" , function()
    for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
        if a.Owner.Value == game.Players.LocalPlayer then
            for i = 1,tonumber(_G.Point) do
                a:WaitForChild("PurchasedObjects"):WaitForChild("MovingTarget"):WaitForChild("AddPoints"):FireServer(a:WaitForChild("PurchasedObjects"):WaitForChild("MovingTarget"):WaitForChild("Target3"))
            end
        end
    end
end)
Sector:AddToggle("Esp VehiclePart(Quest)", false, function(v)
    _G.ESPOperations = v
end)
local function Oil()
    local dist, thing = math.huge
    for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
        if a.Owner.Value == game.Players.LocalPlayer then
            for _,b in pairs(a.UnpurchasedButtons:GetChildren()) do
                if table.find({"Large Oil 1","Large Oil 2","Large Oil 3","Large Oil 4","Large Oil 5","Large Oil 6","Oil 1","Oil 2","Oil 3","Oil 4","Oil 5","Oil 6"},b.Name) then
                    local mag = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - b.Gradient.Position).magnitude
                    if mag < dist then
                        dist = mag 
                        thing = b
                    end
                end
            end
        end
    end
    return thing
end
local function Misc()
    local dist, thing = math.huge
    for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
        if a.Owner.Value == game.Players.LocalPlayer then
            for _,b in pairs(a.UnpurchasedButtons:GetChildren()) do
                if not table.find({"Large Oil 1","Large Oil 2","Large Oil 3","Large Oil 4","Large Oil 5","Large Oil 6","Oil 1","Oil 2","Oil 3","Oil 4","Oil 5","Oil 6"},b.Name) then
                    if tostring(b.Neon.Color) == "0, 1, 0" or tostring(b.Neon.Color) == "1, 0, 0" or tostring(b.Neon.Color) == "0.0156863, 0.686275, 0.921569" then
                        local mag = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - b.Gradient.Position).magnitude
                        if mag < dist then
                            dist = mag 
                            thing = b
                        end
                    end
                end
            end
        end
    end
    return thing
end
local function Rebirth()
    local dist, thing = math.huge
    for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
        if a.Owner.Value == game.Players.LocalPlayer then
            for _,b in pairs(a.UnpurchasedButtons:GetChildren()) do
                if tostring(b.Neon.Color) == "1, 1, 0" and tonumber(b:GetAttribute("RebirthAmount")) <= game:GetService("Players").LocalPlayer.leaderstats.Rebirths.Value then
                    local mag = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - b.Gradient.Position).magnitude
                    if mag < dist then
                        dist = mag 
                        thing = b
                    end
                end
            end
        end
    end
    return thing
end
local function fix()
    for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
        if a.Owner.Value == game.Players.LocalPlayer then
            for _,b in pairs(a.PurchasedObjects:GetChildren()) do
                if table.find({"Large Oil 1","Large Oil 2","Large Oil 3","Large Oil 4","Large Oil 5","Large Oil 6","Oil 1","Oil 2","Oil 3","Oil 4","Oil 5","Oil 6"},b.Name) then
                    if b:FindFirstChild("Broken") and b.Broken.Value == true then
                        for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
                            if a.Owner.Value == game.Players.LocalPlayer then
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = a.Essentials.CashCollector.CFrame
                                wait(1)
                                firetouchinterest(a.Essentials.CashCollector, game.Players.LocalPlayer.Character["Right Leg"], 0)
                                wait(.1)
                                firetouchinterest(a.Essentials.CashCollector, game.Players.LocalPlayer.Character["Right Leg"], 1)
                                wait(.1)
                            end
                        end
                        wait(0.5)
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = b.ElectricalBox.Effect.CFrame
                        wait(1)
                        fireproximityprompt(b.ElectricalBox.Effect.OilExtractor)
                    end
                end
            end
        end
    end
end

spawn(function()
    pcall(function()
        while wait() do
            pcall(function()
                if _G.AutoRebirth then
                    pcall(function()
                        if fix() then
                            fix()
                        elseif game:GetService("Players").LocalPlayer.leaderstats.Cash.Value <= 0 then
                            for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
                                if a.Owner.Value == game.Players.LocalPlayer then
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = a.PurchasedObjects["Oil 1"].CB1.CFrame
                                    wait(0.1)
                                    fireproximityprompt(a.PurchasedObjects["Oil 1"].CB1.DefaultExtractor)
                                    wait(1)
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = a.Essentials.CashCollector.CFrame
                                    wait(.1)
                                    firetouchinterest(a.Essentials.CashCollector, game.Players.LocalPlayer.Character["Right Leg"], 0)
                                    wait(.1)
                                    firetouchinterest(a.Essentials.CashCollector, game.Players.LocalPlayer.Character["Right Leg"], 1)
                                    wait(.1)
                                end
                            end
                        elseif Rebirth() then
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Rebirth().Gradient.CFrame
                            wait(1)
                            firetouchinterest(Rebirth().Gradient, game.Players.LocalPlayer.Character["Right Leg"], 0)
                            wait(.1)
                            firetouchinterest(Rebirth().Gradient, game.Players.LocalPlayer.Character["Right Leg"], 1)
                            wait(.1)
                        elseif Oil() then
                            if tostring(Oil().Neon.Color) == "0, 1, 0" or tostring(Oil().Neon.Color) == "0.0156863, 0.686275, 0.921569" then
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Oil().Gradient.CFrame
                                wait(1)
                                firetouchinterest(Oil().Gradient, game.Players.LocalPlayer.Character["Right Leg"], 0)
                                wait(.1)
                                firetouchinterest(Oil().Gradient, game.Players.LocalPlayer.Character["Right Leg"], 1)
                                wait(.1)
                            elseif tostring(Oil().Neon.Color) == "1, 0, 0" then
                                for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
                                    if a.Owner.Value == game.Players.LocalPlayer then
                                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = a.Essentials.CashCollector.CFrame
                                        wait(1)
                                        firetouchinterest(a.Essentials.CashCollector, game.Players.LocalPlayer.Character["Right Leg"], 0)
                                        wait(.1)
                                        firetouchinterest(a.Essentials.CashCollector, game.Players.LocalPlayer.Character["Right Leg"], 1)
                                        wait(.1)
                                    end
                                end
                            end
                        elseif Misc() then
                            if tostring(Misc().Neon.Color) == "0, 1, 0" or tostring(Misc().Neon.Color) == "0.0156863, 0.686275, 0.921569" then
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Misc().Gradient.CFrame
                                wait(1)
                                firetouchinterest(Misc().Gradient, game.Players.LocalPlayer.Character["Right Leg"], 0)
                                wait(.1)
                                firetouchinterest(Misc().Gradient, game.Players.LocalPlayer.Character["Right Leg"], 1)
                                wait(.1)
                            elseif tostring(Misc().Neon.Color) == "1, 0, 0" then
                                for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
                                    if a.Owner.Value == game.Players.LocalPlayer then
                                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = a.Essentials.CashCollector.CFrame
                                        wait(1)
                                        firetouchinterest(a.Essentials.CashCollector, game.Players.LocalPlayer.Character["Right Leg"], 0)
                                        wait(.1)
                                        firetouchinterest(a.Essentials.CashCollector, game.Players.LocalPlayer.Character["Right Leg"], 1)
                                        wait(.1)
                                    end
                                end
                            end
                        elseif game:GetService("Players").LocalPlayer.PlayerGui.RebirthGui.RebirthButton.Visible == true then
                            if game:GetService("Players").LocalPlayer.leaderstats.Cash.Value >= 500000 then
                                game:GetService("ReplicatedStorage"):WaitForChild("RebirthEVT"):FireServer()
                            else
                                for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
                                    if a.Owner.Value == game.Players.LocalPlayer then
                                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = a.Essentials.CashCollector.CFrame
                                        wait(.1)
                                        firetouchinterest(a.Essentials.CashCollector, game.Players.LocalPlayer.Character["Right Leg"], 0)
                                        wait(.1)
                                        firetouchinterest(a.Essentials.CashCollector, game.Players.LocalPlayer.Character["Right Leg"], 1)
                                        wait(.1)
                                    end
                                end
                            end
                        end
                    end)
                end
            end)
        end
    end)
end)
spawn(function()
    pcall(function()
        while wait() do
            pcall(function()
                if table.find(_G.SelectTraget,"Players") and _G.SpamRPG then
                    for _,v in pairs(workspace:GetChildren()) do
                        if v.Name ~= game.Players.LocalPlayer.Name and v:FindFirstChild("HumanoidRootPart") and not table.find(_G.WL,v.Name) then
                            game:GetService("ReplicatedStorage"):WaitForChild("RocketSystem"):WaitForChild("RocketHit"):FireServer(v.HumanoidRootPart.Position,Vector3.yAxis,game:GetService("Players").LocalPlayer.Character.RPG,game:GetService("Players").LocalPlayer.Character.RPG,v.HumanoidRootPart)
                            wait()
                        end
                    end
                end
            end)
        end
    end)
end)
local function Shield()
    local dist, thing = math.huge
    for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
        if a.Owner.Value ~= game.Players.LocalPlayer and a.PurchasedObjects:FindFirstChild("Base Shield") and a.PurchasedObjects["Base Shield"]:FindFirstChild("Shield") and a.PurchasedObjects["Base Shield"]["Shield"]:FindFirstChild("Shield4") then
            local mag = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - a.WorldPivot.Position).magnitude
            if mag < dist then
                dist = mag 
                thing = a
            end
        end
    end
    return thing
end
spawn(function()
    pcall(function()
        while wait() do
            pcall(function()
                if table.find(_G.SelectTraget,"Base Shield") and _G.SpamRPG then
                    pcall(function()
                        game:GetService("ReplicatedStorage"):WaitForChild("RocketSystem"):WaitForChild("RocketHit"):FireServer(Shield().PurchasedObjects["Base Shield"].Shield.Shield4.Position,Vector3.yAxis,game:GetService("Players").LocalPlayer.Character.RPG,game:GetService("Players").LocalPlayer.Character.RPG,Shield().PurchasedObjects["Base Shield"].Shield.Shield4)
                    end)
                end
            end)
        end
    end)
end) 

local function Ship()
    local dist, thing = math.huge
    for _,v in pairs(workspace["Game Systems"]["Gunship Workspace"]:GetChildren()) do
        if v.Name == "AC-130 Gunship" then
            local mag = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.MainPart.Position).magnitude
            if mag < dist then
                dist = mag 
                thing = v
            end
        end
    end
    return thing
end
spawn(function()
    pcall(function()
        while wait() do
            pcall(function()
                if table.find(_G.SelectTraget,"AC-130 Gunship") and _G.SpamRPG then
                    pcall(function()
                        game:GetService("ReplicatedStorage"):WaitForChild("RocketSystem"):WaitForChild("RocketHit"):FireServer(Ship().MainPart.Position,Vector3.yAxis,game:GetService("Players").LocalPlayer.Character.RPG,game:GetService("Players").LocalPlayer.Character.RPG,Ship().MainPart)
                    end)
                end
            end)
        end
    end)
end)
spawn(function()
    pcall(function()
        while wait() do
            pcall(function()
                if _G.FarmVehiclePart then
                    pcall(function()
                        for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
                            if a.Owner.Value == game.Players.LocalPlayer then
                                for _,v in pairs(workspace["Game Systems"]["Crate Workspace"]:GetChildren()) do
                                    if _G.FarmVehiclePart == true then
                                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
                                        wait(1)
                                    end
                                    if _G.FarmVehiclePart == true then
                                        fireproximityprompt(v.StealPrompt)
                                        wait(2)
                                    end
                                    if _G.FarmVehiclePart == true then
                                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = a.Essentials["Oil Collector"].CratePromptPart.CFrame
                                        wait(1)
                                    end
                                    if _G.FarmVehiclePart == true then
                                        fireproximityprompt(a.Essentials["Oil Collector"].CratePromptPart.SellPrompt)
                                        wait(1)
                                    end
                                end
                            end
                        end
                    end)
                end
            end)
        end
    end)
end)

spawn(function()
    pcall(function()
        while wait() do
            pcall(function()
                if _G.FarmOil then
                    pcall(function()
                        if game.Players.LocalPlayer.Character:FindFirstChild("Barrel") then
                            for _,a in pairs(workspace.Tycoon.Tycoons:GetChildren()) do
                                if a.Owner.Value == game.Players.LocalPlayer then
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = workspace.Tycoon.Tycoons.Hotel.Essentials["Oil Collector"].Collector.BarrelSlot.CFrame
                                    wait(2)
                                    fireproximityprompt(a.Essentials["Oil Collector"].Collector.dropPrompt)
                                end
                            end
                        else
                            for i = 1,2 do
                                if workspace.Beams:FindFirstChild("Oil Rig"..tostring(i)) then
                                    if not workspace["Game Systems"].Warehouses["Oil Rig"..tostring(i)]["Oil Capture"]:FindFirstChild("Barrel Template") then
                                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = workspace.Beams:FindFirstChild("Oil Rig"..tostring(i)).CFrame
                                    else
                                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = workspace.Beams:FindFirstChild("Oil Rig"..tostring(i)).CFrame
                                        wait(2)
                                        fireproximityprompt(workspace["Game Systems"].Warehouses["Oil Rig"..tostring(i)]["Oil Capture"]["Barrel Template"].PromptPart.BarrelPickup)
                                        wait(1)
                                    end
                                end
                            end
                        end
                    end)
                end
            end)
        end
    end)
end)

spawn(function()
    pcall(function()
        while wait() do
            pcall(function()
                if _G.ESPOperations then
                    pcall(function()
                        for _,v in pairs(workspace["Game Systems"].Operations:GetChildren()) do
                            for _,vv in pairs(v:GetChildren()) do
                                if vv:FindFirstChild("Collection") and vv.Collection:FindFirstChildOfClass("ProximityPrompt") and not vv.Collection:FindFirstChildOfClass("BillboardGui") then
                                    local BillboardGui = Instance.new("BillboardGui")
                                    local TextLabel = Instance.new("TextLabel")
                                    BillboardGui.Parent = vv.Collection
                                    BillboardGui.AlwaysOnTop = true
                                    BillboardGui.Size = UDim2.new(0, 50, 0, 50)
                                    BillboardGui.StudsOffset = Vector3.new(0, 2, 0)
                                    TextLabel.Parent = BillboardGui
                                    TextLabel.BackgroundColor3 = Color3.new(1, 1, 1)
                                    TextLabel.BackgroundTransparency = 1
                                    TextLabel.Size = UDim2.new(1, 0, 1, 0)
                                    TextLabel.Text = vv.Name
                                    TextLabel.TextColor3 = Color3.new(1, 0, 0)
                                    TextLabel.TextScaled = true
                                end
                            end
                        end
                    end)
                end
            end)
        end
    end)
end)































































































local Tab = Window:CreateTab("Setting/Misc")
local Sector = Tab:CreateSector("Section1", "left")
Sector:AddTextbox("Speed" , "16" , function(w)
    _G.Speed = w
end)
Sector:AddTextbox("Jump" , "50" , function(w)
    _G.Jump = w
end)
Sector:AddToggle("WalkSpeed", false, function(t)
    _G.WalkSpeed = t
end)
Sector:AddToggle("JumpPower", false, function(t)
    _G.JumpPower = t
end)
Sector:AddToggle("CtrlClickTP", false, function(t)
    _G.CtrlClickTP = t
end)
Sector:AddButton("Rejoin" , function()
    game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, game.JobId, game:GetService("Players").LocalPlayer)
end)
Sector:AddButton("ResetCamera" , function()
    game:GetService("Workspace").CurrentCamera:Destroy()
    wait(.1)
    game:GetService("Workspace").CurrentCamera.CameraSubject = game:GetService("Players").LocalPlayer.Character.Humanoid
    game:GetService("Workspace").CurrentCamera.CameraType = "Custom"
    game:GetService("Players").LocalPlayer.CameraMinZoomDistance = .5
    game:GetService("Players").LocalPlayer.CameraMaxZoomDistance = 100000
    game:GetService("Players").LocalPlayer.CameraMode = "Classic"
end)
Sector:AddButton("InstantProximityPrompt" , function()
    game:GetService("ProximityPromptService").PromptButtonHoldBegan:Connect(function(prompt)
        prompt.HoldDuration = 0
    end)
end)
spawn(function()
    pcall(function()
        while wait() do
            pcall(function()
                if _G.JumpPower then
                    pcall(function()
                        wait()
                        local HumanModCons = {}
                        local Char = game.Players.LocalPlayer.Character or workspace:FindFirstChild(game.Players.LocalPlayer.Name)
                        local Human = Char and Char:FindFirstChildWhichIsA("Humanoid")
                        local function JumpPowerChange()
                            if Char and Human and _G.JumpPower then
                                if game.Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid').UseJumpPower then
                                    game.Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid').JumpPower = tonumber(_G.Jump)
                                else
                                    game.Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid').JumpHeight  = tonumber(_G.Jump)
                                end
                            end
                        end
                        JumpPowerChange()
                        HumanModCons.jpLoop = (HumanModCons.jpLoop and HumanModCons.jpLoop:Disconnect() and false) or Human:GetPropertyChangedSignal("JumpPower"):Connect(JumpPowerChange)
                        HumanModCons.jpCA = (HumanModCons.jpCA and HumanModCons.jpCA:Disconnect() and false) or game.Players.LocalPlayer.CharacterAdded:Connect(function(v)
                            Char, Human = v, v:WaitForChild("Humanoid")
                            JumpPowerChange()
                            HumanModCons.jpLoop = (HumanModCons.jpLoop and HumanModCons.jpLoop:Disconnect() and false) or Human:GetPropertyChangedSignal("JumpPower"):Connect(JumpPowerChange)
                        end)
                        wait(9e9)
                    end)
                end
            end)
        end
    end)
end)
spawn(function()
    pcall(function()
        while wait() do
            pcall(function()
                if _G.WalkSpeed then
                    pcall(function()
                        wait()
                        local HumanModCons = {}
                        local Char = game.Players.LocalPlayer.Character or workspace:FindFirstChild(game.Players.LocalPlayer.Name)
                        local Human = Char and Char:FindFirstChildWhichIsA("Humanoid")
                        local function WalkSpeedChange()
                            if Char and Human and _G.WalkSpeed then
                                Human.WalkSpeed = tonumber(_G.Speed)
                            end
                        end
                        WalkSpeedChange()
                        HumanModCons.wsLoop = (HumanModCons.wsLoop and HumanModCons.wsLoop:Disconnect() and false) or Human:GetPropertyChangedSignal("WalkSpeed"):Connect(WalkSpeedChange)
                        HumanModCons.wsCA = (HumanModCons.wsCA and HumanModCons.wsCA:Disconnect() and false) or game.Players.LocalPlayer.CharacterAdded:Connect(function(v)
                            Char, Human = v, v:WaitForChild("Humanoid")
                            WalkSpeedChange()
                            HumanModCons.wsLoop = (HumanModCons.wsLoop and HumanModCons.wsLoop:Disconnect() and false) or Human:GetPropertyChangedSignal("WalkSpeed"):Connect(WalkSpeedChange)
                        end)
                        wait(9e9)
                    end)
                end
            end)
        end
    end)
end)
local UIS = game:GetService("UserInputService")
local Player = game.Players.LocalPlayer
local Mouse = Player:GetMouse()
function GetCharacter()
    return game.Players.LocalPlayer.Character
    end
    function Teleport(pos)
    local Char = GetCharacter()
    if Char then
        Char:MoveTo(pos)
    end
end
UIS.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 and UIS:IsKeyDown(Enum.KeyCode.LeftControl) and _G.CtrlClickTP == true then
        Teleport(Mouse.Hit.p)
    end
end)

local Sector = Tab:CreateSector("Section2", "Right")
Sector:AddKeybind("Keybind GUI", "Insert",true, function()
    for i, v in pairs(game:GetService("CoreGui"):GetChildren()) do
        if v:FindFirstChild("main") then
            v.main.Visible = not v.main.Visible;
        end
    end
end)
Sector:AddToggle("CloseGuiAfterExecute", false, function(o)
    _G.CloseGuiAfterExecute = o
end)
Sector:AddToggle("RejoinAfterKick", false, function(o)
    _G.rejoinKick = o
end)
spawn(function()
    getgenv().rejoin = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(Kick)
        if ((Kick.Name == "ErrorPrompt") and Kick:FindFirstChild("MessageArea") and Kick.MessageArea:FindFirstChild("ErrorFrame")) then
            if _G.rejoinKick == true then
                game:GetService("TeleportService"):Teleport(game.PlaceId)
            end
        end
    end)
end)
Sector:AddTextbox("FPS" , "20" , function(w)
    _G.FPS = w
end)
Sector:AddToggle("SetFpsCap", false, function(o)
    _G.Fpscap = o
end)
Sector:AddButton("infiniteyield" , function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
end)
Sector:AddButton("DarkDex" , function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/infyiff/backup/main/dex.lua", true))()
end)
Sector:AddButton("RemoteSpy" , function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/SmellLikeHacker/IDK/main/RemoteSpy", true))()
end)
Sector:AddButton("CopyDiscordLink" , function()
    setclipboard("https://discord.gg/48geaWzacy")
end)
Sector:AddButton("JoinDiscord" , function()
    request = http_request or request or HttpPost or syn.request
    request({Url = "http://127.0.0.1:6463/rpc?v=1",Method = "POST",Headers = {["Content-Type"] = "application/json",["origin"] = "https://discord.com",},Body = game:GetService("HttpService"):JSONEncode({["args"] = {["code"] = "48geaWzacy",},["cmd"] = "INVITE_BROWSER",["nonce"] = "."})})
end)
Sector:AddButton("SUPER SECRET BUTTON" , function()
    local soundId = "rbxassetid://6454805792"
    local sound = Instance.new("Sound")
    sound.SoundId = soundId
    sound.Volume = 10
    sound.Looped = true
    sound.Parent = game.Players.LocalPlayer.Character
    sound:Play()
end)
spawn(function()
    pcall(function()
        while task.wait() do
            pcall(function()
                game:GetService("Players").LocalPlayer.DevCameraOcclusionMode = "Invisicam"
                game:GetService("Players").LocalPlayer.CameraMaxZoomDistance = 100000
            end)
        end
    end)
end)
spawn(function()
    pcall(function()
        while wait() do
            pcall(function()
                if _G.CloseGuiAfterExecute then
                    pcall(function()
                        wait()
                        for i,v in pairs(game:GetService("CoreGui"):GetChildren()) do
                            if v:FindFirstChild("main") then
                                v.main.Visible = not v.main.Visible
                            end
                        end
                        wait(9e9)
                    end)
                end
            end)
        end
    end)
end)
spawn(function()
    pcall(function()
        while wait(1) do
            pcall(function()
                if _G.Fpscap then
                    setfpscap(tonumber(_G.FPS))
                end
            end)
        end
    end)
end)
game:GetService("Players").LocalPlayer.Idled:connect(function()
    game:GetService("VirtualUser"):CaptureController()
    game:GetService("VirtualUser"):ClickButton2(Vector2.new())
end)
library:ConfigSystem("WarTycoon"):Load()
while wait(1) do
    pcall(function()
        library:ConfigSystem("WarTycoon"):Save()
    end)
end
