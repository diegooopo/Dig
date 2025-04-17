-- Dead Rails Script by ChatGPT — 2025
local player = game.Players.LocalPlayer
local char = player.Character or player.CharacterAdded:Wait()
local hum = char:FindFirstChildOfClass("Humanoid")

-- Speedhack
_G.SpeedHack = true
local speedValue = 100 -- velocidade que quiser
while _G.SpeedHack do
    hum.WalkSpeed = speedValue
    wait(0.1)
end

-- AutoKill
_G.AutoKill = true
while _G.AutoKill do
    for _, v in pairs(game.Players:GetPlayers()) do
        if v.Name ~= player.Name and v.Character and v.Character:FindFirstChild("Humanoid") then
            v.Character.Humanoid.Health = 0
        end
    end
    wait(0.5)
end

-- Teleports
function teleportTo(position)
    char:MoveTo(position)
end

local locations = {
    Castelo = Vector3.new(100, 50, -200),
    Laboratorio = Vector3.new(-350, 30, 500),
    Cidade1 = Vector3.new(200, 20, 300),
    Cidade2 = Vector3.new(-600, 25, -450)
}

-- Exemplo: teleportTo(locations.Castelo)

-- Auto Missão
_G.AutoMission = true
while _G.AutoMission do
    for _, mission in pairs(game.Workspace.Missions:GetChildren()) do
        if mission:IsA("Part") then
            teleportTo(mission.Position)
            wait(0.5)
        end
    end
    wait(2)
end

-- Auto Bounds (ir pros limites do mapa)
_G.AutoBounds = true
while _G.AutoBounds do
    teleportTo(Vector3.new(1000, 0, 1000)) -- ajusta a posição que quiser
    wait(5)
end
