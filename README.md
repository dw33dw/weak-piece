local bosses = {workspace["[JOR]"],workspace["[MRMS]"],workspace["[Ace]"],workspace.Heaven}

 

task.spawn(function()

    while wait(1) do

        pcall(function()

            for _,v in pairs(bosses) do

                fireclickdetector(v.ClickDetector)

            end

            for i,v2 in pairs(game.Players:GetChildren()) do

                for _,v in pairs(v2.Backpack:GetChildren()) do

                    if v:FindFirstChild("DF") and v:FindFirstChild("Event") then

                        if v.Name == "Explosion" then

                            v.Event:FireServer("Explosive")

                        else

                            v.Event:FireServer(v.Name.."Punch")

                            v.Event:FireServer(v.Name)

                        end

                    end

                end

                if v2.Character then

                    for _,v in pairs(v2.Character:GetChildren()) do

                        if v:FindFirstChild("DF") and v:FindFirstChild("Event") then

                            if v.Name == "Explosion" then

                                v.Event:FireServer("Explosive")

                            else

                                v.Event:FireServer(v.Name.."Punch")

                                v.Event:FireServer(v.Name)

                            end

                        end

                    end

                end

            end

        end)

    end

end)

 

while wait(0.2) do

    for i,v2 in pairs(workspace.Enemy:GetChildren()) do

        for _,v in pairs(v2:GetChildren()) do

            if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then

                game:GetService("ReplicatedStorage").Remote.Skills:FireServer("MMExplosion", 9e18, v.HumanoidRootPart.CFrame)

                game:GetService("ReplicatedStorage").Remote.Skills:FireServer("MExplosion", 9e18, v.HumanoidRootPart.CFrame)

                game:GetService("ReplicatedStorage").Remote.Skills:FireServer("Explosion", 9e18, v.HumanoidRootPart.CFrame)

            end

        end

    end

end
