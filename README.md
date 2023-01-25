_G.autorebirth = false
 
function a()
   wait(0.5)
   for _,v in pairs(workspace:GetDescendants()) do
       if v:IsA("TouchTransmitter") then
           if game.Players.LocalPlayer.Character:FindFirstChild("Head") and v then
               firetouchinterest(game.Players.LocalPlayer.Character.Head, v.Parent, 0)
               firetouchinterest(game.Players.LocalPlayer.Character.Head, v.Parent, 1)
           else
               a()
               break;
           end
       end
   end
   if autorebirth then
       game:GetService("ReplicatedStorage").RebirthRequest:InvokeServer()
   end
   a()
end
a()
