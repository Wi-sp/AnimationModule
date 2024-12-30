-- How to use example...

local Player = game.Players.LocalPlayer
local Character = Player.Character or Player.CharacterAdded:Wait()
local AnimHandler = loadstring(game:HttpGet("https://raw.githubusercontent.com/ProudNamed/SuperLightning/refs/heads/main/AnimModule/MainModule"))()

-- Load and prepare the walk animation
local Walk = game:GetObjects("rbxassetid://128808444469386")[1] --Change the id here to whatever
Walk.Parent = Character
game:GetService("ContentProvider"):PreloadAsync({Walk})

-- Create and play the walk animation
local WalkAnim = AnimHandler.new(Character, Walk)
WalkAnim:Play()

