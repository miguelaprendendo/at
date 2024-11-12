-- Configurações da lib
NPCFarm.targetNPCs = {"Titan", "Abnormal"}
NPCFarm.attackDistance = 5

-- Função para encontrar NPCs
function NPCFarm.findNPCs()
    local npcs = {}
    for _, npc in pairs(game.Workspace:GetChildren()) do
        if table.find(NPCFarm.targetNPCs, npc.Name) and npc:FindFirstChild("HumanoidRootPart") then
            table.insert(npcs, npc)
        end
    end
    return npcs
end
-- Função para atacar NPC
function NPCFarm.attackNPC(npc)
    if npc then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = npc.HumanoidRootPart.CFrame * CFrame.new(0, 0, -NPCFarm.attackDistance)
        game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool"):Activate()
    end
end

-- Função para atacar todos os NPCs
function NPCFarm.attackAllNPCs()
    local npcs = NPCFarm.findNPCs()
    for _, npc in pairs(npcs) do
        NPCFarm.attackNPC(npc)
    end
end
return NPCFarm
