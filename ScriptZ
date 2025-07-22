-- Load Rayfield UI Library
local Rayfield = loadstring(game:HttpGet("https://sirius.menu/rayfield"))()

-- Services
local RS = game:GetService("ReplicatedStorage")
local RunS = game:GetService("RunService")
local Enemies = workspace:WaitForChild("Enemies")
local HurtEnemy = RS:WaitForChild("HurtEnemy")

-- Control Variable
local Enabled = true

-- Original Auto-Damage Logic
RunS.RenderStepped:Connect(function()
    if Enabled then
        for _, e in pairs(Enemies:GetChildren()) do
            if e:IsA("Model") and e:FindFirstChild("Humanoid") and e:FindFirstChild("HumanoidRootPart") then
                HurtEnemy:FireServer(e, 999999999999999999) -- Damage
            end
        end
    end
end)

-- GUI Setup
local Window = Rayfield:CreateWindow({
    Name = "Noobs Must Die",
    LoadingTitle = "Noobs Must Die",
    LoadingSubtitle = "by You",
    ConfigurationSaving = {
        Enabled = false
    },
    KeySystem = true,
    KeySettings = {
        Title = "Key Required",
        Subtitle = "Enter the access key to proceed",
        Note = "Key: Freemium-1029384756",
        FileName = "NoobsMustDieKeyData",
        SaveKey = true,
        GrabKeyFromSite = false,
        Key = "Freemium-1029384756"
    }
})

-- Create "Destroy" Tab
local DestroyTab = Window:CreateTab("Destroy", 4483362458)

-- Toggle for Auto Kill
DestroyTab:CreateToggle({
    Name = "Enable Auto Kill",
    CurrentValue = true,
    Flag = "AutoKillToggle",
    Callback = function(Value)
        Enabled = Value
    end,
})
