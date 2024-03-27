local range = 20 -- Adjust the range as needed

while true do
    wait(0.1) -- Adjust the wait time for performance

    local character = game.Players.LocalPlayer.Character
    if character then
        local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
        if humanoidRootPart then
            for _, player in ipairs(game.Players:GetPlayers()) do
                if player ~= game.Players.LocalPlayer and player.Character then
                    local playerCharacter = player.Character
                    local root = playerCharacter:FindFirstChild("HumanoidRootPart")
                    if root then
                        local distance = (humanoidRootPart.Position - root.Position).magnitude
                        if distance <= range then
                            local humanoid = playerCharacter:FindFirstChildOfClass("Humanoid")
                            if humanoid then
                                humanoid.Health = 0
                            end
                        end
                    end
                end
            end
        end
    end
end
