local npcs
while task.wait() do
    npcs = workspace.NPCFolders.EnemyFolder
    for _, v in ipairs(npcs:GetChildren()) do
        if not v:FindFirstChild("Head") then continue end

  local head = v.Head
        local effectAttachment = head:FindFirstChild("EffectAttachment")
        if not effectAttachment then
            effectAttachment = Instance.new("Attachment")
            effectAttachment.Name = "EffectAttachment"
            effectAttachment.Parent = head
            
  local effect = Instance.new("Part")
   effect.Name = "HeadEffect"
            effect.Shape = Enum.PartType.Ball
            effect.Size = Vector3.new(40, 40, 40)
            effect.Material = Enum.Material.Neon
            effect.BrickColor = BrickColor.new("Really blue")
            effect.Transparency = 0.4
            effect.CanCollide = false
            effect.Anchored = false
            effect.Parent = head

   local weld = Instance.new("WeldConstraint")
            weld.Part0 = effect
  weld.Part1 = head
            weld.Parent = effect
        end
    end
end
