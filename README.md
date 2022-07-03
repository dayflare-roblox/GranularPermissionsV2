### GranularPermissionsV2

	# Welcome to Granular Permissions Version 2!
	
	I recently released another permission manager called Granular Permissions. This module was built from the ground up
	in relation to the old module.
	
	This module is simple but effective, it uses roblox's core functions to validate player requests
	based on preset permission managers, then it returns whether they're allowed aswell
	as their permission number (hierarchy)!.
	
	I made this module to be as extensive and open source as possible, with easy understanding of how things work.
	I'd love to see your projects include this code or this code but forked to be even better!
	
	To use this module simply reference the below code for an example:
	
```
	local GranularPermissions = require(path.to.module)
	local Permissions = GranularPermissions.new()

	Permissions:Configure({
		Authorised = {
			{Group = 4602493, CheckType = ">=", Rank = 5},
			{Gamepass = 1453495345},
			3483457857,
			"dayflare"
		},
	})
	
	game.Players.PlayerAdded:Connect(function(Player: Player)
		local Hierarchy, isAllowed = Permissions:Check(Player)
		
		if isAllowed then
			print("Player is authorised with permission data ", Hierarchy, isAllowed)
		end
	end)
```
	
	Guide & Explanations:
	
	> "Hierarchy" is the index of which the permission slip was entered. (number)
	> "isAllowed" is a result to whether they are allowed or not. (boolean)
	> As in the example above, we support group ranks, gamepasses, userids and usernames!
	> This module is fully extensive and easy to use... that being said, enjoy!
