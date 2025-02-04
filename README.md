local ReplicatedStorage = game:GetService("ReplicatedStorage")

-- Criando o evento para enviar o som
local SoundEvent = Instance.new("RemoteEvent")
SoundEvent.Name = "SoundEvent"
SoundEvent.Parent = ReplicatedStorage

-- Função para tocar o som para todos
SoundEvent.OnServerEvent:Connect(function(player, soundId)
    -- Cria um som em todos os jogadores do servidor
    local sound = Instance.new("Sound")
    sound.SoundId = soundId
    sound.Parent = game.Workspace
    sound:Play()
end)
