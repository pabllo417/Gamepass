--[[ All Hubs/Script Are Come From Trustful Sources And If Some Code Aren't Working Please DM ikura0 In discord and report It Lr U Can request What to Add ]]--


--[[ Notification]]--

function Notify(text)
    local g, label = Instance.new("ScreenGui", game.Players.LocalPlayer.PlayerGui), Instance.new("TextLabel")
    label.Parent = g
    label.Text = text 
    label.Size = UDim2.new(0, 200, 0, 50)
    label.Position = UDim2.new(0.5, -100, 1, -50)
    label.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
    label.TextColor3 = Color3.new(1, 1, 1)
    label.BackgroundTransparency = 0.5

    corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0, 6)
    corner.Parent = label

    game:GetService("TweenService"):Create(label, TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {Position = UDim2.new(0.5, -100, 0.9, -25)}):Play()
    wait(3)
    label:Destroy()
end

--[[ Anti AFK ]]--

iku = coroutine.create(function() 
 VirtualUser = game:GetService("VirtualUser")
    game:GetService("Players").LocalPlayer.Idled:Connect(function()
        VirtualUser:CaptureController()
        VirtualUser:ClickButton2(Vector2.new())
    end)
end) 
coroutine.resume(iku)

--[[ Random function ]]--

function ClickDet()
    spawn(function()
        for _, descendant in ipairs(workspace:GetDescendants()) do
            if descendant:IsA("ClickDetector") then
                task.spawn(function()
                    fireclickdetector(descendant)
                end)
            end
        end
    end) 
end

function proxi()
spawn(function()
    for _, descendant in ipairs(workspace:GetDescendants()) do
        if descendant:IsA("ProximityPrompt") then
            fireproximityprompt(descendant)
        end
    end
end) 
end

function CframeGen()
    local plyr = game.Players.LocalPlayer
    local chr = plyr.Character
    setclipboard(("game.Players.LocalPlayer.Character:PivotTo(CFrame.new(%s))"):format(tostring(chr:GetPrimaryPartCFrame())))
end

function HidePlayer()
    while true do
        for _, player in pairs(game.Players:GetPlayers()) do
            if player ~= game.Players.LocalPlayer and player.Character then
                player.Character:Destroy()
            end
        end
        wait(5)
    end
end

function DelPP()
    for _, v in next, workspace:GetDescendants() do
        if v:IsA("ProximityPrompt") then
            v.HoldDuration = 0
        end
    end
end

function Touchinterest()
    spawn(function()
        for _, descendant in ipairs(workspace:GetDescendants()) do
            if descendant:IsA("TouchTransmitter") and
                    game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character.PrimaryPart then
                task.spawn(function()
                    firetouchinterest(descendant:FindFirstAncestorWhichIsA("Part"),
                        game.Players.LocalPlayer.Character.PrimaryPart, 1)
                    task.wait()
                    firetouchinterest(descendant:FindFirstAncestorWhichIsA("Part"),
                        game.Players.LocalPlayer.Character.PrimaryPart, 0)
                end)
            end
        end
    end)
end

Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/wizard"))()

function ThisActuallyCool()
    local currentTime = os.date("*t")
    local hour = currentTime.hour

    if hour >= 6 and hour < 12 then
        return "🌅"
    elseif hour >= 12 and hour < 15 then
        return "☀️🕛"
    elseif hour >= 15 and hour < 18 then
        return "🌞"
    elseif hour >= 18 or hour < 6 then
        return "🌙"
    else
        return "🌄"
    end
end

PhantomForcesWindow = Library:NewWindow("Rass Script " .. ThisActuallyCool())

WeLoveCat = PhantomForcesWindow:NewSection("Script")
--[[ Hub Script ]] --
WeLoveCat:CreateButton("Wyvern", function() loadstring(game:HttpGet("https://raw.githubusercontent.com/wyvernleaker/WYVERN/main/WYVERN.lua",true))()
Notify("Wyvern Loading.....")
end)

WeLoveCat:CreateButton("Infinite Yield", function() loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
Notify("Infinite Yield Loaded")
end)

WeLoveCat:CreateButton("RemoteSpy Mobile", function()   loadstring(game:HttpGet("https://raw.githubusercontent.com/REDzHUB/RS/main/SimpleSpyMobile"))()
Notify("SimpleSpy Loaded")
end)

WeLoveCat:CreateButton("Dark Dex New", function()   loadstring(game:HttpGet("https://raw.githubusercontent.com/Babyhamsta/RBLX_Scripts/main/Universal/BypassedDarkDexV3.lua", true))()
Notify("Dex V3 Loaded")
end)

WeLoveCat:CreateButton("V1 Player Hub", function()  loadstring(game:HttpGet("https://raw.githubusercontent.com/JustAP1ayer/PlayerHubOther/main/PlayerHubIngameUgcLimiteds.lua"))()
Notify("V1 PlayerHub Loaded")
end)

WeLoveCat:CreateButton("V2 Player Hub", function() loadstring(game:HttpGet(('https://raw.githubusercontent.com/JustAP1ayer/PlayerHubOther/main/PlayerHubIngameUgcLimitedsV2.lua')))()
  Notify("V2 Player Hub Loaded")
end)

--[[ 2nd Section UGC Script ]]--
local WeLoveCat2 = PhantomForcesWindow:NewSection("UGC")  

--[[ Redblue Lim Clicker ]]--

local ClickingSpeed = 0
local x, y, m = 55, 65.5, 1
local loopActive = false

WeLoveCat2:CreateToggle("Auto Buy", function(value)  
    loopActive = value
    spawn(function()
        while loopActive do 
            if game.CoreGui.PurchasePrompt.ProductPurchaseContainer.Animator:FindFirstChild("Prompt") and
                game.CoreGui.PurchasePrompt.ProductPurchaseContainer.Animator.Prompt:FindFirstChild("AlertContents") and
                game.CoreGui.PurchasePrompt.ProductPurchaseContainer.Animator.Prompt.AlertContents:FindFirstChild("Footer") and
                game.CoreGui.PurchasePrompt.ProductPurchaseContainer.Animator.Prompt.AlertContents.Footer:FindFirstChild("Buttons") and
                game.CoreGui.PurchasePrompt.ProductPurchaseContainer.Animator.Prompt.AlertContents.Footer.Buttons:FindFirstChild("2") and
                game.CoreGui.PurchasePrompt.ProductPurchaseContainer.Animator.Prompt.AlertContents.Footer.Buttons[2]:FindFirstChild("ButtonContent").ButtonMiddleContent and
                game.CoreGui.PurchasePrompt.ProductPurchaseContainer.Animator.Prompt.AlertContents.Footer.Buttons[2]:FindFirstChild("ButtonContent").ButtonMiddleContent:FindFirstChildOfClass("TextLabel") and tonumber(
                game.CoreGui.PurchasePrompt.ProductPurchaseContainer.Animator.Prompt.AlertContents.Footer.Buttons[2]:FindFirstChild("ButtonContent").ButtonMiddleContent:FindFirstChildOfClass("TextLabel").Text) <= tonumber(m) then

                local pos = game.CoreGui.PurchasePrompt.ProductPurchaseContainer.Animator.Prompt.AlertContents.Footer.Buttons[2].AbsolutePosition
                game:GetService("VirtualInputManager"):SendMouseButtonEvent(pos.X + tonumber(x), pos.Y + tonumber(y), 0, true, game, 1)
                wait()
                game:GetService("VirtualInputManager"):SendMouseButtonEvent(pos.X + tonumber(x), pos.Y + tonumber(y), 0, false, game, 1)
                wait(ClickingSpeed)
            else
                wait()
            end
        end
    end)
Notify("Auto Buy Limited")
end)

WeLoveCat2:CreateToggle("Auto Close Error", function(value)
    loopActive = value
    spawn(function()
        while loopActive do
            local pp = game.CoreGui.PurchasePrompt.ProductPurchaseContainer.Animator:FindFirstChild("Prompt")
            if pp and pp.AlertContents and pp.AlertContents.Footer and pp.AlertContents.Footer.Buttons and not pp.AlertContents.Footer.Buttons:FindFirstChild("2") then
                if pp.AlertContents.Footer.Buttons:FindFirstChild("1") then
                    local b1 = pp.AlertContents.Footer.Buttons[1].AbsolutePosition
                    game:GetService("VirtualInputManager"):SendMouseButtonEvent(b1.X + 55, b1.Y + 65.5, 0, true, game, 1)
                    wait()
                    game:GetService("VirtualInputManager"):SendMouseButtonEvent(b1.X + 55, b1.Y + 65.5, 0, false, game, 1)
                end
            end
            wait()
        end
    end)
 Notify("Auto Close Error")
end)

WeLoveCat2:CreateButton("Cframe Teleport", function() 
    CframeGen()
    Notify("Cframe Teleport Copied")
end)


WeLoveCat2:CreateButton("Hide Player Loop", function() 
    HidePlayer()
    Notify("All Player Are now Invisible")
end)

WeLoveCat2:CreateButton("Delete Proximity CD", function() 
    DelPP()
    Notify("Proximity Deleted")
end)

WeLoveCat2:CreateButton("Adonis Checker", function() 
loadstring(game:HttpGet("https://raw.githubusercontent.com/JustAScripts/Favorable/main/AdonisChecker.Lua",true))()
end)

WeLoveCat2:CreateButton("Adonis Bypassed", function()  loadstring(game:HttpGet("https://raw.githubusercontent.com/Pixeluted/adoniscries/main/Source.lua", true))() --[[ AdonisCries Is Famous Adonis Bypasser and The Only working The Catch is it's Ofbuscate But Ton Player used it and nothing Happen or any Bad ]]-- 

   Notify("Bypassed!")
end) 

--[[ Firing Function 3rd Section ]]--

WeLoveCat3 = PhantomForcesWindow:NewSection("Firing")

WeLoveCat3:CreateButton("Touchinterests", function()
    Touchinterest()
    Notify("Touchinterest Fired")
end)

WeLoveCat3:CreateButton("Clickedetector", function()
    ClickDet()
    Notify("Clickedetector Fired")
end)

WeLoveCat3:CreateButton("ProximityPrompt", function()
    proxi()
    Notify("Proximitypromt Fired")
end)

--[[ 4th Section Credit ]]--

WeLoveCat= PhantomForcesWindow:NewSection("WhatsApp")

WeLoveCat:CreateButton("Support By Joining", function()
setclipboard("https://whatsapp.com/channel/0029VaHheNk4SpkFwASXLd2Q")
end)

WeLoveCat:CreateButton("Destroy Gui", function()
game.CoreGui.WizardLibrary:Destroy()
Notify("Library Destroy")
end)

Notify(" Just A Script ")
