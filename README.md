local notification = Instance.new("Hint")
notification.Text = "Script by Deadlyquest666"
notification.Parent = game.StarterGui
 
local player = game.Players.LocalPlayer
 
local infiniteJumpPower = 100
local defaultJumpPower = 50
 
local gui = Instance.new("ScreenGui")
gui.Name = "InfiniteJumpGUI"
gui.Parent = player.PlayerGui
 
local mainFrame = Instance.new("Frame")
mainFrame.Name = "MainFrame"
mainFrame.Size = UDim2.new(0, 200, 0, 50)
mainFrame.Position = UDim2.new(1, -220, 1, -60) -- Position at the bottom-right corner
mainFrame.BackgroundTransparency = 0.3
mainFrame.BackgroundColor3 = Color3.new(0.2, 0.8, 0.8) -- Teal background color
mainFrame.BorderSizePixel = 0
mainFrame.Parent = gui
 
 
local turnOnButton = Instance.new("TextButton")
turnOnButton.Name = "TurnOnButton"
turnOnButton.Text = "Infinite Jump"
turnOnButton.Size = UDim2.new(0, 200, 0, 50)
turnOnButton.Position = UDim2.new(0, 0, 0, 0)
turnOnButton.BackgroundTransparency = 0.3
turnOnButton.BackgroundColor3 = Color3.new(0.4, 0.9, 0.4) -- Light green background color
turnOnButton.Parent = mainFrame
 
local minimizeButton = Instance.new("TextButton")
minimizeButton.Name = "MinimizeButton"
minimizeButton.Text = "_"
minimizeButton.Size = UDim2.new(0, 30, 0, 30)
minimizeButton.Position = UDim2.new(1, -35, 0, 5) -- Position at the top-right corner
minimizeButton.BackgroundTransparency = 0.3
minimizeButton.BackgroundColor3 = Color3.new(0.8, 0.2, 0.2) -- Red background color
minimizeButton.TextColor3 = Color3.new(1, 1, 1)
minimizeButton.Parent = mainFrame
 
local function handleJump()
    
    if player.Character and player.Character:FindFirstChildOfClass("Humanoid") then
        local humanoid = player.Character:FindFirstChildOfClass("Humanoid")
        
 
        humanoid.JumpPower = infiniteJumpPower
        
        humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
    end
end
 
local function turnOnInfiniteJump()
    handleJump()
    turnOnButton.Visible = true
end
 
local function minimizeGUI()
    mainFrame.Visible = false
    minimizeButton.Visible = false
end
 
turnOnButton.MouseButton1Click:Connect(turnOnInfiniteJump)
minimizeButton.MouseButton1Click:Connect(minimizeGUI)
 
local UserInputService = game:GetService("UserInputService")
UserInputService.InputBegan:Connect(function(input, isProcessed)
    if not isProcessed and input.KeyCode == Enum.KeyCode.Space then
        turnOnInfiniteJump()
    end
end)
 game:GetService("StarterGui"):SetCore("SendNotification", { 
        Title = "Script By";
        Text  = "Deadlyquest666";
        Icon  = "rbxthumb://type=Asset&id=5107182114&w=150&h=150"})
    Duration = 16;
