--[[ 
  ______    _ _            _____           _                          
 |  ____|  | | |          |  __ \         | |                         
 | |__ __ _| | | ___ _ __ | |__) |__ _ __ | |_ __ _  __ _  ___  _ __  
 |  __/ _` | | |/ _ \ '_ \|  ___/ _ \ '_ \| __/ _` |/ _` |/ _ \| '_ \ 
 | | | (_| | | |  __/ | | | |  |  __/ | | | || (_| | (_| | (_) | | | |
 |_|  \__,_|_|_|\___|_| |_|_|   \___|_| |_|\__\__,_|\__, |\___/|_| |_|
                                                     __/ |            
                                                    |___/             
-- Yi who must not be named BETA
]]

local scriptVersion = 0.41
local autoUpdate	= true
local loadOrbWalker = true

assert(load(Base64Decode("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"), nil, "bt", _ENV))()
TrackerLoad("C5nwrpDS6qN2KMv5")

if myHero.charName ~= "MasterYi" then return end

local Q, W, E, R  = {}, {}, {}, {}
local slot = {"Q", "W", "E", "R"}
local IsReady = function(spell) return myHero:CanUseSpell(spell) == READY end
local myTrueRange = myHero.range + GetDistance(myHero.minBBox)
local reset = false

function OnLoad()	
	Show("loading...")
	Update()
	if GetInGameTimer() < 5 then DelayAction(function() myTrueRange = myHero.range + GetDistance(myHero.minBBox) end, 5 - GetInGameTimer()) end	
	MasterYi()
	LoadMenu()
	if loadOrbWalker then LoadOrbWalker() end
end

function OnTick()
	Target()
	if Config.Keys.Flee then
		MasterYi:Flee()
	elseif target and Config.Keys.Combo then
		MasterYi:Combo()
	elseif target and Config.Keys.Harass then
		MasterYi:Harass()
	end	
end

function OnDraw()
	if myHero.dead then return end
	if Config.Draw.MyRange then
		DrawCircle3D(myHero.x, myHero.y, myHero.z, myTrueRange, 1, 0xff00ff00)
	end
	if Config.Draw.Target and target then
		DrawCircle3D(target.x, target.y, target.z, target.range + GetDistance(target, target.minBBox), 1, 0xffff0000)
	end
end

function LoadMenu() 
	Config = scriptConfig("FallenYi", "FallenYi")
	Config:addSubMenu("Key Settings", "Keys")
	Config:addSubMenu("AutoKill", "AutoKill")	
	Config:addSubMenu("Combo", "Combo")	
	Config.Keys:addParam("Combo", "Combo", SCRIPT_PARAM_ONKEYDOWN, false, 32)
	Config:addSubMenu("Harass", "Harass")
	Config.Keys:addParam("Harass", "Harass", SCRIPT_PARAM_ONKEYDOWN, false, 67)
	Config:addSubMenu("Evade", "Evade")
	Config:addSubMenu("Flee", "Flee")	
	Config.Keys:addParam("Flee", "Flee", SCRIPT_PARAM_ONKEYDOWN, false, 71)
	Config:addSubMenu("Follow", "Follow")
	Config.Follow:addSubMenu("Blinks", "Blinks")
	Config.Follow.Blinks:addParam("Flash", "flash", SCRIPT_PARAM_ONOFF, true)	
	Config:addSubMenu("Draw", "Draw")
	if loadOrbWalker then Config:addSubMenu("OrbWalker", "OrbWalker") end
	Config.Draw:addParam("MyRange", "my range", SCRIPT_PARAM_ONOFF, false)				
	Config.Draw:addParam("Target", "target range", SCRIPT_PARAM_ONOFF, true)
	Config:addSubMenu("Misc", "Misc")
	Config:addParam("version","____________________________________________", 5, " v "..scriptVersion)
	Config:addParam("author","by FallenPentagon", 5, "")
	MasterYi:Menu()
	AddDrawCallback(function() MasterYi:Draw() end)
	AddTickCallback(function() MasterYi:AutoKill() end)
	AddProcessAttackCallback(function(unit, spell) MasterYi:ProcessAttack(unit, spell) end)
	AddProcessSpellCallback(function(unit, spell) MasterYi:ProcessSpell(unit, spell) end)
	AddRemoveBuffCallback(function(unit, buff) MasterYi:RemoveBuff(unit, buff) end)
	AddApplyBuffCallback(function(source, unit, buff) MasterYi:ApplyBuff(source, unit, buff) end)
	AddNewPathCallback(function(unit, startPos, endPos, isDash, dashSpeed) MasterYi:Follow(unit, startPos, endPos, isDash, dashSpeed) end)
end

function LoadOrbWalker()  
	if not _G.UOLloaded then     
		if FileExist(LIB_PATH.."UOL.lua") then
			require "UOL" 
			UOL:AddToMenu(Config.OrbWalker)
			isUOL = true
   		else
    		Show("Couldnt find UOL.lua, downloading now...")
    		DownloadFile("https://raw.githubusercontent.com/nebelwolfi/BoL/master/Common/UOL.lua", LIB_PATH.."UOL.lua", function() Show("Downloaded UOL.lua successfully, press F9 twice to reload") end)
    		return
    	end
    end
end

function Update()
	local source = "www.FallenPentagon.com"
	local path = "/BolScripts/FallenYi.version"
	local url = "http://"..source.."/BolScripts/FallenYi.lua"
	if tonumber(GetWebResult(source, path)) > scriptVersion and autoUpdate then
		Show("Newer version found, don't press F9 while its Downloading...")
		DownloadFile(url, SCRIPT_PATH..GetCurrentEnv().FILE_NAME, function() Show("Downloaded successfully, press F9 twice to reload") end)
	else
		Show("Successfully loaded v"..scriptVersion)
	end
end

function Target()
	ts:update()
   	if isUOL and UOL:GetTarget() and UOL:GetTarget().type == myHero.type then
    	target = UOL:GetTarget()
    else
    	target = ts.target
    end
    if target and isUOL then UOL:ForceTarget(target) end
end

function AddTS(range, type)
	ts = TargetSelector(TARGET_LESS_CAST_PRIORITY, range, type, false)
	ts.name = "Target Selector"
	Config.Misc:addTS(ts)
end

function Show(text)
	print("<font color = \"#6F3A9C\">[FallenYi]<font color = \"#ffff33\"> "..text)
end

function GetUnitName(unit)
	if unit.charName == "MonkeyKing" then
		return "Wukong"
	end
	return unit.charName
end

function LoadTable()
	tSpellData = {
   		["Alistar"] = {true, spell = {{name = "Headbutt", slot = 1}}},
    	["Anivia"] = {true, spell = {{name = "Frostbite", slot = 2, block = 60}}},
    	["Annie"] = {true, spell = {{name = "Disintegrate", slot = 0, block = 40}}},
    	["Akali"] = {true, spell = {{name = "Mark of the Assassin", slot = 0, dodge = 70, block = 10}, 
    		{name = "Shadow Dance", slot = 3, dodge = 70, block = 30}}},
    	["Brand"] = {true, spell = {{name = "Conflagration", slot = 2, dodge = 50, block = 20}, 
    		{name = "Pyroclasm", slot = 3, delayd = 0.2, block = 80}}}, 
    	["Caitlyn"] = {true, spell = {{name = "Ace in the Hole", slot = 3, block = 80, delayd = 1.2, delayb = 0.2}}},  
    	["Cassiopeia"] = {true, spell = {{name = "Twin Fang", slot = 2, dodge = 50, block = 20}}},  
    	["ChoGath"] = {true, spell = {{name = "Feast", slot = 3}}}, 
    	["Darius"] = {true, spell = {{name = "Noxian Guillotine", slot = 3}}}, 
    	["Diana"] = {true, spell = {{name = "Lunar Rush", slot = 3, block = 60}}}, 
    	["Evelynn"] = {true, spell = {{name = "Ravage", slot = 2, dodge = 70, block = 30}}},
    	["Fiddlesticks"] = {true, spell = {{name = "Dark Wind", slot = 2, block = 20}}},
    	["Fizz"] = {true, spell = {{name = "Urchin Strike", slot = 0, block = 20}}},
    	["Gangplank"] = {true, spell = {{name = "Parrrley", slot = 0, dodge = 80, block = 60}}},
    	["Garen"] = {true, spell = {{name = "Demacian Justice", slot = 3, dodge = 40, block = 60, pref = 2}}},
    	["Irelia"] = {true, spell = {{name = "Bladesurge", slot = 0, dodge = 40}, 
    		{name = "Equilibrium Strike", slot = 2}}},
    	["Janna"] = {true, spell = {{name = "Zephyr", slot = 1}}},
    	["JarvanIV"] = {true, spell = {{name = "Cataclysm", slot = 3, block = 60}}},
    	["Jax"] = {true, spell = {{name = "Leap Strike", slot = 0, dodge = 50, block = 50}}},
    	["Kayle"] = {true, spell = {{name = "Reckoning", slot = 0, block = 60}}},
    	["Kassadin"] = {true, spell = {{name = "Null Sphere", slot = 0, block = 50}}},
    	["Katarina"] = {true, spell = {{name = "Bouncing Blades", slot = 0, block = 50}}},
    	["KhaZix"] = {true, spell = {{name = "Taste Their Fear", slot = 0, block = 101}}},
    	["LeBlanc"] = {true, spell = {{name = "Sigil of Malice", slot = 0, block = 60}}},
    	["LeeSin"] = {true, spell = {{name = "Dragon's Rage", slot = 3, block = 60}}},
    	["Lissandra"] = {true, spell = {{name = "Frozen Tomb", slot = 3, block = 40, delayd = 0.32}}},
    	["Lucian"] = {true, spell = {{name = "Piercing Light", slot = 0, block = 30}}},
    	["Lulu"] = {true, spell = {{name = "Whimsy", slot = 1}}},
    	["Malphite"] = {true, spell = {{name = "Seismic Shard", slot = 0, block = 20}}},
    	["Maokai"] = {true, spell = {{name = "Twisted Advance", slot = 1}}},
    	["MasterYi"] = {true, spell = {{name = "Alpha Strike", slot = 0, dodge = 50, block = 50}}},
    	["MissFortune"] = {true, spell = {{name = "Double Up", slot = 0, block = 40}}},
    	["Nami"] = {true, spell = {{name = "Ebb and Flow", slot = 1, block = 30}}},
    	["Nautilus"] = {true, spell = {{name = "Depth Charge", slot = 3}}},
    	["Nocturne"] = {true, spell = {{name = "Unspeakable Horror", slot = 2}}},
    	["Nunu"] = {true, spell = {{name = "Ice Blast", slot = 2, block = 10}}},
    	["Olaf"] = {true, spell = {{name = "Reckless Swing", slot = 2}}},
    	["Pantheon"] = {true, spell = {{name = "Spear Shot", slot = 0, block = 40}, 
    		{name = "Aegis of Zeonia", slot = 1}}},
    	["Poppy"] = {true, spell = {{name = "Heroic Charge", slot = 2}}},
    	["Quinn"] = {true, spell = {{name = "Vault", slot = 2, dodge = 40, block = 20}}},
    	["RekSai"] = {true, spell = {{name = "Furious Bite", slot = 2, dodge = 40, block = 10}}},
    	["Rammus"] = {true, spell = {{name = "Puncturing Taunt", slot = 2}}},
    	["Ryze"] = {true, spell = {{name = "Rune Prison", slot = 1, dodge = 0}, 
    		{name = "Spell Flux", slot = 2, dodge = 0}}},
    	["Shaco"] = {true, spell = {{name = "Two-Shiv Poison", slot = 2, block = 40}}},
    	["Singed"] = {true, spell = {{name = "Fling", slot = 2}}},
    	["Syndra"] = {true, spell = {{name = "Unleashed Power", slot = 3, block = 80}}},
    	["Tahmkench"] = {true, spell = {{name = "Devour", slot = 1}}},
    	["Taric"] = {true, spell = {{name = "Dazzle", slot = 2}}},
    	["Teemo"] = {true, spell = {{name = "Blinding Dart", slot = 0, block = 50}}},
    	["Tristana"] = {true, spell = {{name = "Buster Shot", slot = 3, block = 30}}},
    	["Trundle"] = {true, spell = {{name = "Subjugate", slot = 3, dodge = 40, block = 10}}},
    	["Vayne"] = {true, spell = {{name = "Condemn", slot = 2}}},
    	["Veigar"] = {true, spell = {{name = "Primordial Burst", slot = 3, block = 80}}},
    	["Vi"] = {true, spell = {{name = "Assault and Battery", slot = 3}}},
    	["Viktor"] = {true, spell = {{name = "Siphon Power", slot = 0, dodge = 40, block = 40}}},
    	["Vladimir"] = {true, spell = {{name = "Transfusion", slot = 0, block = 50}}},
   		["Volibear"] = {true, spell = {{name = "Frenzy", slot = 1, dodge = 70, block = 50}}},
    	["Warwick"] = {true, spell = {{name = "Hungering Strike", slot = 0}}},
    	["Wukong"] = {true, spell = {{name = "Nimbus Strike", slot = 2, dodge = 80, block = 40}}},
    	["XinZhao"] = {true, spell = {{name = "Audacious Charge", slot = 2, dodge = 70, block = 30}}},
    	["Yasuo"] = {true, spell = {{name = "Sweeping Blade", slot = 2, dodge = 40, block = 40}}},
    	["Zed"] = {true, spell = {{name = "Death Mark", slot = 3, block = 70, delayb = 3.7}}},   
    	["Zilean"] = {true, spell = {{name = "Time Warp", slot = 2}}}, 
	} 	
	blinks = {
		["Ezreal"] = {true, spell = {{name = "Arcane Shift", slot = 2}}},
		["Katarina"] = {true, spell = {{name = "Shunpo", slot = 2}}},
		["Kassadin"] = {true, spell = {{name = "Riftwalk", slot = 0}}},
		["LeBlanc"] = {true, spell = {{name = "Distortion", slot = -1},
			{name = "Mimic: Distortion", slot = -3}}},
		["Lissandra"] = {true, spell = {{name = "Glacial Path", slot = 2}}},
		["Talon"] = {true, spell = {{name = "Cutthroat", slot = 2}}},
		["Yasuo"] = {true, spell = {{name = "Last Breath", slot = 3}}},
		["Zed"] = {true, spell = {{name = "Living Shadow", slot = -1},
			{name = "Death Mark", slot = -3}}},
	}
end

class "MasterYi"
function MasterYi:__init()
	LoadTable()
	Q.cost = function() return myHero:GetSpellData(0).level * 10 + 60 end
	Q.damage = function() return myHero:GetSpellData(0).level * 35 + myHero.totalDamage - 10 end
	Q.range = 600
	Q.travelTime = 1.1
	W.cost = 50
	E.active = false
	E.damage = function() return myHero:GetSpellData(2).level * (5 + 0.025 * myHero.totalDamage) + 5 + 0.1 * myHero.totalDamage end
	R.cost = 100	
end

function MasterYi:AutoKill()
	local eDmg = ((IsReady(2) or E.active) and Config.AutoKill.E) and E.damage() or 0
	for _, enemy in pairs(GetEnemyHeroes()) do
		if ValidTarget(enemy, myTrueRange) then
			if enemy.health <= myHero.totalDamage + eDmg then
				if Config.AutoKill.E then CastSpell(2) end
				UOL:ForceTarget(enemy)
			elseif enemy.health <= 2 * (myHero.totalDamage + eDmg) and IsReady(1) and Config.AutoKill.W then
				if Config.AutoKill.E then CastSpell(2) end
				self:Reset()
				UOL:ForceTarget(enemy)
			end
		elseif ValidTarget(enemy, Q.range) and IsReady(0) and Config.AutoKill.Q then
			if enemy.health <= myHero.totalDamage + eDmg + Q.damage() then
				if Config.AutoKill.E then CastSpell(2) end
				CastSpell(0, enemy)
				UOL:ForceTarget(enemy)
			elseif enemy.health <= 2 * (myHero.totalDamage + eDmg) and IsReady(1) and Config.AutoKill.W and myHero.mana <= Q.cost() + W.cost then
				if Config.AutoKill.E then CastSpell(2) end
				self:Reset()
				CastSpell(0, enemy)
				UOL:ForceTarget(enemy)
			end
		end
	end     
end

function MasterYi:Block(spell)
	if IsReady(1) then
		CastSpell(1)
	elseif Config.Evade[spell.name].QDelay > Config.Evade[spell.name].WDelay then
		DelayAction(function() self:Dodge(spell) end, Config.Evade[spell.name].QDelay - Config.Evade[spell.name].WDelay)
	end
end

function MasterYi:Combo()
	local eDmg = ((IsReady(2) or E.active) and Config.Combo.E) and E.damage() or 0
	if ValidTarget(target, myTrueRange) then
		if Config.Combo.E and IsReady(2) then 
			CastSpell(2) 
		end
		if myHero.health / myHero.maxHealth * 100 <= Config.Combo.HpW then 
			self:Reset()
		end
	elseif ValidTarget(target, Q.range) and IsReady(0) and ((myHero.ms < target.ms + 65 and Config.Combo.QG) or (target.health <= myHero:CalcDamage(target, Q.damage() + Config.Combo.Q * (myHero.totalDamage + eDmg))) or myHero.health / myHero.maxHealth * 100 <= Config.Combo.HpQ) then
		CastSpell(0, target)
	end
end

function MasterYi:Dodge(spell)
	if IsReady(0) then
		local laneMinions = minionManager(MINION_ENEMY, Q.range, myHero, function(a,b) return GetDistance(a) < GetDistance(b) end)
		local jungleMinions = minionManager(MINION_JUNGLE, Q.range, myHero, function(a,b) return GetDistance(a) < GetDistance(b) end)
		laneMinions:update()
		jungleMinions:update()
		local unit = nil
		if Config.Keys.Flee then
			local laneMinions = minionManager(MINION_ENEMY, Q.range, myHero, function(a,b) return GetDistance(a) > GetDistance(b) end)
			local jungleMinions = minionManager(MINION_JUNGLE, Q.range, myHero, function(a,b) return GetDistance(a) > GetDistance(b) end)
			local distance = 4000			
			for _, minion in pairs(laneMinions.objects) do
				if ValidTarget(minion) and GetDistance(minion, mousePos) < distance and GetDistance(minion, mousePos) < GetDistance(mousePos) - 200 then
					unit = minion
					distance = GetDistance(minion, mousePos)
				end
			end			
			for _, minion in pairs(jungleMinions.objects) do
				if ValidTarget(minion) and GetDistance(minion, mousePos) < distance and GetDistance(minion, mousePos) < GetDistance(mousePos) - 200 then
					unit = minion
					distance = GetDistance(minion, mousePos)
				end
			end		
			for _, enemy in pairs(GetEnemyHeroes()) do
				if ValidTarget(enemy) and GetDistance(enemy, mousePos) < distance and GetDistance(enemy, mousePos) < GetDistance(mousePos) - 200 then
					unit = enemy
					distance = GetDistance(enemy, mousePos)
				end
			end	
		end
		if Config.Keys.Combo and ValidTarget(target) then
			if GetDistance(target) <= Q.range then
				unit = target
			else 
				local distance = GetDistance(target)				
				for _, minion in pairs(laneMinions.objects) do
					if ValidTarget(minion) and GetDistance(minion, target) < distance and GetDistance(minion) > myTrueRange then
						unit = minion
						distance = GetDistance(minion, target)
					end
				end			
				for _, minion in pairs(jungleMinions.objects) do
					if ValidTarget(minion) and GetDistance(minion, target) < distance and GetDistance(minion) > myTrueRange then
						unit = minion
						distance = GetDistance(minion, target)
					end
				end		
				for _, enemy in pairs(GetEnemyHeroes()) do
					if ValidTarget(enemy) and GetDistance(enemy, target) < distance and GetDistance(enemy) > myTrueRange then
						unit = enemy
						distance = GetDistance(enemy, target)
					end
				end	
			end
		end
		if not unit then	
			local distance = Q.range			
			for _, minion in pairs(laneMinions.objects) do
				if ValidTarget(minion) and GetDistance(minion) < distance then
					unit = minion
					distance = GetDistance(minion)
				end
			end			
			for _, minion in pairs(jungleMinions.objects) do
				if ValidTarget(minion) and GetDistance(minion) < distance then
					unit = minion
					distance = GetDistance(minion)
				end
			end	
			for _, enemy in pairs(GetEnemyHeroes()) do
				if ValidTarget(enemy) and GetDistance(enemy) < distance then
					unit = enemy
					distance = GetDistance(enemy)
				end
			end				
		end
		if unit then 
			CastSpell(0, unit)
		elseif Config.Evade[spell.name].WDelay > Config.Evade[spell.name].QDelay then
			DelayAction(function() self:Block(spell) end, Config.Evade[spell.name].WDelay - Config.Evade[spell.name].QDelay)
		end
	elseif Config.Evade[spell.name].WDelay > Config.Evade[spell.name].QDelay then
		DelayAction(function() self:Block(spell) end, Config.Evade[spell.name].WDelay - Config.Evade[spell.name].QDelay)
	end
end

function MasterYi:Draw()
	if myHero.dead then return end
	if Config.Draw.QRange and IsReady(0) then
		DrawCircle3D(myHero.x, myHero.y, myHero.z, Q.range, 1, 0xff00ff00)
	end
end

function MasterYi:Evade(spell)
	if Config.Evade[spell.name].Prefer == 1 then
		if (IsReady(0) or myHero:GetSpellData(0).currentCd < Config.Evade[spell.name].QDelay) and myHero.health / myHero.maxHealth * 100 <= Config.Evade[spell.name].HpQ then
				DelayAction(function() self:Dodge(spell) end, Config.Evade[spell.name].QDelay)
		elseif (IsReady(1) or myHero:GetSpellData(1).currentCd < Config.Evade[spell.name].WDelay) and myHero.health / myHero.maxHealth * 100 <= Config.Evade[spell.name].HpW then
				DelayAction(function() self:Block(spell) end, Config.Evade[spell.name].WDelay)
		end
	else
		if (IsReady(1) or myHero:GetSpellData(1).currentCd < Config.Evade[spell.name].WDelay) and myHero.health / myHero.maxHealth * 100 <= Config.Evade[spell.name].HpW then
			DelayAction(function() self:Block(spell) end, Config.Evade[spell.name].WDelay)
		elseif (IsReady(0) or myHero:GetSpellData(0).currentCd < Config.Evade[spell.name].QDelay) and myHero.health / myHero.maxHealth * 100 <= Config.Evade[spell.name].HpQ then
			DelayAction(function() self:Dodge(spell) end, Config.Evade[spell.name].QDelay)
		end
	end
end

function MasterYi:Flee()
	myHero:MoveTo(mousePos.x, mousePos.z)
	if Config.Flee.UseQ and IsReady(0) then
		local laneMinions = minionManager(MINION_ENEMY, Q.range, myHero, function(a,b) return GetDistance(a) > GetDistance(b) end)
		local jungleMinions = minionManager(MINION_JUNGLE, Q.range, myHero, function(a,b) return GetDistance(a) > GetDistance(b) end)
		laneMinions:update()
		jungleMinions:update()
		local distance = 4000
		local unit = nil		
		for _, enemy in pairs(GetEnemyHeroes()) do
			if ValidTarget(enemy, Q.range) and GetDistance(enemy, mousePos) < distance and GetDistance(enemy, mousePos) < GetDistance(enemy, mousePos) - 200 then
				unit = enemy
				distance = GetDistance(enemy, mousePos)
			end
		end		
		for _, minion in pairs(jungleMinions.objects) do
			if ValidTarget(minion, Q.range) and GetDistance(minion, mousePos) < distance and GetDistance(minion, mousePos) < GetDistance(mousePos) - 200 then
				unit = minion
				distance = GetDistance(minion, mousePos)
			end
		end
		for _, minion in pairs(laneMinions.objects) do
			if ValidTarget(minion, Q.range) and GetDistance(minion, mousePos) < distance and GetDistance(minion, mousePos) < GetDistance(mousePos) - 200 then
				unit = minion
				distance = GetDistance(minion, mousePos)
			end
		end
		if unit then
			CastSpell(0, unit)
		end
	end
end

function MasterYi:ApplyBuff(source, unit, buff)
	if unit and unit.isMe then
		if buff.name:find("supercharged") then 
        	E.active = true
    	end
	end
end

function MasterYi:RemoveBuff(unit, buff)
	if unit and unit.isMe and buff.name:find("supercharged") then
      	E.active = false
   	end
end

function MasterYi:Harass()
	if ValidTarget(target, myTrueRange) and Config.Harras.E and IsReady(1) then
		CastSpell(1)
	elseif ValidTarget(target, Q.range) and Config.Harras.Q and IsReady(0) then
		CastSpell(0, target)
	end
end 

function MasterYi:Menu()
	AddTS(1200, DAMAGE_PHYSICAL)
	Config.AutoKill:addParam("Q", "use Q", SCRIPT_PARAM_ONOFF, true)
	Config.AutoKill:addParam("W", "use W as reset", SCRIPT_PARAM_ONOFF, true)	
	Config.AutoKill:addParam("E", "use E", SCRIPT_PARAM_ONOFF, true)
	Config.Combo:addParam("Q", "Q when x AA's can kill", SCRIPT_PARAM_SLICE, 3, 1, 5, 0)
	--Config.Combo:addParam("QX", "Q when can hit", SCRIPT_PARAM_SLICE, 4, 0, 4, 0)
	Config.Combo:addParam("QG", "Q as gapcloser", SCRIPT_PARAM_ONOFF, true)	
	Config.Combo:addParam("HpQ", "Q when HP(%)", SCRIPT_PARAM_SLICE, 20, 0, 100, 0)
	Config.Combo:addParam("HpW", "W as reset when HP(%)",  SCRIPT_PARAM_SLICE, 30, 0, 100, 0)
	Config.Combo:addParam("E", "use E", SCRIPT_PARAM_ONOFF, true)	
	Config.Combo:addParam("R", "R on slow", SCRIPT_PARAM_ONOFF, true)	
	Config.Harass:addParam("Q", "use Q", SCRIPT_PARAM_ONOFF, true)	
	Config.Harass:addParam("E", "use E", SCRIPT_PARAM_ONOFF, false)
	Config.Draw:addParam("QRange", "Q range", SCRIPT_PARAM_ONOFF, true)	
	Config.Flee:addParam("UseQ", "use Q", SCRIPT_PARAM_ONOFF, false)	
	local spells = false
	for _, enemy in pairs(GetEnemyHeroes()) do
		Config.Follow:addParam(GetUnitName(enemy), GetUnitName(enemy), SCRIPT_PARAM_ONOFF, true)
        if tSpellData[GetUnitName(enemy)] then
            for i = 1, #tSpellData[GetUnitName(enemy)].spell do
            	spells = true
            	local spellName = enemy:GetSpellData(tSpellData[GetUnitName(enemy)].spell[i].slot).name
                Config.Evade:addSubMenu(GetUnitName(enemy).." | "..slot[tSpellData[GetUnitName(enemy)].spell[i].slot + 1].." | "..tSpellData[GetUnitName(enemy)].spell[i].name, spellName)      
                Config.Evade[spellName]:addParam("HpQ", "Q when HP(%) lower then", SCRIPT_PARAM_SLICE, (tSpellData[GetUnitName(enemy)].spell[i].dodge or 100), 0, 100, 0)
                Config.Evade[spellName]:addParam("HpW", "W when HP(%) lower then", SCRIPT_PARAM_SLICE, (tSpellData[GetUnitName(enemy)].spell[i].block or 0), 0, 100, 0)
                Config.Evade[spellName]:addParam("Prefer", "prefer", SCRIPT_PARAM_LIST, (tSpellData[GetUnitName(enemy)].spell[i].pref or 1), {"Q > W", "W > Q"})
                Config.Evade[spellName]:addParam("QDelay", "Q delay (default: "..(tSpellData[GetUnitName(enemy)].spell[i].delayd or 0)..")", SCRIPT_PARAM_SLICE, (tSpellData[GetUnitName(enemy)].spell[i].delayd or 0), 0, 5, 1)
            	Config.Evade[spellName]:addParam("WDelay", "W delay (default: "..(tSpellData[GetUnitName(enemy)].spell[i].delayb or 0)..")", SCRIPT_PARAM_SLICE, (tSpellData[GetUnitName(enemy)].spell[i].delayb or 0), 0, 5, 1)
            end
        end
        if blinks[GetUnitName(enemy)] then
        	for i = 1, #blinks[GetUnitName(enemy)].spell do
            	local spellName = enemy:GetSpellData(blinks[GetUnitName(enemy)].spell[i].slot).name
                Config.Follow.Blinks:addParam(spellName, GetUnitName(enemy).." | "..slot[blinks[GetUnitName(enemy)].spell[i].slot + 1].." | "..blinks[GetUnitName(enemy)].spell[i].name, SCRIPT_PARAM_ONOFF, true)	
        	end
        end
    end
    if not spells then
    	Config.Evade:addParam("info","no spells found", 5, "")
    end
end

function MasterYi:Follow(unit, startPos, endPos, isDash, dashSpeed)
	if Config.Follow[GetUnitName(unit)] and isDash and GetDistance(startPos) < GetDistance(endPos) and unit == target and Config.Keys.Combo and GetDistance(endPos) > myTrueRange then
		local dashTime = GetDistance(startPos, endPos) / dashSpeed
		if dashTime > Q.travelTime then
			DelayAction(function() if IsReady(0) and ValidTarget(target, Q.range) then CastSpell(0, target) end end, (dashTime - Q.travelTime))
		elseif IsReady(0) and ValidTarget(target, Q.range) then 
			CastSpell(0, target)
		end
	end
end

function MasterYi:ProcessAttack(unit, spell)
	if unit.isMe and reset then 
		if spell.name:find("Attack") and IsReady(1) and spell.target == target then
			CastSpell(1)
			UOL:ResetAA()
		elseif spell.name:find("Medi") and ValidTarget(target, myTrueRange) then
			myHero:Attack(target)
			reset = false
		end
	end
end

function MasterYi:ProcessSpell(unit, spell)
	if unit.team ~= myHero.team then
		if spell.target and spell.target.isMe and Config.Evade[spell.name] then
			self:Evade(spell)
		elseif (Config.Follow.Blinks[spell.name] or (Config.Follow[GetUnitName(unit)] and Config.Follow.Blinks.Flash)) and IsReady(0) and ValidTarget(unit, Q.range) and GetDistance(spell.endPos) > GetDistance(spell.startPos) and GetDistance(spell.endPos) > myTrueRange then
			CastSpell(0, unit)
		end
	end
end

function MasterYi:Reset()
	reset = true
	DelayAction(function() reset = false end, 1)
end
