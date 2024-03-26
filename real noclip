local Workspace = game:GetService("Workspace")
local CoreGui = game:GetService("CoreGui")
local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local Noclip = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local OnButton = Instance.new("TextButton")
local OffButton = Instance.new("TextButton")
local Plr = Players.LocalPlayer
local Clipon = false
local Dragging = false
local Offset = Vector2.new(0, 0)

Noclip.Name = "Noclip"
Noclip.Parent = CoreGui

Frame.Name = "Frame"
Frame.Parent = Noclip
Frame.BackgroundColor3 = Color3.fromRGB(29, 103, 127, 1) -- Naranja fuerte
Frame.BorderColor3 = Color3.new(0.0588235, 0.0588235, 0.0588235)
Frame.BorderSizePixel = 2
Frame.Position = UDim2.new(0.5, -105, 0.5, -63) -- Centrado en la pantalla
Frame.Size = UDim2.new(0, 210, 0, 127)
Frame.Active = true
Frame.Draggable = true -- Hace que el marco sea arrastrable

Title.Name = "Title"
Title.Parent = Frame
Title.BackgroundColor3 = Color3.fromRGB(37, 150, 190) -- Naranja claro
Title.BorderSizePixel = 0
Title.Size = UDim2.new(1, 0, 0.3, 0)
Title.Font = Enum.Font.Highway
Title.Text = "Noclip by Axoim"
Title.TextColor3 = Color3.new(0, 0, 0) -- Negro
Title.TextScaled = true
Title.TextSize = 26
Title.TextStrokeColor3 = Color3.new(1, 1, 1) -- Blanco
Title.TextStrokeTransparency = 0

OnButton.Name = "OnButton"
OnButton.Parent = Frame
OnButton.BackgroundColor3 = Color3.fromRGB(37, 150, 190) -- Naranja claro
OnButton.BorderSizePixel = 0
OnButton.Position = UDim2.new(0.15, 0, 0.45, 0) -- Alineado en el centro vertical
OnButton.Size = UDim2.new(0.35, 0, 0.4, 0)
OnButton.Font = Enum.Font.Highway
OnButton.FontSize = Enum.FontSize.Size18
OnButton.Text = "On"
OnButton.TextColor3 = Color3.new(0, 0, 0) -- Negro
OnButton.TextScaled = true
OnButton.TextSize = 18
OnButton.TextStrokeColor3 = Color3.new(1, 1, 1) -- Blanco
OnButton.TextStrokeTransparency = 0

OffButton.Name = "OffButton"
OffButton.Parent = Frame
OffButton.BackgroundColor3 = Color3.fromRGB(37, 150, 190) -- Naranja claro
OffButton.BorderSizePixel = 0
OffButton.Position = UDim2.new(0.5, 0, 0.45, 0) -- Alineado en el centro vertical
OffButton.Size = UDim2.new(0.35, 0, 0.4, 0)
OffButton.Font = Enum.Font.Highway
OffButton.FontSize = Enum.FontSize.Size18
OffButton.Text = "Off"
OffButton.TextColor3 = Color3.new(0, 0, 0) -- Negro
OffButton.TextScaled = true
OffButton.TextSize = 18
OffButton.TextStrokeColor3 = Color3.new(1, 1, 1) -- Blanco
OffButton.TextStrokeTransparency = 0

local function ToggleNoclip(enabled)
    Clipon = enabled
    if enabled then
        for a, b in pairs(Workspace:GetChildren()) do
            if b.Name == Plr.Name then
                for i, v in pairs(b:GetDescendants()) do
                    if v:IsA("BasePart") then
                        v.CanCollide = false
                    end
                end
            end
        end
    else
        for a, b in pairs(Workspace:GetChildren()) do
            if b.Name == Plr.Name then
                for i, v in pairs(b:GetDescendants()) do
                    if v:IsA("BasePart") then
                        v.CanCollide = true
                    end
                end
            end
        end
    end
end

OnButton.MouseButton1Click:Connect(function()
    ToggleNoclip(true)
end)

OffButton.MouseButton1Click:Connect(function()
    ToggleNoclip(false)
end)

Frame.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        Dragging = true
        Offset = input.Position - Frame.Position
        Frame.CaptureFocus = true
    end
end)

UserInputService.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement then
        if Dragging then
            Frame.Position = UDim2.new(0, input.Position.X - Offset.X, 0, input.Position.Y - Offset.Y)
        end
    end
end)

UserInputService.InputEnded:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        Dragging = false
        Frame.CaptureFocus = false
    end
end)

ToggleNoclip(false) -- Noclip
