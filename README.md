-- Lokos Hub Panel Script
-- Auto-opening panel with all options visible

local player = game.Players.LocalPlayer
local mouse = player:GetMouse()

-- Create the Lokos Hub panel
local lokosHubPanel = Instance.new("ScreenGui")
lokosHubPanel.Name = "LokosHubPanel"
lokosHubPanel.Parent = player:WaitForChild("PlayerGui")

-- Create the panel window
local panelWindow = Instance.new("Frame")
panelWindow.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
panelWindow.BorderSizePixel = 2
panelWindow.Size = UDim2.new(0, 300, 0, 400)
panelWindow.Position = UDim2.new(0, 10, 0, 10)
panelWindow.Visible = true  -- Always visible when script runs
panelWindow.Parent = lokosHubPanel

-- Create title label
local titleLabel = Instance.new("TextLabel")
titleLabel.Text = "Lokos Hub"
titleLabel.BackgroundTransparency = 1
titleLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
titleLabel.TextSize = 20
titleLabel.Size = UDim2.new(0, 300, 0, 30)
titleLabel.Position = UDim2.new(0, 0, 0, 0)
titleLabel.Parent = panelWindow

-- Create tabs frame
local tabsFrame = Instance.new("Frame")
tabsFrame.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
tabsFrame.Size = UDim2.new(0, 300, 0, 30)
tabsFrame.Position = UDim2.new(0, 0, 0, 30)
tabsFrame.Parent = panelWindow

-- Create tab buttons
local mainTabButton = Instance.new("TextButton")
mainTabButton.Text = "Main"
mainTabButton.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
mainTabButton.BorderSizePixel = 0
mainTabButton.Size = UDim2.new(0, 100, 0, 30)
mainTabButton.Position = UDim2.new(0, 0, 0, 0)
mainTabButton.Parent = tabsFrame

-- Create main tab content frame
local mainTabContent = Instance.new("Frame")
mainTabContent.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
mainTabContent.Size = UDim2.new(0, 300, 0, 340)
mainTabContent.Position = UDim2.new(0, 0, 0, 60)
mainTabContent.Visible = true
mainTabContent.Parent = panelWindow

-- Create Aimbot option
local aimbotOption = Instance.new("Frame")
aimbotOption.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
aimbotOption.Size = UDim2.new(0, 300, 0, 40)
aimbotOption.Position = UDim2.new(0, 0, 0, 0)
aimbotOption.Parent = mainTabContent

local aimbotLabel = Instance.new("TextLabel")
aimbotLabel.Text = "Aimbot"
aimbotLabel.BackgroundTransparency = 1
aimbotLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
aimbotLabel.Size = UDim2.new(0, 200, 0, 40)
aimbotLabel.Position = UDim2.new(0, 0, 0, 0)
aimbotLabel.Parent = aimbotOption

local aimbotToggle = Instance.new("TextButton")
aimbotToggle.Text = "ON"  -- Default ON
aimbotToggle.BackgroundColor3 = Color3.fromRGB(50, 255, 50)
aimbotToggle.Size = UDim2.new(0, 80, 0, 30)
aimbotToggle.Position = UDim2.new(0, 210, 0, 5)
aimbotToggle.Parent = aimbotOption

-- Create Recoil option
local recoilOption = Instance.new("Frame")
recoilOption.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
recoilOption.Size = UDim2.new(0, 300, 0, 40)
recoilOption.Position = UDim2.new(0, 0, 0, 50)
recoilOption.Parent = mainTabContent

local recoilLabel = Instance.new("TextLabel")
recoilLabel.Text = "Recoil Control"
recoilLabel.BackgroundTransparency = 1
recoilLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
recoilLabel.Size = UDim2.new(0, 200, 0, 40)
recoilLabel.Position = UDim2.new(0, 0, 0, 0)
recoilLabel.Parent = recoilOption

local recoilToggle = Instance.new("TextButton")
recoilToggle.Text = "ON"  -- Default ON
recoilToggle.BackgroundColor3 = Color3.fromRGB(50, 255, 50)
recoilToggle.Size = UDim2.new(0, 80, 0, 30)
recoilToggle.Position = UDim2.new(0, 210, 0, 5)
recoilToggle.Parent = recoilOption

-- Create ESP option
local espOption = Instance.new("Frame")
espOption.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
espOption.Size = UDim2.new(0, 300, 0, 40)
espOption.Position = UDim2.new(0, 0, 0, 100)
espOption.Parent = mainTabContent

local espLabel = Instance.new("TextLabel")
espLabel.Text = "ESP"
espLabel.BackgroundTransparency = 1
espLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
espLabel.Size = UDim2.new(0, 200, 0, 40)
espLabel.Position = UDim2.new(0, 0, 0, 0)
espLabel.Parent = espOption

