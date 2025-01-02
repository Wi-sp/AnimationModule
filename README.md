-- This code can play client sided animations from any Roblox game there is. It is fully Open Sourced you are allowed to improve it if you'd like. (This is mainly used for executors)

-- How to use example... (Copy the RAW file of this or it will get messed up)

local Player = game.Players.LocalPlayer -- Get the local player
local Character = Player.Character or Player.CharacterAdded:Wait() -- Wait for the character to load if not already available

-- Preload the animation handler module
local AnimHandlerSource = game:HttpGet("https://raw.githubusercontent.com/Wi-sp/AnimationModule/refs/heads/main/Main")
local AnimHandler = loadstring(AnimHandlerSource)()

-- Load the animation asset using its asset ID
local Walk = game:GetObjects("rbxassetid://99536403684167")[1] -- Change the ID here to whatever you want.

-- Create a new animation instance using the animation handler
-- The first argument is the character, and the second is the animation object
local WalkAnim = AnimHandler.new(Character, Walk)

-- Adjust the weight and priority of the animation before playing
WalkAnim:AdjustWeight(1, 0.15) -- Set weight to 1 for full influence; the second argument is the fade time
WalkAnim.Priority = Enum.AnimationPriority.Action -- Set the animation priority to Action

-- Play the animation
WalkAnim:Play() -- Start playing the animation

-- Additional methods you can use with the animation instance:

-- Adjust the speed of the animation
-- WalkAnim:AdjustSpeed(1.5) -- Set the speed to 1.5 times the normal speed (You can change the speed)

-- Stop the animation with a fade-out effect
-- WalkAnim:Stop() -- Stop the animation

-- Cancel the animation and reset its state
-- local savedPosition = WalkAnim:Cancel() -- Cancel the animation and return the last position

-- Destroy the animation instance when it's no longer needed
-- WalkAnim:Destroy() -- Clean up the animation instance to free resources
