
-- SUPER VIP MENU
local Players = game:GetService("Players")
local player = Players.LocalPlayer

local gui = Instance.new("ScreenGui")
gui.Name = "SuperVIP"
gui.ResetOnSpawn = false
gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 280, 0, 180)
frame.Position = UDim2.new(0.5, -140, 0.4, 0)
frame.BackgroundColor3 = Color3.fromRGB(25, 12, 45)
frame.BorderSizePixel = 0
frame.Parent = gui

local frameCorner = Instance.new("UICorner")
frameCorner.CornerRadius = UDim.new(0, 12)
frameCorner.Parent = frame

local stroke = Instance.new("UIStroke")
stroke.Color = Color3.fromRGB(120, 60, 180)
stroke.Thickness = 2
stroke.Parent = frame

local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 40)
title.BackgroundTransparency = 1
title.Text = "SUPER VIP MENU"
title.TextColor3 = Color3.fromRGB(220, 180, 255)
title.Font = Enum.Font.GothamBold
title.TextSize = 16
title.Parent = frame

local function addButton(name, text, y)
    local b = Instance.new("TextButton")
    b.Size = UDim2.new(0.85, 0, 0, 40)
    b.Position = UDim2.new(0.075, 0, 0, y)
    b.BackgroundColor3 = Color3.fromRGB(80, 40, 130)
    b.Text = text
    b.TextColor3 = Color3.new(1, 1, 1)
    b.Font = Enum.Font.GothamBold
    b.TextSize = 14
    b.Parent = frame

    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0, 8)
    corner.Parent = b

    b.Activated:Connect(function()
        print("[" .. name .. "] được nhấn!")
    end)

    b.MouseEnter:Connect(function()
        b.BackgroundColor3 = Color3.fromRGB(110, 60, 170)
    end)

    b.MouseLeave:Connect(function()
        b.BackgroundColor3 = Color3.fromRGB(80, 40, 130)
    end)
end

addButton("Egg", "NHẶT TRỨNG", 50)
addButton("Event", "SỰ KIỆN", 110)

gui.Parent = player:WaitForChild("PlayerGui")