local espToggle = Instance.new("TextButton")
espToggle.Text = "ON"  -- Default ON
espToggle.BackgroundColor3 = Color3.fromRGB(50, 255, 50)
espToggle.Size = UDim2.new(0, 80, 0, 30)
espToggle.Position = UDim2.new(0, 210, 0, 5)
espToggle.Parent = espOption

-- Create FOV option
local fovOption = Instance.new("Frame")
fovOption.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
fovOption.Size = UDim2.new(0, 300, 0, 40)
fovOption.Position = UDim2.new(0, 0, 0, 150)
fovOption.Parent = mainTabContent

local fovLabel = Instance.new("TextLabel")
fovLabel.Text = "FOV"
fovLabel.BackgroundTransparency = 1
fovLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
fovLabel.Size = UDim2.new(0, 200, 0, 40)
fovLabel.Position = UDim2.new(0, 0, 0, 0)
fovLabel.Parent = fovOption

local fovSlider = Instance.new("Slider")
fovSlider.Name = "FOVSlider"
fovSlider.Min = 0
fovSlider.Max = 100
fovSlider.Value = 100  -- Default max
fovSlider.Size = UDim2.new(0, 200, 0, 20)
fovSlider.Position = UDim2.new(0, 0, 0, 20)
fovSlider.Parent = fovOption

local fovValueLabel = Instance.new("TextLabel")
fovValueLabel.Text = "100%"
fovValueLabel.BackgroundTransparency = 1
fovValueLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
fovValueLabel.Size = UDim2.new(0, 100, 0, 40)
fovValueLabel.Position = UDim2.new(0, 200, 0, 0)
fovValueLabel.Parent = fovOption

-- Create close button
local closeButton = Instance.new("TextButton")
closeButton.Text = "X"
closeButton.BackgroundColor3 = Color3.fromRGB(255, 50, 50)
closeButton.BorderSizePixel = 0
closeButton.Size = UDim2.new(0, 30, 0, 30)
closeButton.Position = UDim2.new(0, 270, 0, 0)
closeButton.Parent = panelWindow

-- Tab functionality
mainTabButton.MouseButton1Click:Connect(function()
    mainTabContent.Visible = true
end)

-- Toggle functionality
aimbotToggle.MouseButton1Click:Connect(function()
    if aimbotToggle.Text == "ON" then
        aimbotToggle.Text = "OFF"
        aimbotToggle.BackgroundColor3 = Color3.fromRGB(255, 50, 50)
    else
        aimbotToggle.Text = "ON"
        aimbotToggle.BackgroundColor3 = Color3.fromRGB(50, 255, 50)
    end
end)

recoilToggle.MouseButton1Click:Connect(function()
    if recoilToggle.Text == "ON" then
        recoilToggle.Text = "OFF"
        recoilToggle.BackgroundColor3 = Color3.fromRGB(255, 50, 50)
    else
        recoilToggle.Text = "ON"
        recoilToggle.BackgroundColor3 = Color3.fromRGB(50, 255, 50)
    end
end)

espToggle.MouseButton1Click:Connect(function()
    if espToggle.Text == "ON" then
        espToggle.Text = "OFF"
        espToggle.BackgroundColor3 = Color3.fromRGB(255, 50, 50)
    else
        espToggle.Text = "ON"
        espToggle.BackgroundColor3 = Color3.fromRGB(50, 255, 50)
    end
end)

-- Update FOV value display
fovSlider.MouseButton1Up:Connect(function()
    fovValueLabel.Text = math.floor(fovSlider.Value) .. "%"
end)

-- Panel visibility toggle
panelWindow.Visible = true  -- Force visible

-- Add aimbot functionality
game:GetService("RunService").Heartbeat:Connect(function()
    if aimbotToggle.Text == "ON" then
        local player = game.Players.LocalPlayer
        local character = player.Character or player.CharacterAdded:Wait()
        local camera = workspace.CurrentCamera
        
        -- Get all players except the local player
        local players = game.Players:GetPlayers()
        for _, target in pairs(players) do
            if target ~= player then
                local targetCharacter = target.Character
                if targetCharacter then
                    local head = targetCharacter:FindFirstChild("Head")
                    if head then
                        local targetPosition = head.Position
                        local screenPoint, onScreen = camera:WorldToViewportPoint(targetPosition)
                        
                        if onScreen then
                            local direction = Vector3.new(screenPoint.X, screenPoint.Y, 0) - Vector3.new(mouse.X, mouse.Y, 0)
                            local normalizedDirection = direction.Unit * 0.05
                        
                            mouse.X = mouse.X + normalizedDirection.X
                            mouse.Y = mouse.Y + normalizedDirection.Y
                        end
                    end
                end
            end
        end
    end
end)
