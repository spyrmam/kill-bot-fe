if game:GetService("RunService"):IsClient() then error("Script must be server-side in order to work; use h/ and not hl/") end local Player,game,owner = owner,game local RealPlayer = Player do print("this shit was made by spyrmam") local rp = RealPlayer script.Parent = rp.Character

--RemoteEvent for communicating
local Event = Instance.new("RemoteEvent")
Event.Name = "UserInput_Event"

--Fake event to make stuff like Mouse.KeyDown work
local function fakeEvent()
    local t = {_fakeEvent=true,Functions={},Connect=function(self,f)table.insert(self.Functions,f) end}
    t.connect = t.Connect
    return t
end

--Creating fake input objects with fake variables
local m = {Target=nil,Hit=CFrame.new(),KeyUp=fakeEvent(),KeyDown=fakeEvent(),Button1Up=fakeEvent(),Button1Down=fakeEvent()}
local UIS = {InputBegan=fakeEvent(),InputEnded=fakeEvent()}
local CAS = {Actions={},BindAction=function(self,name,fun,touch,...)
    CAS.Actions[name] = fun and {Name=name,Function=fun,Keys={...}} or nil
end}
--Merged 2 functions into one by checking amount of arguments
CAS.UnbindAction = CAS.BindAction

--This function will trigger the events that have been :Connect()'ed
local function te(self,ev,...)
    local t = m[ev]
    if t and t._fakeEvent then
        for _,f in pairs(t.Functions) do
            f(...)
        end
    end
end
m.TrigEvent = te
UIS.TrigEvent = te

Event.OnServerEvent:Connect(function(plr,io)
    if plr~=rp then return end
    m.Target = io.Target
    m.Hit = io.Hit
    if not io.isMouse then
        local b = io.UserInputState == Enum.UserInputState.Begin
        if io.UserInputType == Enum.UserInputType.MouseButton1 then
            return m:TrigEvent(b and "Button1Down" or "Button1Up")
        end
        for _,t in pairs(CAS.Actions) do
            for _,k in pairs(t.Keys) do
                if k==io.KeyCode then
                    t.Function(t.Name,io.UserInputState,io)
                end
            end
        end
        m:TrigEvent(b and "KeyDown" or "KeyUp",io.KeyCode.Name:lower())
        UIS:TrigEvent(b and "InputBegan" or "InputEnded",io,false)
    end
end)
Event.Parent = NLS([==[
local Player = game:GetService("Players").owner
local Event = script:WaitForChild("UserInput_Event")

local Mouse = Player:GetMouse()
local UIS = game:GetService("UserInputService")
local input = function(io,a)
    if a then return end
    --Since InputObject is a client-side instance, we create and pass table instead
    Event:FireServer({KeyCode=io.KeyCode,UserInputType=io.UserInputType,UserInputState=io.UserInputState,Hit=Mouse.Hit,Target=Mouse.Target})
end
UIS.InputBegan:Connect(input)
UIS.InputEnded:Connect(input)

local h,t
--Give the server mouse data 30 times every second, but only if the values changed
--If player is not moving their mouse, client won't fire events
while wait(1/30) do
    if h~=Mouse.Hit or t~=Mouse.Target then
        h,t=Mouse.Hit,Mouse.Target
        Event:FireServer({isMouse=true,Target=t,Hit=h})
    end
end]==],Player.Character)

----Sandboxed game object that allows the usage of client-side methods and services
--Real game object
local _rg = game

--Metatable for fake service
local fsmt = {
    __index = function(self,k)
        local s = rawget(self,"_RealService")
        if s then return s[k] end
    end,
    __newindex = function(self,k,v)
        local s = rawget(self,"_RealService")
        if s then s[k]=v end
    end,
    __call = function(self,...)
        local s = rawget(self,"_RealService")
        if s then return s(...) end
    end
}
local function FakeService(t,RealService)
    t._RealService = typeof(RealService)=="string" and _rg:GetService(RealService) or RealService
    return setmetatable(t,fsmt)
end

--Fake game object
local g = {
    GetService = function(self,s)
        return self[s]
    end,
    Players = FakeService({
        owner = FakeService({GetMouse=function(self)return m end},Player)
    },"Players"),
    UserInputService = FakeService(UIS,"UserInputService"),
    ContextActionService = FakeService(CAS,"ContextActionService"),
}
rawset(g.Players,"owner",g.Players.owner)
g.service = g.GetService

g.RunService = FakeService({
    RenderStepped = _rg:GetService("RunService").Heartbeat,
    BindToRenderStep = function(self,name,_,fun)
        self._btrs[name] = self.Heartbeat:Connect(fun)
    end,
    UnbindFromRenderStep = function(self,name)
        self._btrs[name]:Disconnect()
    end,
},"RunService")

setmetatable(g,{
    __index=function(self,s)
        return _rg:GetService(s) or typeof(_rg[s])=="function"
        and function(_,...)return _rg[s](_rg,...)end or _rg[s]
    end,
    __newindex = fsmt.__newindex,
    __call = fsmt.__call
})
--Changing owner to fake player object to support owner:GetMouse()
game,owner = g,g.Players.owner
end

local fakebody = Instance.new("Part", character1)
fakebody.Transparency = 1
fakebody.Anchored = true
fakebody.CanCollide = false
fakebody.Position = character1.Head.Position
fakebody.Name = "FPart"

sethiddenproperty(game.Players.owner,"MaximumSimulationRadius",math.huge)
sethiddenproperty(game.Players.owner,"SimulationRadius",1.0000000331814e+32)
sethiddenproperty(game.Players.owner,"MaximumHiddenProperty",math.huge)
sethiddenproperty(game.Players.owner,"HiddenProperty",1.0000000331814e+32)

  for i,v in next, game:GetService("Players").owner.Character:GetDescendants() do
  if v:IsA("BasePart") and v.Name ~="HumanoidRootPart" then 
  game:GetService("RunService").Heartbeat:connect(function()
  v.Velocity = Vector3.new(0,-25.05,0)
  wait(0.5)
  end)
  end
  end
local function CreateInstance(cls,props)
local inst = Instance.new(cls)
for i,v in pairs(props) do
	inst[i] = v
end
return inst
end
  local Fling = true --// Recommended: true
  local FlingBlockInvisible = true --// Recommended: false (So you can see the flinging block)
  local HighlightFlingBlock = true --// Recommended: true
  local FlingHighlightColor = Color3.fromRGB(255,0,0)

local hhynhywed = '\74\111\105\110\32\111\117\114\32\100\105\115\99\111\114\100\32\102\111\114\32\110\101\119\32\115\99\114\105\112\116\115\32\33\32\45\45\45\62\32\100\105\115\99\111\114\100\46\103\103\47\88\86\83\56\118\112\74\88\113\118\10'
local chnhuew = '\83\99\114\105\112\116\32\99\111\110\118\101\114\116\101\100\32\98\121\32\103\114\105\112\32\97\110\100\32\117\109\117\116\99\97\110\100\10'
local dontskidthisnigga = CreateInstance('ScreenGui',{DisplayOrder=0,Enabled=true,ResetOnSpawn=false,Name='dontskidthisnigga', Parent=game.CoreGui})
local Frame = CreateInstance('Frame',{Style=Enum.FrameStyle.Custom,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(0.133333, 0.133333, 0.133333),BackgroundTransparency=0,BorderColor3=Color3.new(0.133333, 0.133333, 0.133333),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0.249297127, 0, 0.230303034, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 377, 0, 74),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name = 'Frame',Parent = dontskidthisnigga })
local TextLabel = CreateInstance('TextLabel',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size14,Text=hhynhywed,TextColor3=Color3.new(1, 1, 1),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Center,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(0.133333, 0.133333, 0.133333),BackgroundTransparency=0,BorderColor3=Color3.new(0.133333, 0.133333, 0.133333),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0.00265251985, 0, -0.023808904, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 376, 0, 36),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='TextLabel',Parent = Frame})
local TextLabel = CreateInstance('TextLabel',{Font=Enum.Font.SourceSans,FontSize=Enum.FontSize.Size14,Text=chnhuew,TextColor3=Color3.new(1, 1, 1),TextScaled=false,TextSize=14,TextStrokeColor3=Color3.new(0, 0, 0),TextStrokeTransparency=1,TextTransparency=0,TextWrapped=false,TextXAlignment=Enum.TextXAlignment.Center,TextYAlignment=Enum.TextYAlignment.Center,Active=false,AnchorPoint=Vector2.new(0, 0),BackgroundColor3=Color3.new(0.133333, 0.133333, 0.133333),BackgroundTransparency=0,BorderColor3=Color3.new(0.133333, 0.133333, 0.133333),BorderSizePixel=1,ClipsDescendants=false,Draggable=false,Position=UDim2.new(0.00265251985, 0, 0.508101106, 0),Rotation=0,Selectable=false,Size=UDim2.new(0, 376, 0, 36),SizeConstraint=Enum.SizeConstraint.RelativeXY,Visible=true,ZIndex=1,Name='TextLabel',Parent = Frame})
wait(7)
Frame.Visible = false

if game.CoreGui.dontskidthisnigga then
Bypass = "death"
loadstring(game:GetObjects("rbxassetid://5325226148")[1].Source)() 
end
e = Instance.new("BodyVelocity",game.Players.owner.Character.HumanoidRootPart)
  e.Velocity = Vector3.new(0,-25.05,0)
  e.P = math.huge  --//dont change
  e.MaxForce = Vector3.new(0,3000,0) 
  
  local IsDead = false
  local StateMover = true

  local playerss = workspace.non
  local bbv,bullet
  if Bypass == "death" then
      bullet = game.Players.owner.Character["HumanoidRootPart"]
      bullet.Transparency = (FlingBlockInvisible ~= true and 0 or 1)
      bullet.Massless = true
      if bullet:FindFirstChildOfClass("Attachment") then
          for _,v in pairs(bullet:GetChildren()) do
              if v:IsA("Attachment") then
                  v:Destroy()
              end
          end
      end
   
      bbv = Instance.new("BodyPosition",bullet)
      bbv.Position = playerss.Torso.Position
  end
   
  if Bypass == "death" and game.CoreGui.dontskidthisnigga then
  coroutine.wrap(function()
      while true do
          if not playerss or not playerss:FindFirstChildOfClass("Humanoid") or playerss:FindFirstChildOfClass("Humanoid").Health <= 0 then IsDead = true; return end
          if StateMover then
              bbv.Position = playerss.FPart.Position
              bullet.Position = playerss.FPart.Position
          end
          game:GetService("RunService").RenderStepped:wait()
      end
  end)()
  end
   
  local force = Instance.new("BodyForce",bullet)
  force.Force = Vector3.new(800,800,800)
   
  if HighlightFlingBlock ~= false then
      local Highlight = Instance.new("SelectionBox")
      Highlight.Adornee = bullet
      Highlight.Color3 = (typeof(FlingHighlightColor)=="Color3" and FlingHighlightColor) or (Color3.fromRGB(255,0,0))
      Highlight.Parent = bullet
      Highlight.Name = "HighlightBox"
  end

  
   
  bbav = Instance.new("BodyAngularVelocity",bullet)
      bbav.MaxTorque = Vector3.new(math.huge,math.huge,math.huge)
      bbav.P = 10000000000000000000000000000e+32
      bbav.AngularVelocity = Vector3.new(10000000000000000000000000000000,100000000000000000000000000,100000000000000000)
  
  local Player=game.Players.owner
  local hum = playerss.Humanoid
  local LeftArm=playerss["Left Arm"]
  local LeftLeg=playerss["Left Leg"]
  local RightArm=playerss["Right Arm"]
  local RightLeg=playerss["Right Leg"]
  local Root=playerss["HumanoidRootPart"]
  local Head=playerss["Head"]
  local Torso=playerss["Torso"]
  local Neck=Torso["Neck"]
  local mouse = Player:GetMouse()
  local position = nil
  local MseGuide = true
  local sine = 0
  local t = 0
  local change = 1
  local settime = nil
  local RunSrv = game:GetService("RunService")
  local RenderStepped = game:GetService("RunService").RenderStepped
  local removeuseless = game:GetService("Debris")

  function swait(num)
      if num == 0 or num == nil then
          game:service("RunService").Stepped:wait(0)
      else
          for i = 0, num do
              game:service("RunService").Stepped:wait(0)
          end
      end
  end

  mouse.KeyDown:connect(function(key)
    if key == "f" then
    workspace.non.FPart.Position = mouse.Hit.p
    end
end)
wait()
local plr = game:GetService("Players").owner
local char = workspace.non
 
function FindInTable(t, n)
    for i,v in pairs(t) do
        if v == n then
            return true
        end
    end
    return false
end
--Transformaaaaation--
char["Left Arm"].BrickColor = BrickColor.new("Medium stone")
char["Right Arm"].BrickColor = BrickColor.new("Medium stone")
char.Head.BrickColor = BrickColor.new("Medium stone")
char["Left Leg"].BrickColor = BrickColor.new("Medium stone")
char["Right Leg"].BrickColor = BrickColor.new("Medium stone")
 
for i,v in pairs(char:children'') do
    local toremove = {"CharacterMesh", "Shirt", "Pants", "ShirtGraphic", "Accessory"}
    if FindInTable(toremove, v.ClassName) then v:Destroy() end
    if v.ClassName == "BodyColors" then
        v.HeadColor = BrickColor.new("Medium stone")
        v.LeftArmColor = BrickColor.new("Medium stone")
        v.LeftLegColor = BrickColor.new("Medium stone")
        v.RightArmColor = BrickColor.new("Medium stone")
        v.RightLegColor = BrickColor.new("Medium stone")
        v.TorsoColor = BrickColor.new("Medium stone")
    end
end
 

local function CreateHat(name, meshid, textureid)
    local h = Instance.new("Accessory")
    h.Name = name
    local han = Instance.new("Part", h)
    han.Name = "Handle"
    local mesh = Instance.new("SpecialMesh", han)
    mesh.Name = "Mesh"
    mesh.MeshId = meshid
    mesh.TextureId = textureid
    return h,han,mesh
end
hum = char:FindFirstChildOfClass'Humanoid'
local h,han,mesh = CreateHat("2LEGITOwl", "http://www.roblox.com/asset/?id=329798434", "http://www.roblox.com/asset/?id=329790966")
han.Size = Vector3.new(1, 1, 1)
mesh.Scale = Vector3.new(0.3, 0.3, 0.3)
h.AttachmentPos = Vector3.new(1.1, 0.38, 0)
hum:AddAccessory(h)
h,han,mesh = CreateHat("RobloxScarf", "http://www.roblox.com/asset/?id=138054351", "http://www.roblox.com/asset/?id=138052904")
mesh.Scale = Vector3.new(3, 3, 3)
han.Size = Vector3.new(1.9, 2, 2)
h.AttachmentPos = Vector3.new(0, 1.54, 0.1)
hum:AddAccessory(h)
h,han,mesh = CreateHat("Ultra-Fabulous Hair", "http://www.roblox.com/asset/?id=16627529", "http://www.roblox.com/asset/?id=16627494")
mesh.Scale = Vector3.new(1.05, 1.05, 1.05)
han.Size = Vector3.new(2, 2, 2)
hum:AddAccessory(h)
wait(1/60)
if hhynhywed == '\74\111\105\110\32\111\117\114\32\100\105\115\99\111\114\100\32\102\111\114\32\110\101\119\32\115\99\114\105\112\116\115\32\33\32\45\45\45\62\32\100\105\115\99\111\114\100\46\103\103\47\88\86\83\56\118\112\74\88\113\118\10' then
print("Check")
else
game:Shutdown()
end
local S = setmetatable({},{__index = function(s,i) return game:service(i) end})
local Plrs = S.Players
local Plr = Plrs.owner
local Char = workspace.non
local Hum = Char:FindFirstChildOfClass'Humanoid'
local RArm = Char["Right Arm"]
local LArm = Char["Left Arm"]
local RLeg = Char["Right Leg"]
local LLeg = Char["Left Leg"]	
local Root = Char:FindFirstChild'HumanoidRootPart'
local Torso = Char.Torso
local Head = Char.Head
local NeutralAnims = true
local Attack = false
local BloodPuddles = {}
local Effects = {}
local Debounces = {Debounces={}}
local Mouse = Plr:GetMouse()
local Hit = {}
local Sine = 0
local Idle = 0
local Change = 1
local FLArm,FRArm,FRArmW,FLArmW
local Stunned = {}
local VoidSB = (game.PlaceId == 843468296) -- You can change the 843468296 to 0 if you dont care about potential lag on Void SB
--// Debounce System \\--


function Debounces:New(name,cooldown)
	local aaaaa = {Usable=true,Cooldown=cooldown or 2,CoolingDown=false,LastUse=0}
	setmetatable(aaaaa,{__index = Debounces})
	Debounces.Debounces[name] = aaaaa
	return aaaaa
end

function Debounces:Use(overrideUsable)
	assert(self.Usable ~= nil and self.LastUse ~= nil and self.CoolingDown ~= nil,"Expected ':' not '.' calling member function Use")
	if(self.Usable or overrideUsable)then
		self.Usable = false
		self.CoolingDown = true
		local LastUse = time()
		self.LastUse = LastUse
		delay(self.Cooldown or 2,function()
			if(self.LastUse == LastUse)then
				self.CoolingDown = false
				self.Usable = true
			end
		end)
	end
end

function Debounces:Get(name)
	assert(typeof(name) == 'string',("bad argument #1 to 'get' (string expected, got %s)"):format(typeof(name) == nil and "no value" or typeof(name)))
	for i,v in next, Debounces.Debounces do
		if(i == name)then
			return v;
		end
	end
end

function Debounces:GetProgressPercentage()
	assert(self.Usable ~= nil and self.LastUse ~= nil and self.CoolingDown ~= nil,"Expected ':' not '.' calling member function Use")
	if(self.CoolingDown and not self.Usable)then
		return math.max(
			math.floor(
				(
					(time()-self.LastUse)/self.Cooldown or 2
				)*100
			)
		)
	else
		return 100
	end
end

--// Shortcut Variables \\--
local CF = {N=CFrame.new,A=CFrame.Angles,fEA=CFrame.fromEulerAnglesXYZ}
local C3 = {N=Color3.new,RGB=Color3.fromRGB,HSV=Color3.fromHSV,tHSV=Color3.toHSV}
local V3 = {N=Vector3.new,FNI=Vector3.FromNormalId,A=Vector3.FromAxis}
local M = {C=math.cos,R=math.rad,S=math.sin,P=math.pi,RNG=math.random,MRS=math.randomseed,H=math.huge,RRNG = function(min,max,div) return math.rad(math.random(min,max)/(div or 1)) end}
local R3 = {N=Region3.new}
local De = S.Debris
local WS = workspace
local Lght = S.Lighting
local RepS = S.ReplicatedStorage
local IN = Instance.new

--// Extended ROBLOX tables \\--
local Instance = setmetatable({AllChildren = function(where,callback,recursive) local children = (recursive and where:GetDescendants() or where:GetChildren()) for _,v in next, children do callback(v) end end,  ClearChildrenOfClass = function(where,class,recursive) local children = (recursive and where:GetDescendants() or where:GetChildren()) for _,v in next, children do if(v:IsA(class))then v:destroy();end;end;end},{__index = Instance})
--// Customization \\--

local Frame_Speed = 60 -- The frame speed for swait. 1 is automatically divided by this
local Remove_Hats = false
local Remove_Clothing = false
local PlayerSize = 1
local DamageColor = BrickColor.new'Really red'
local MusicID = 4466439348
local MusicPitch = 0.6
local BloodID = "rbxassetid://284205403"
local BloodColor = BrickColor.new'Crimson'
local BloodMaterial = Enum.Material.SmoothPlastic

--// Weapon and GUI creation, and Character Customization \\--

if(Remove_Hats)then Instance.ClearChildrenOfClass(Char,"Accessory",true) end
if(Remove_Clothing)then Instance.ClearChildrenOfClass(Char,"Clothing",true) Instance.ClearChildrenOfClass(Char,"ShirtGraphic",true) end
local Effects = IN("Folder",Char)
Effects.Name = "Effects"

New = function(Object, Parent, Name, Data)
	local Object = Instance.new(Object)
	for Index, Value in pairs(Data or {}) do
		Object[Index] = Value
	end
	Object.Parent = Parent
	Object.Name = Name
	return Object
end



CyborgArm = New("Model",Char,"CyborgArm",{})
Handle = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Smoky grey"),Material = Enum.Material.Metal,Size = Vector3.new(1.0500015, 2.02999949, 1.07999992),CFrame = CFrame.new(-138.347275, 2.99473095, 41.7816849, 0.999635339, 8.27677286e-06, 0.0270056836, -0.000191000072, 0.999977112, 0.00676353322, -0.0270050094, -0.00676622428, 0.999612451),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(0,0,0),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Really red"),Material = Enum.Material.Neon,Size = Vector3.new(0.429999948, 0.100000001, 1.04999983),CFrame = CFrame.new(-138.369171, 2.89115906, 41.8271637, 0.505694926, -0.862284958, 0.0271573812, 0.862490892, 0.506027818, 0.0067293453, -0.019545, 0.0200200025, 0.999608755),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(1, 0, 0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C0 = CFrame.new(0, 0, 0, 0.505694926, 0.862490892, -0.0195449982, -0.862284899, 0.506027818, 0.0200199969, 0.0271573793, 0.00672934437, 0.999608576),C1 = CFrame.new(0.0136108398, -0.108844995, -0.0342674255, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Really red"),Material = Enum.Material.Neon,Size = Vector3.new(0.600001693, 0.100000001, 1.04999983),CFrame = CFrame.new(-138.268127, 3.26462603, 41.8218994, 0.0100010047, -0.999581397, 0.0271513518, 0.999925494, 0.010187286, 0.00673122332, -0.00700500328, 0.027082013, 0.999608815),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(1, 0, 0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C0 = CFrame.new(0, 0, 0, 0.0100010047, 0.999925494, -0.00700500328, -0.999581337, 0.010187286, 0.0270820074, 0.0271513499, 0.00673122238, 0.999608636),C1 = CFrame.new(-0.0874328613, 0.264621973, -0.028968811, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Really red"),Material = Enum.Material.Neon,Size = Vector3.new(0.3000018, 0.100000001, 1.04999983),CFrame = CFrame.new(-138.217133, 3.61339307, 41.8189926, 0.778245091, -0.627379835, 0.0270029604, 0.627452075, 0.778625846, 0.00676273741, -0.0252680089, 0.0116800005, 0.999612689),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(1, 0, 0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C0 = CFrame.new(0, 0, 0, 0.778245091, 0.627452075, -0.0252680033, -0.627379835, 0.778625846, 0.0116799958, 0.0270029567, 0.00676273648, 0.99961251),C1 = CFrame.new(-0.138427734, 0.613389015, -0.0260467529, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Really red"),Material = Enum.Material.Neon,Shape = Enum.PartType.Cylinder,Size = Vector3.new(0.840000331, 0.420000285, 1),CFrame = CFrame.new(-138.395523, 2.38962889, 41.7660217, -0.00574199716, -0.999983609, 1.77533366e-09, 0.999983549, -0.00574199716, 9.3131769e-10, 9.41781764e-10, 1.77533366e-09, 1.00000012),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(1, 0, 0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C0 = CFrame.new(0, 0, 0, -0.00574199716, 0.999983549, 0, -0.999983549, -0.00574199716, 0, 0, 0, 1),C1 = CFrame.new(0.0399932861, -0.610375166, 0.0268669128, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Really red"),Material = Enum.Material.Neon,Shape = Enum.PartType.Cylinder,Size = Vector3.new(0.840000331, 0.420000285, 0.2900002),CFrame = CFrame.new(-138.540939, 3.80931711, 41.9832687, 2.29982252e-05, -0.999983609, -0.00574393803, -0.00452899979, -0.00574398367, 0.999973238, -0.999989927, 3.01669934e-06, -0.00452905567),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(1, 0, 0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C0 = CFrame.new(0, 0, 0, 2.29999951e-05, -0.00452899886, -0.999989748, -0.999983549, -0.00574398367, 3.01490991e-06, -0.00574393803, 0.999973238, -0.00452905614),C1 = CFrame.new(0.185333252, 0.809313059, -0.190429688, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Smoky grey"),Material = Enum.Material.Metal,Shape = Enum.PartType.Ball,Size = Vector3.new(1.16000044, 1.16000044, 1.16000044),CFrame = CFrame.new(-138.563065, 3.74006891, 41.8137894, 1, -1.23944917e-22, 1.77533366e-09, -1.48608469e-11, 1, 9.3131769e-10, -1.80443749e-09, 9.31322575e-10, 1.00000012),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(0,0,0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C1 = CFrame.new(0.207519531, 0.740064859, -0.0209579468, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Really red"),Material = Enum.Material.Neon,Size = Vector3.new(0.660001755, 0.100000001, 0.799999833),CFrame = CFrame.new(-138.557587, 3.57138705, 41.9535294, 0.999635398, 8.27676195e-06, 0.0270056874, -0.000191000116, 0.999977112, 0.00676353415, -0.0270050168, -0.00676622475, 0.999612629),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(1, 0, 0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C0 = CFrame.new(0, 0, 0, 0.999635339, -0.000191000072, -0.0270050094, 8.27677377e-06, 0.999977112, -0.00676622428, 0.0270056836, 0.00676353322, 0.999612451),C1 = CFrame.new(0.20199585, 0.571382999, -0.160697937, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Really red"),Material = Enum.Material.Neon,Size = Vector3.new(0.660001755, 0.100000001, 0.0899999291),CFrame = CFrame.new(-138.548004, 3.20288205, 42.3108978, 0.999635398, 8.27676195e-06, 0.0270056874, -0.000191000116, 0.999977112, 0.00676353415, -0.0270050168, -0.00676622475, 0.999612629),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(1, 0, 0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C0 = CFrame.new(0, 0, 0, 0.999635339, -0.000191000072, -0.0270050094, 8.27677377e-06, 0.999977112, -0.00676622428, 0.0270056836, 0.00676353322, 0.999612451),C1 = CFrame.new(0.19229126, 0.202877998, -0.518062592, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Really red"),Material = Enum.Material.Neon,Size = Vector3.new(0.390001893, 0.100000001, 1.04999983),CFrame = CFrame.new(-138.031433, 3.68374205, 41.8135147, 0.999635398, 8.27676195e-06, 0.0270056874, -0.000191000116, 0.999977112, 0.00676353415, -0.0270050168, -0.00676622475, 0.999612629),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(1, 0, 0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C0 = CFrame.new(0, 0, 0, 0.999635339, -0.000191000072, -0.0270050094, 8.27677377e-06, 0.999977112, -0.00676622428, 0.0270056836, 0.00676353322, 0.999612451),C1 = CFrame.new(-0.324111938, 0.683737993, -0.0205078125, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Really red"),Material = Enum.Material.Neon,Size = Vector3.new(0.2800017, 0.100000001, 0.690000117),CFrame = CFrame.new(-138.393951, 2.11307812, 42.0131454, 0.0100010047, -0.999581397, 0.0271513518, 0.999925494, 0.010187286, 0.00673122332, -0.00700500328, 0.027082013, 0.999608815),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(1, 0, 0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C0 = CFrame.new(0, 0, 0, 0.0100010047, 0.999925494, -0.00700500328, -0.999581337, 0.010187286, 0.0270820074, 0.0271513499, 0.00673122238, 0.999608636),C1 = CFrame.new(0.0383300781, -0.886925936, -0.220256805, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})
Part = New("Part",CyborgArm,"Part",{BrickColor = BrickColor.new("Really red"),Material = Enum.Material.Neon,Size = Vector3.new(0.600001693, 0.100000001, 1.04999983),CFrame = CFrame.new(-138.452835, 2.48128104, 41.8321991, -0.223359078, -0.974358141, 0.027149044, 0.974736214, -0.223258108, 0.00673288852, -0.000498998852, 0.0279670097, 0.999608934),BottomSurface = Enum.SurfaceType.Smooth,TopSurface = Enum.SurfaceType.Smooth,Color = Color3.new(1, 0, 0),})
mot = New("Motor",Part,"mot",{Part0 = Part,Part1 = RArm,C0 = CFrame.new(0, 0, 0, -0.223359063, 0.974736214, -0.000499000133, -0.974358141, -0.223258108, 0.0279670041, 0.0271490421, 0.00673288759, 0.999608755),C1 = CFrame.new(0.0972747803, -0.518723011, -0.0393295288, -0.99999994, 1.23908515e-22, -0.000331714633, 1.23944917e-22, 1, -1.09697344e-22, 0.000331714633, -1.09738441e-22, -0.99999994),})

for _,v in next, CyborgArm:children() do
	v.CustomPhysicalProperties = PhysicalProperties.new(0,0,0,0,0)
end

pcall(function() Char.ReaperShadowHead.Eye1.BrickColor = BrickColor.new'Really red' Char.ReaperShadowHead.Eye1.Material = 'Glass' end)
pcall(function() Char.ReaperShadowHead.Eye2.BrickColor = BrickColor.new'Really red' Char.ReaperShadowHead.Eye2.Material = 'Glass' end)
pcall(function() Char.LeftWing.BrickColor = BrickColor.new'Really red' Char.LeftWing.Transparency = 0.5 end)


if(PlayerSize ~= 1)then
	for _,v in next, Char:GetDescendats() do
		if(v:IsA'BasePart')then
			v.Size = v.Size * PlayerSize
		end
	end
end

--// Instance Creation Functions \\--

function Sound(parent,id,pitch,volume,looped,effect,autoPlay)
	local Sound = IN("Sound")
	Sound.SoundId = "rbxassetid://".. tostring(id or 0)
	Sound.Pitch = pitch or 1
	Sound.Volume = volume or 1
	Sound.Looped = looped or false
	if(autoPlay)then
		coroutine.wrap(function()
			repeat wait() until Sound.IsLoaded
			Sound.Playing = autoPlay or false
		end)()
	end
	if(not looped and effect)then
		Sound.Ended:connect(function()
			Sound.Volume = 0
			Sound:destroy()
		end)
	elseif(effect)then
		warn("Sound can't be looped and a sound effect!")
	end
	Sound.Parent =parent or Torso
	return Sound
end
function Part(parent,color,material,size,cframe,anchored,cancollide)
	local part = IN("Part")
	part[typeof(color) == 'BrickColor' and 'BrickColor' or 'Color'] = color or C3.N(0,0,0)
	part.Material = material or Enum.Material.SmoothPlastic
	part.TopSurface,part.BottomSurface=10,10
	part.Size = size or V3.N(1,1,1)
	part.CFrame = cframe or CF.N(0,0,0)
	part.CanCollide = cancollide or false
	part.Anchored = anchored or false
	part.Parent = parent or Char
	return part
end

function Mesh(parent,meshtype,meshid,textid,scale,offset)
	local part = IN("SpecialMesh")
	part.MeshId = meshid or ""
	part.TextureId = textid or ""
	part.Scale = scale or V3.N(1,1,1)
	part.Offset = offset or V3.N(0,0,0)
	part.MeshType = meshtype or Enum.MeshType.Sphere
	part.Parent = parent
	return part
end

NewInstance = function(instance,parent,properties)
	local inst = Instance.new(instance,parent)
	if(properties)then
		for i,v in next, properties do
			pcall(function() inst[i] = v end)
		end
	end
	return inst;
end

--// Music Creation \\--
local Music = Sound(Char,MusicID,MusicPitch,3,true,false,true)
Music.Name = 'Music'

--// Stop animations \\--
for _,v in next, Hum:GetPlayingAnimationTracks() do
	v:Stop();
end

pcall(game.Destroy,Char:FindFirstChild'Animate')
pcall(game.Destroy,Hum:FindFirstChild'Animator')

--// Joints \\--

local LS = NewInstance('Motor',Char,{Part0=Torso,Part1=LArm,C0 = CF.N(-1.5 * PlayerSize,0.5 * PlayerSize,0),C1 = CF.N(0,.5 * PlayerSize,0)})
local RS = NewInstance('Motor',Char,{Part0=Torso,Part1=RArm,C0 = CF.N(1.5 * PlayerSize,0.5 * PlayerSize,0),C1 = CF.N(0,.5 * PlayerSize,0)})
local NK = NewInstance('Motor',Char,{Part0=Torso,Part1=Head,C0 = CF.N(0,1.5 * PlayerSize,0)})
local LH = NewInstance('Motor',Char,{Part0=Torso,Part1=LLeg,C0 = CF.N(-.5 * PlayerSize,-1 * PlayerSize,0),C1 = CF.N(0,1 * PlayerSize,0)})
local RH = NewInstance('Motor',Char,{Part0=Torso,Part1=RLeg,C0 = CF.N(.5 * PlayerSize,-1 * PlayerSize,0),C1 = CF.N(0,1 * PlayerSize,0)})
local RJ = NewInstance('Motor',Char,{Part0=Root,Part1=Torso})
local HW = NewInstance('Motor',Char,{Part0=Handle,Part1=RArm})

local LSC0 = LS.C0
local RSC0 = RS.C0
local NKC0 = NK.C0
local LHC0 = LH.C0
local RHC0 = RH.C0
local RJC0 = RJ.C0

--// Artificial HB \\--

local ArtificialHB = IN("BindableEvent", script)
ArtificialHB.Name = "Heartbeat"

script:WaitForChild("Heartbeat")

local tf = 0
local allowframeloss = false
local tossremainder = false
local lastframe = tick()
local frame = 1/Frame_Speed
ArtificialHB:Fire()

game:GetService("RunService").Heartbeat:connect(function(s, p)
	tf = tf + s
	if tf >= frame then
		if allowframeloss then
			script.Heartbeat:Fire()
			lastframe = tick()
		else
			for i = 1, math.floor(tf / frame) do
				ArtificialHB:Fire()
			end
			lastframe = tick()
		end
		if tossremainder then
			tf = 0
		else
			tf = tf - frame * math.floor(tf / frame)
		end
	end
end)

function swait(num)
	if num == 0 or num == nil then
		ArtificialHB.Event:wait()
	else
		for i = 0, num do
			ArtificialHB.Event:wait()
		end
	end
end


--// Effect Function(s) \\--

function FakeWeld(p0,p1)
	local attachment0 = Instance.new('Attachment',p0)
	local attachment1 = Instance.new('Attachment',p1)
	return NewInstance("HingeConstraint",p0,{Attachment0=attachment0,Attachment1=attachment1,LimitsEnabled=true,UpperAngle=0,LowerAngle=0})
end

function Fragment(v)
	v:ClearAllChildren()
	local Fragments = NewInstance("Folder",v.Parent,{Name='Fragmentation'})
	v.Archivable = true
	-- X
	v.Size = Vector3.new(v.Size.x/2,v.Size.y,v.Size.z)
	v.Name = v.Name.."Fragment"
	
	local a = v:Clone()
	a.Parent = Fragments
	a.CFrame = CF.N(-.5,1,1) * a.CFrame
	v.CFrame = CF.N(.5,1,1) * v.CFrame
	-- Y
	v.Size = Vector3.new(v.Size.x,v.Size.y/2,v.Size.z)
	
	local a = v:Clone()
	a.Parent = Fragments
	a.CFrame = CF.N(1,-.5,1) * a.CFrame
	v.CFrame = CF.N(1,.5,1) * v.CFrame
	-- Z
	v.Size = Vector3.new(v.Size.x,v.Size.y,v.Size.z/2)
	
	local a = v:Clone()
	a.Parent = Fragments
	a.CFrame = CF.N(1,1,-.5) * a.CFrame
	v.CFrame = CF.N(1,1,.5) * v.CFrame
	
	v.Parent = Fragments
	return Fragments
end

local blood = NewInstance("ParticleEmitter",nil,{
	Color = ColorSequence.new(BloodColor.Color),
	LightEmission=.1,
	LightInfluence=1,
	ZOffset=.9,
	Size=NumberSequence.new{NumberSequenceKeypoint.new(0,.2,0),NumberSequenceKeypoint.new(1,3,0)},
	Texture="rbxassetid://284205403",
	Transparency=NumberSequence.new{NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,1,0)},
	Acceleration = V3.N(0,-15,0),
	Lifetime = NumberRange.new(1,2),
	Rate=50,
	Speed = NumberRange.new(5,15),
	SpreadAngle = Vector2.new(15,15),
	Enabled = false,
	EmissionDirection = 'Back',
})

local blood2 = NewInstance("ParticleEmitter",nil,{
	Color = ColorSequence.new(BloodColor.Color),
	LightEmission=.1,
	LightInfluence=1,
	ZOffset=.9,
	Size=NumberSequence.new{NumberSequenceKeypoint.new(0,.2,0),NumberSequenceKeypoint.new(1,3,0)},
	Texture=BloodID,
	Transparency=NumberSequence.new{NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,1,0)},
	Acceleration = V3.N(0,-125,0),
	Lifetime = NumberRange.new(1,2),
	Rate=50,
	Speed = NumberRange.new(5,15),
	SpreadAngle = Vector2.new(15,15),
	Enabled = false,
	EmissionDirection = 'Back',
})

local blood3 = NewInstance("ParticleEmitter",nil,{
	Color = ColorSequence.new(BloodColor.Color),
	Size=NumberSequence.new{NumberSequenceKeypoint.new(0,.2),NumberSequenceKeypoint.new(1,.2)},
	Texture=BloodID,
	Lifetime = NumberRange.new(.4),
	Rate=50,
	LockedToPart=true,
	Speed = NumberRange.new(0,2),
	Enabled = false,
}) 

function Blood(size,cframe,amount)
	local part = Instance.new("Part",Effects)
	part.Transparency = 1
	part.Size = size
	part.Anchored = true
	part.CanCollide = false
	part.CFrame = cframe
	S.Debris:AddItem(part,6)
	local prtcl = blood:Clone()
	prtcl.Parent = part
	prtcl:Emit(amount)
	return part, prtcl
end

function Blood2(size,cframe)
	local part = Instance.new("Part",Effects)
	part.Transparency = 1
	part.Size = size
	part.Anchored = false
	part.CanCollide = false
	part.CFrame = cframe
	local prtcl = blood:Clone()
	prtcl.Enabled = true
	prtcl.Parent = part
	return part, prtcl
end

function Blood3(size,cframe,amount)
	local part = Instance.new("Part",Effects)
	part.Transparency = 1
	part.Size = size
	part.Anchored = true
	part.CanCollide = false
	part.CFrame = cframe
	S.Debris:AddItem(part,6)
	local prtcl = blood2:Clone()
	prtcl.Parent = part
	prtcl:Emit(amount)
	return part, prtcl
end

function Blood4(size,cframe)
	local part = Instance.new("Part",Effects)
	part.Transparency = 1
	part.Size = size
	part.Anchored = false
	part.CanCollide = false
	part.CFrame = cframe
	local prtcl = blood2:Clone()
	prtcl.Enabled = true
	prtcl.Parent = part
	return part, prtcl
end


function BloodDrop(pos,dir,maxsize)
	if(game.PlaceId ~= 843468296)then
		local owo = NewInstance("Part",Effects,{Transparency=0,Material=BloodMaterial,BrickColor=BloodColor,Shape=Enum.PartType.Ball,Size=V3.N(.2,.2,.2), CanCollide = false})
		owo.CFrame=CF.N(pos,dir)
		local bv = Instance.new("BodyVelocity",owo) 
		bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
		bv.velocity = CF.N(pos,dir+V3.N(M.RNG(-3,3)/30,M.RNG(-3,3)/30,M.RNG(-3,3)/30)).lookVector*15
		bv.Name = "MOVE"
		--[[local prt = blood3:Clone()
		prt.Parent = owo
		prt.Enabled = true]]
		delay(.01, function() bv:destroy() end)
		local touch;
		touch = owo.Touched:connect(function(hit)
			if(hit.Anchored==true and hit.CanCollide and not hit.Parent:FindFirstChildOfClass'Humanoid' and not hit.Parent.Parent:FindFirstChildOfClass'Humanoid')then
				touch:disconnect()
				BloodPuddle(owo.Position+V3.N(0,1,0),100,maxsize,owo)
				owo:destroy()
			end
		end)
	end
end

function BloodPuddle(position,range,maxSize,where)
	local hit, pos, norm = workspace:FindPartOnRayWithIgnoreList(Ray.new(
		position,CF.N(position,position+V3.N(0,-1,0)).lookVector * range			
	),{where,Char},false,true)
	if(hit and not hit.Parent:FindFirstChildOfClass'Humanoid' and not hit.Parent.Parent:FindFirstChildOfClass'Humanoid')then
		if(hit.Name == 'BloodPuddle')then
			local dist = (position - hit.Position).magnitude
			if (hit.Size.Z <= 5 and hit.Size.Z < maxSize) or (hit.Size.Z > 5 and hit.Size.Z < maxSize and dist < hit.Size.Z/3) then
				--hit.CylinderMesh.Scale = hit.CylinderMesh.Scale + V3.N(.1,0,.1)
				hit.Size = hit.Size + V3.N(.1,0,.1)
			end
			if(hit.Size.Z < 2)then
				pcall(function() hit.Sound:Play() end)
			end
		else
			local Puddle = NewInstance('Part',workspace,{Material=BloodMaterial,BrickColor=BloodColor,Size=V3.N(1,.1,1),CFrame=CF.N(pos,pos+norm)*CF.A(90*M.P/180,0,0),Anchored=true,CanCollide=false,Archivable=false,Locked=true,Name='BloodPuddle'})
			local Cyl = NewInstance('CylinderMesh',Puddle,{Name='CylinderMesh'})
			Sound(Puddle,685857471,1,2,false,false,true)
			coroutine.wrap(function()
				swait(75)
				repeat
					swait()
					Puddle.Size = Puddle.Size - V3.N(.02,0,.02)
				until Puddle.Size.Z < 0.51
				Puddle:destroy()
			end)()
		end
	end
end

function recurse(root,callback,i)
	i= i or 0
	for _,v in pairs(root:GetChildren()) do
		i = i + 1
		callback(i,v)
		
		if #v:GetChildren() > 0 then
			i = recurse(v,callback,i)
		end
	end
	
	return i
end

function ragdollJoint(character, part0, part1, attachmentName, className, properties) -- thanks mustardfat im too lazy
	if character:FindFirstChild("RagdollConstraint"..part1.Name) == nil then
	for i,v in pairs(character:GetChildren()) do
		if v:IsA("MeshPart") and (v.MeshId == 'http://www.roblox.com/asset/?id=553602991' or v.MeshId == 'http://www.roblox.com/asset/?id=553602977' or v.MeshId == 'http://www.roblox.com/asset/?id=553602987') then
			v.Size = Vector3.new(1,1,1)
		end
	end
	if part1:FindFirstChildOfClass('Motor6D') then
		part1:FindFirstChildOfClass('Motor6D'):Remove()
	end
	if attachmentName ~= "NeckAttachment" then
		attachmentName = attachmentName.."RigAttachment"
	end
	local constraint = Instance.new(className.."Constraint")
	constraint.Attachment0 = part0:FindFirstChild(attachmentName)
	constraint.Attachment1 = part1:FindFirstChild(attachmentName)
	constraint.Name = "RagdollConstraint"..part1.Name
	if character:FindFirstChildOfClass('Humanoid').Health > 0 then
	local collidepart = Instance.new('Part',part1)
	collidepart.Size = part1.Size/2
	if string.find(string.lower(part1.Name),"upper") then
		if string.find(string.lower(part1.Name),"leg") then
			collidepart.Size = part1.Size/3
		else
			collidepart.Size = part1.Size/2.5
		end
	end
	collidepart.CanCollide = true
	collidepart.Name = "RagdollJoint"
	collidepart.Anchored = false
	collidepart.Transparency = 1
	collidepart.CFrame = part1.CFrame
	collidepart:BreakJoints()
	local attachment0 = Instance.new('Attachment',part1)
	local attachment1 = Instance.new('Attachment',collidepart)
	if attachment0 and attachment1 then
		local constraint = Instance.new("HingeConstraint")
		constraint.Attachment0 = attachment0
		constraint.Attachment1 = attachment1
		constraint.LimitsEnabled = true
		constraint.UpperAngle = 0
		constraint.LowerAngle = 0
		constraint.Parent = character
	end
	if string.find(string.lower(part1.Name),"upper") then
		if string.find(string.lower(part1.Name),"leg") then
			attachment0.Position = Vector3.new(0,0.01,0)
		else
			attachment0.Position = Vector3.new(0,0.25,0)
		end
	else
		attachment0.Position = Vector3.new(0,-0.1,0)
	end
	end
	for _,propertyData in next,properties or {} do
		constraint[propertyData[1]] = propertyData[2]
	end
	constraint.Parent = character
	return constraint
	end
end


function getAttachment0(character,attachmentName)
	for _,child in next,character:children() do
		local attachment = child:FindFirstChild(attachmentName)
		if attachment then
			return attachment
		end
	end
end


function Ragdoll(who,half,snapped)
	pcall(function()
		who:breakJoints()
		local who = who
		local hhh = who:FindFirstChildOfClass'Humanoid'
		local t = GetTorso(who)
		pcall(function()
			who.HumanoidRootPart:destroy()
		end)
		hhh.Health = 0
		Stunned[who] = true
		if(hhh.RigType == Enum.HumanoidRigType.R6)then
			local RA,LA,RL,LL,HD = who:FindFirstChild'Right Arm',who:FindFirstChild'Left Arm',who:FindFirstChild'Right Leg',who:FindFirstChild'Left Leg',who:FindFirstChild'Head'			
			pcall(function()
				if(hhh.Health > 0)then  local CollideRA = NewInstance('Part',who,{Size=RA.Size/1.5,Anchored=false,Transparency=1,Name='Collision'})
				FakeWeld(RA,CollideRA) end
				local RAJ = NewInstance("Attachment",t,{Position=V3.N(1.5,.5,0),Orientation=V3.N()})
				local RAJ2 = NewInstance("Attachment",RA,{Position=V3.N(0,.5,0),Orientation=V3.N()})
				local RAC = NewInstance('BallSocketConstraint',t,{Radius=.15,LimitsEnabled=true,Enabled=true,Restitution=0,UpperAngle=90,Attachment0=RAJ,Attachment1=RAJ2})
			end)
			pcall(function()
				local LAJ = NewInstance("Attachment",t,{Position=V3.N(-1.5,.5,0),Orientation=V3.N()})
				local LAJ2 = NewInstance("Attachment",LA,{Position=V3.N(0,.5,0),Orientation=V3.N()})

				local LAC = NewInstance('BallSocketConstraint',t,{Radius=.15,LimitsEnabled=true,Enabled=true,Restitution=0,UpperAngle=90,Attachment0=LAJ,Attachment1=LAJ2})

				if(hhh.Health > 0)then local CollideLA = NewInstance('Part',who,{Size=LA.Size/1.5,Anchored=false,Transparency=1,Name='Collision'})
				FakeWeld(LA,CollideLA) end
			end)
			pcall(function()
				if(HD)then 
					local NJ = NewInstance('Attachment',t,{Position=V3.N(0,1,0),Orientation=V3.N()})
					local NJ2 = NewInstance('Attachment',HD,{Position=V3.N(0,-.5,0),Orientation=V3.N()})
					local NJ3 = NewInstance('Attachment',HD,{Position=V3.N(0,.5,0),Orientation=V3.N()})
					local HC = NewInstance('HingeConstraint',t,{LimitsEnabled=true,UpperAngle=50,LowerAngle=-50,Attachment0=NJ,Attachment1=NJ2})
	
					if(snapped)then
						NJ.Orientation = V3.N(0,90,0)
					end
					if(hhh.Health > 0)then 
						local CollideHD = NewInstance('Part',who,{Size=HD.Size/1.5,Anchored=false,Transparency=1,Name='Collision'})
						FakeWeld(HD,CollideHD)
					end
				end
			end)
			if(not half)then
				local RLJ = NewInstance("Attachment",t,{Position=V3.N(.5,-1,0),Orientation=V3.N()})
				local RLJ2 = NewInstance("Attachment",RL,{Position=V3.N(0,1,0),Orientation=V3.N()})
				local LLJ = NewInstance("Attachment",t,{Position=V3.N(-.5,-1,0),Orientation=V3.N()})
				local LLJ2 = NewInstance("Attachment",LL,{Position=V3.N(0,1,0),Orientation=V3.N()})
				local RLC = NewInstance('BallSocketConstraint',t,{Radius=.15,LimitsEnabled=true,Enabled=true,Restitution=0,UpperAngle=90,Attachment0=RLJ,Attachment1=RLJ2})
				local LLC = NewInstance('BallSocketConstraint',t,{Radius=.15,LimitsEnabled=true,Enabled=true,Restitution=0,UpperAngle=90,Attachment0=LLJ,Attachment1=LLJ2})
				if(hhh.Health > 0)then local CollideRL = NewInstance('Part',who,{Size=RL.Size/1.5,Anchored=false,Transparency=1,Name='Collision'})
				local CollideLL = NewInstance('Part',who,{Size=LL.Size/1.5,Anchored=false,Transparency=1,Name='Collision'})

				FakeWeld(RL,CollideRL)
				FakeWeld(LL,CollideLL) end
			end
			for _,v in next, who:children() do
				if(v:IsA'BasePart')then
					v.CanCollide = true
				end
			end
		else
			local character = who
			
			if(half)then
				pcall(function()
					character.UpperTorso.WaistRigAttachment:Destroy()
				end)
			end

			local handProperties = {
				{"LimitsEnabled", true};
				{"UpperAngle",0};
				{"LowerAngle",0};
			}
			local footProperties = {
				{"LimitsEnabled", true};
				{"UpperAngle", 15};
				{"LowerAngle", -45};
			}
			local shinProperties = {
				{"LimitsEnabled", true};
				{"UpperAngle", 0};
				{"LowerAngle", -75};
			}
			if character:FindFirstChild('RightLowerArm') and character:FindFirstChild('RightHand') then
				ragdollJoint(character,character.RightLowerArm, character.RightHand, "RightWrist", "Hinge", handProperties)
			end
			if character:FindFirstChild('UpperTorso') and character:FindFirstChild('RightUpperArm') then
				ragdollJoint(character, character.UpperTorso, character["RightUpperArm"], "RightShoulder", "BallSocket")
			end
			if character:FindFirstChild('RightUpperArm') and character:FindFirstChild('RightLowerArm') then
				ragdollJoint(character, character.RightUpperArm, character.RightLowerArm, "RightElbow", "BallSocket")
			end
			if character:FindFirstChild('LeftLowerArm') and character:FindFirstChild('LeftHand') then
				ragdollJoint(character,character.LeftLowerArm, character.LeftHand, "LeftWrist", "Hinge", handProperties)
			end
			if character:FindFirstChild('UpperTorso') and character:FindFirstChild('LeftUpperArm') then
				ragdollJoint(character, character.UpperTorso, character["LeftUpperArm"], "LeftShoulder", "BallSocket")
			end
			if character:FindFirstChild('LeftUpperArm') and character:FindFirstChild('LeftLowerArm') then
				ragdollJoint(character, character.LeftUpperArm, character.LeftLowerArm, "LeftElbow", "BallSocket")
			end
			if character:FindFirstChild('RightUpperLeg') and character:FindFirstChild('RightLowerLeg') then
				ragdollJoint(character,character.RightUpperLeg, character.RightLowerLeg, "RightKnee", "Hinge", shinProperties)
			end
			if character:FindFirstChild('RightLowerLeg') and character:FindFirstChild('RightFoot') then
				ragdollJoint(character,character.RightLowerLeg, character.RightFoot, "RightAnkle", "Hinge", footProperties)
			end
			if character:FindFirstChild('LowerTorso') and character:FindFirstChild('RightUpperLeg') then
				ragdollJoint(character,character.LowerTorso, character.RightUpperLeg, "RightHip", "BallSocket")
			end
			if character:FindFirstChild('LeftUpperLeg') and character:FindFirstChild('LeftLowerLeg') then
				ragdollJoint(character,character.LeftUpperLeg, character.LeftLowerLeg, "LeftKnee", "Hinge", shinProperties)
			end
			if character:FindFirstChild('LeftLowerLeg') and character:FindFirstChild('LeftFoot') then
				ragdollJoint(character,character.LeftLowerLeg, character.LeftFoot, "LeftAnkle", "Hinge", footProperties)
			end
			if character:FindFirstChild('LowerTorso') and character:FindFirstChild('LeftUpperLeg') then
				ragdollJoint(character,character.LowerTorso, character.LeftUpperLeg, "LeftHip", "BallSocket")
			end
			if character:FindFirstChild('UpperTorso') and character:FindFirstChild('LowerTorso') then
				ragdollJoint(character,character.LowerTorso, character.UpperTorso, "Waist", "BallSocket", {
					{"LimitsEnabled",true};
					{"UpperAngle",5};
					{"Radius",5};
				})
			end
			if character:FindFirstChild('UpperTorso') and character:FindFirstChild('Head') then
				ragdollJoint(character,character.UpperTorso, character.Head, "Neck", "Hinge", {
					{"LimitsEnabled",true};
					{"UpperAngle",50};
					{"LowerAngle",-50};
				})
			end
			local NeckA = ragdollJoint(character,character.UpperTorso, character.Head, "Neck", "Hinge", {
				{"LimitsEnabled",true};
				{"UpperAngle",50};
				{"LowerAngle",-50};
			})

			recurse(character, function(_,v)
				if v:IsA("Attachment") then
					v.Axis = Vector3.new(0, 1, 0)
					v.SecondaryAxis = Vector3.new(0, 0, 1)
					v.Rotation = Vector3.new(0, 0, 0)
					if(v.Parent == character.Head and snapped)then
						v.Orientation = V3.N(0,-90,0)
					end
				end
			end)
		end
	end)
end


function Bezier(startpos, pos2, pos3, endpos, t)
	local A = startpos:lerp(pos2, t)
	local B  = pos2:lerp(pos3, t)
	local C = pos3:lerp(endpos, t)
	local lerp1 = A:lerp(B, t)
	local lerp2 = B:lerp(C, t)
	local cubic = lerp1:lerp(lerp2, t)
	return cubic
end

function Effect(data)
	local FX = data.Effect or 'Resize-AndFade'
	local Parent = data.Parent or Effects
	local Color = data.Color or C3.N(0,0,0)
	local Size = data.Size or V3.N(1,1,1)
	local MoveDir = data.MoveDirection or nil
	local MeshData = data.Mesh or nil
	local SndData = data.Sound or nil
	local Frames = data.Frames or 45
	local Manual = data.Manual or nil
	local Material = data.Material or nil
	local CFra = data.CFrame or Torso.CFrame
	local Settings = data.FXSettings or {}
	local Snd,Prt,Msh;
	if(Manual and typeof(Manual) == 'Instance' and Manual:IsA'BasePart')then
		Prt = Manual
	else
		Prt = Part(Parent,Color,Material,Size,CFra,true,false)
	end
	if(typeof(MeshData) == 'table')then
		Msh = Mesh(Prt,MeshData.MeshType,MeshData.MeshId,MeshData.TextureId,MeshData.Scale,MeshData.Offset)
	elseif(typeof(MeshData) == 'Instance')then
		Msh = MeshData:Clone()
		Msh.Parent = Prt
	end
	if(typeof(SndData) == 'table' or typeof(SndData) == 'Instance')then
		Snd = Sound(Prt,SndData.SoundId,SndData.Pitch,SndData.Volume,false,false,true)
	end
	if(Snd)then
		repeat wait() until Snd.Playing and Snd.IsLoaded and Snd.TimeLength > 0
		Frames = Snd.TimeLength * Frame_Speed/Snd.Pitch
	end
	local MoveSpeed = nil;
	if(MoveDir)then
		MoveSpeed = (CFra.p - MoveDir).magnitude/Frames
	end
	local Inc = M.RNG()-M.RNG()
	local Thingie = 0
	local Thingie2 = M.RNG(50,100)/100

	coroutine.wrap(function()
		if(FX ~= 'Arc')then
			for i = 1, Frames do
				if(FX == 'Resize-AndFade')then
					if(not Settings.EndSize)then
						Settings.EndSize = V3.N(0,0,0)
					end
					local grow = (typeof(Settings.EndSize) == 'Vector3' and Settings.EndSize-Size or typeof(Settings.EndSize) == 'number' and V3.N(Settings.EndSize))
					if(Settings.EndIsIncrement)then
						Prt.Size = Prt.Size - Settings.EndSize					
					else
						Prt.Size = Prt.Size - grow/Frames
					end 
					Prt.Transparency = (i/Frames)
				elseif(FX == 'Resize+AndFade')then
					if(not Settings.EndSize)then
						Settings.EndSize = Size*2
					end
					local grow = (typeof(Settings.EndSize) == 'Vector3' and Settings.EndSize-Size or typeof(Settings.EndSize) == 'number' and V3.N(Settings.EndSize))
					if(Settings.EndIsIncrement)then
						Prt.Size = Prt.Size + Settings.EndSize					
					else
						Prt.Size = Prt.Size + grow/Frames
					end 
					Prt.Transparency = (i/Frames)
				elseif(FX == 'Fade')then
					Prt.Transparency = (i/Frames)
				end
				if(Settings.RandomizeCFrame)then
					Prt.CFrame = Prt.CFrame * CF.A(M.RRNG(-360,360),M.RRNG(-360,360),M.RRNG(-360,360))
				end
				if(MoveDir and MoveSpeed)then
					local Orientation = Prt.Orientation
					Prt.CFrame = CF.N(Prt.Position,MoveDir)*CF.N(0,0,-MoveSpeed)
					Prt.Orientation = Orientation
				end
				if(swait and typeof(swait) == 'function')then
					swait()
				else
					wait()
				end
			end
			Prt:destroy() 
		else
			local start,third,fourth,endP = Settings.Start,Settings.Third,Settings.Fourth,Settings.End
			if(not Settings.End and Settings.Home)then endP = Settings.Home.CFrame end
			local quarter = third or start:lerp(endP, 0.25) * CF.N(M.RNG(-25,25),M.RNG(0,25),M.RNG(-25,25))
			local threequarter = fourth or start:lerp(endP, 0.75) * CF.N(M.RNG(-25,25),M.RNG(0,25),M.RNG(-25,25))
			assert(start ~= nil,"You need to specify a start point!")
			assert(endP ~= nil,"You need to specify an end point!")
			for i = 0, 1, Settings.Speed or 0.01 do
				if(Settings.Home)then
					endP = Settings.Home.CFrame
				end
				Prt.CFrame = Bezier(start, quarter, threequarter, endP, i)
				if(swait and typeof(swait) == 'function')then
					swait()
				else
					wait()
				end
			end
			if(Settings.RemoveOnGoal)then
				Prt:destroy()
			end
		end
	end)()
	return Prt,Msh,Snd
end	


function SoulSteal(character)
	local torso = (character:FindFirstChild'Head' or character:FindFirstChild'Torso' or character:FindFirstChild'UpperTorso' or character:FindFirstChild'LowerTorso' or character:FindFirstChild'HumanoidRootPart')
	print(torso)
	if(torso and torso:IsA'BasePart')then
		local Model = Instance.new("Model",Effects)
		Model.Name = character.Name.."'s Soul"
		character:BreakJoints()
		local Soul = Part(Model,BrickColor.new'Really red','Glass',V3.N(.5,.5,.5),torso.CFrame,true,false)
		Soul.Name = 'Head'
		NewInstance("Humanoid",Model,{Health=0,MaxHealth=0})
		Effect{
			Effect="Arc",
			Manual = Soul,
			FXSettings={
				Start=torso.CFrame,
				Home = Torso,
				RemoveOnGoal = true,
			}
		}
		local lastPoint = Soul.CFrame.p
	
		for i = 0, 1, 0.01 do 
				local point = CFrame.new(lastPoint, Soul.Position) * CFrame.Angles(-math.pi/2, 0, 0)
				local mag = (lastPoint - Soul.Position).magnitude
				Effect{
					Effect = "Fade",
					CFrame = point * CF.N(0, mag/2, 0),
					Size = V3.N(.5,mag+.5,.5),
					Color = Soul.BrickColor
				}
				lastPoint = Soul.CFrame.p
			swait()
		end
		for i = 1, 5 do
			Effect{
				Effect="Fade",
				Color = BrickColor.new'Really red',
				MoveDirection = (Torso.CFrame*CFrame.new(M.RNG(-40,40),M.RNG(-40,40),M.RNG(-40,40))).p
			}	
		end
	end
end

--// Other Functions \\ --

function getRegion(point,range,ignore)
    return workspace:FindPartsInRegion3WithIgnoreList(R3.N(point-V3.N(1,1,1)*range/2,point+V3.N(1,1,1)*range/2),ignore,100)
end

function clerp(startCF,endCF,alpha)
	return startCF:lerp(endCF, alpha)
end

function GetTorso(char)
	return char:FindFirstChild'Torso' or char:FindFirstChild'UpperTorso'
end



function ShowDamage(Pos, Text, Time, Color)
	coroutine.wrap(function()
	local Rate = (1 / 30)
	local Pos = (Pos or Vector3.new(0, 0, 0))
	local Text = (Text or "")
	local Time = (Time or 2)
	local Color = (Color or Color3.new(1, 0, 1))
	local EffectPart = NewInstance("Part",Effects,{
		Material=Enum.Material.SmoothPlastic,
		RArmlectance = 0,
		Transparency = 1,
		BrickColor = BrickColor.new(Color),
		Name = "Effect",
		Size = Vector3.new(0,0,0),
		Anchored = true
	})
	local BillboardGui = NewInstance("BillboardGui",EffectPart,{
		Size = UDim2.new(1.25, 0, 1.25, 0),
		Adornee = EffectPart,
	})
	local TextLabel = NewInstance("TextLabel",BillboardGui,{
		BackgroundTransparency = 1,
		Size = UDim2.new(1, 0, 1, 0),
		Text = Text,
		Font = "Arial",
		TextColor3 = Color,
		TextStrokeColor3 = Color3.new(0,0,0),
		TextStrokeTransparency=0,
		TextScaled = true,
	})
	game.Debris:AddItem(EffectPart, (Time))
	EffectPart.Parent = game:GetService("Workspace")
	delay(0, function()
		local Frames = (Time / Rate)
		for Frame = 1, Frames do
			wait(Rate)
			local Percent = (Frame / Frames)
			EffectPart.CFrame = CFrame.new(Pos) + Vector3.new(0, Percent, 0)
			TextLabel.TextTransparency = Percent
			TextLabel.TextStrokeTransparency = Percent
		end
		if EffectPart and EffectPart.Parent then
			EffectPart:Destroy()
		end
	end) end)()
end


function DealDamage(who,minDam,maxDam,Knock,Type,critChance,critMult)
	if(who)then
		print(minDam, maxDam, Knock, Type, critChance, critMult)
	end
end

function AOEDamage(where,range,minDam,maxDam,Knock,Type)
print(where,range,minDam,maxDam,Knock,Type)
end

function AOEFunction(where,range,callback)
	for _,v in next, getRegion(where,range,{Char}) do
		if(v.Parent and v.Parent:FindFirstChildOfClass'Humanoid')then
			callback(v.Parent)
		end
	end
end

function ClosestHumanoid(pos,range)
	local mag,closest = math.huge;
	for _,v in next, getRegion(pos,range or 10,{Char}) do
		local hum = (v.Parent and v.Parent:FindFirstChildOfClass'Humanoid')
		if((v.CFrame.p-pos).magnitude < mag and hum and closest ~= hum and hum.Health > 0)then
			mag = (v.CFrame.p-pos).magnitude
			closest = hum
		end
	end
	return closest,(closest and GetTorso(closest.Parent) or nil)
end

function AOEHeal(where,range,amount)
	local healed = {}
	for _,v in next, getRegion(where,range,{Char}) do
		local hum = (v.Parent and v.Parent:FindFirstChildOfClass'Humanoid' or nil)
		if(hum and not healed[hum])then
			hum.Health = hum.Health + amount
			if(v.Parent:FindFirstChild'Head' and hum.Health > 0)then
				ShowDamage((v.Parent.Head.CFrame * CF.N(0, 0, (v.Parent.Head.Size.Z / 2)).p+V3.N(0,1.5,0)), "+"..amount, 1.5, BrickColor.new'Really red'.Color)
			end
		end
	end
end
--// Attack Function \\--

function Equip_Sawblade()
	for i = 1, 5 do
		Effect{
			Effect='Resize+AndFade',
			Color = BrickColor.new'Really red',
			Material = Enum.Material.Neon,
			Size=V3.N(3.5,3.5,3.5),
			CFrame=RArm.CFrame*CF.N(0,-1,0)*CF.A(M.RRNG(0,180),M.RRNG(0,180),M.RRNG(0,180)),
			FXSettings={
				EndSize=V3.N(.05,.05,.05),
				EndIsIncrement=true,
				
			}
		}
	end
	local prt = Part(Char,BrickColor.new'Really red',Enum.Material.SmoothPlastic,V3.N(3.42, 3.42, 0.05),CF.N(),false,false)
	prt.Transparency = .5
	local mesh = Mesh(prt,Enum.MeshType.FileMesh,"rbxassetid://74322089","",V3.N(3,3,3),V3.N())
	local weld = NewInstance("Weld",Char,{Part0=RArm,Part1=prt,C0=CF.N(0,-1.25,0)}) 
	return prt,weld
end

function The_Necc()
	local humanoid, torso = ClosestHumanoid(Torso.CFrame.p,5)
	if(torso)then
		local who = torso.Parent
		Attack = true
		NeutralAnims = false
		who.Parent = Char
		local oRoot
		pcall(function() oRoot = who.HumanoidRootPart; oRoot.Parent = nil end)
		local gWeld = NewInstance("Weld",Char,{Part0=Root,Part1=torso,C0=CF.N(0,0,-1.25)})
		for i = 0, 4, 0.1 do
			swait()
			humanoid.PlatformStand = true
			local Alpha = .15
			RJ.C0 = clerp(RJ.C0,CFrame.new(7.78455425e-13, 0.00629367586, -2.39849396e-06, 0.99999243, 1.23691279e-10, 0, 1.90985006e-11, 0.99998045, -0.00628617778, 9.31322575e-10, 0.00628614007, 0.999973059),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.496486545, -0.990821958, 0.021611277, 0.999870956, 1.90985006e-11, 0.0156118907, -9.81391422e-05, 0.99998045, 0.00628537685, -0.0156115862, -0.00628617778, 0.999851584),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.498530418, -0.990985394, 0.0154574998, 0.999870956, 1.90985006e-11, 0.0156118907, -9.81391422e-05, 0.99998045, 0.00628537685, -0.0156115862, -0.00628617778, 0.999851584),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.0486517, 0.929213107, -0.824554026, 0.712753832, -0.694763601, -0.0963225588, 0.0692147464, 0.206324935, -0.976032555, 0.697985768, 0.689004064, 0.195146814),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(0.386394978, 1.64370263, -1.084023, -0.617445648, -0.751786709, -0.231452331, -0.0510570146, 0.331923157, -0.941923738, 0.784950197, -0.569769561, -0.243328467),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(8.16636839e-06, 1.49895489, -0.0144007429, 0.99999243, 3.67523171e-07, -1.61118805e-07, -3.56405508e-07, 0.997965038, 0.0637686625, 1.8440187e-07, -0.0637682825, 0.997957468),Alpha)
		end		
		gWeld:destroy()
		if(who:FindFirstChild'Head')then
			local s = Sound(who:FindFirstChild'Head',1093102664,1,2,false,false,false)
			s:Play()
			s.Ended:connect(function() s:Destroy() end)
		end
		who.Parent = workspace
		humanoid.Health = 0
		Ragdoll(who,false,true)
		for i = 0, 1.5, 0.1 do
			swait()
			humanoid.PlatformStand = true
			local Alpha = .3
			RJ.C0 = clerp(RJ.C0,CFrame.new(7.78455425e-13, 0.00629367586, -2.39849396e-06, 0.99999243, 1.23691279e-10, 0, 1.90985006e-11, 0.99998045, -0.00628617778, 9.31322575e-10, 0.00628614007, 0.999973059),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.496486545, -0.990821958, 0.021611277, 0.999870956, 1.90985006e-11, 0.0156118907, -9.81391422e-05, 0.99998045, 0.00628537685, -0.0156115862, -0.00628617778, 0.999851584),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.498530418, -0.990985394, 0.0154574998, 0.999870956, 1.90985006e-11, 0.0156118907, -9.81391422e-05, 0.99998045, 0.00628537685, -0.0156115862, -0.00628617778, 0.999851584),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.47842193, 0.485131323, -0.0262347199, 0.0664671659, 0.993123412, -0.0963359103, -0.201927185, -0.0811635256, -0.976031899, -0.977139056, 0.0843269154, 0.195143938),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(2.33067179, 0.249403879, 0.270489573, 0.171869993, 0.978404701, -0.114792682, 0.105083257, -0.134070903, -0.985384524, -0.979495406, 0.157295257, -0.125856698),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(8.16636839e-06, 1.49895489, -0.0144007429, 0.99999243, 3.67523171e-07, -1.61118805e-07, -3.56405508e-07, 0.997965038, 0.0637686625, 1.8440187e-07, -0.0637682825, 0.997957468),Alpha)
		end
		Attack = false
		NeutralAnims = true
	end
end

function Hands_Off()
	local humanoid, torso = ClosestHumanoid(Torso.CFrame.p,5)
	
	if(torso)then
		local who = torso.Parent
		local doAttack = false
		Instance.AllChildren(who,function(v)
			if(v.Name:lower():find"arm")then
				doAttack = true
			end
		end, true)
		if(not doAttack)then return end
		Hum.WalkSpeed = 0
		Hum.JumpPower = 0
		Attack = true
		NeutralAnims = false
		who.Parent = Char
		local oRoot
		pcall(function() oRoot = who.HumanoidRootPart; oRoot.Parent = nil end)
		local gWeld = NewInstance("Weld",Char,{Part0=Root,Part1=torso,C0=CF.N(0,0,-1.25)})
		for i = 0, 4, 0.1 do
			swait()
			humanoid.PlatformStand = true
			local Alpha = .15
			RJ.C0 = clerp(RJ.C0,CFrame.new(3.20564755e-13, 0.00629412755, 1.41908095e-06, 0.999999225, 5.09317033e-11, 0, -4.38656264e-11, 0.999980271, -0.00628618058, 0, 0.00628617639, 0.999979496),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.496493757, -0.990819633, 0.021611426, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.498533875, -0.990984261, 0.0154613676, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.42285931, 0.338565946, -0.110074639, 0.983876407, 0.1786367, 0.00868223887, -0.0932332501, 0.553717494, -0.827468753, -0.152623802, 0.813317537, 0.561444461),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.374735, 0.282860518, -0.133752465, 0.973415911, -0.228878334, 0.00868532527, 0.135509402, 0.544919252, -0.827466309, 0.184656292, 0.806645751, 0.561448157),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(8.16625652e-06, 1.49895275, -0.014400661, 0.999999225, 3.67464963e-07, -1.62050128e-07, -3.56478267e-07, 0.997964799, 0.0637686923, 1.8440187e-07, -0.0637686551, 0.997963905),Alpha)
		end
		local RABC = (who:FindFirstChild'Right Arm' or who:FindFirstChild'RightUpperArm' or who:FindFirstChild'RightLowerArm' or who:FindFirstChild'RightHand' or IN("Part")).BrickColor
		local LABC = (who:FindFirstChild'Left Arm' or who:FindFirstChild'LeftUpperArm' or who:FindFirstChild'LeftLowerArm' or who:FindFirstChild'LeftHand' or IN("Part")).BrickColor
		Sound(torso,1093102664,.85,5,false,true,true)
		Sound(torso,429400881,1,1,false,true,true)
		FRArm = NewInstance('Part',Effects,{Size=V3.N(1,2,1),BrickColor=RABC,Material='Plastic',CanCollide=false,Anchored=false,Locked=true})
		Mesh(FRArm,Enum.MeshType.FileMesh,"rbxasset://fonts/rightarm.mesh","",V3.N(1,1,1),V3.N())
		FLArm = NewInstance('Part',Effects,{Size=V3.N(1,2,1),BrickColor=LABC,Material='Plastic',CanCollide=false,Anchored=false,Locked=true})
		Mesh(FLArm,Enum.MeshType.FileMesh,"rbxasset://fonts/leftarm.mesh","",V3.N(1,1,1),V3.N())		
		FRArmW = NewInstance('Weld',FRArm,{Part0=RArm,Part1=FRArm,C0=CF.N(0,-1,0)*CF.A(M.R(90),0,0)})
		FLArmW = NewInstance('Weld',FLArm,{Part0=LArm,Part1=FLArm,C0=CF.N(0,-1,0)*CF.A(M.R(90),0,0)})
		Instance.AllChildren(who,function(v)
			if(v.Name:lower():find"arm" or v.Name:lower():find"hand")then
				v:destroy()
			end
		end, true)
		if(not VoidSB)then
			coroutine.wrap(function()
				repeat swait() 
				BloodDrop(torso.CFrame * CF.N(-.5,.5,0).p,torso.CFrame * CF.N(-1,.5,0).p,15)
				BloodDrop(torso.CFrame * CF.N(.5,.5,0).p,torso.CFrame * CF.N(1,.5,0).p,15)
				humanoid.Health = humanoid.Health - 0.5 until not who or not who.Parent or not humanoid.Parent
				humanoid.Health = 0
			end)()
		else
			coroutine.wrap(function()
				repeat swait()  humanoid.Health = humanoid.Health - 0.5 until not who or not who.Parent or not humanoid.Parent
				humanoid.Health = 0
			end)()

			local prt1,prtcl1 = Blood4(V3.N(.5,.5,.5),torso.CFrame)
			local prt2,prtcl2 = Blood4(V3.N(.5,.5,.5),torso.CFrame)
			prt1.Parent = torso;
			prt2.Parent = torso;
			local prt1W = NewInstance('Weld',torso,{Part0=prt1,Part1=torso,C0=CF.N(0,-.5,-1.25)*CF.A(0,M.R(90),0)})
			local prt2W = NewInstance('Weld',torso,{Part0=prt2,Part1=torso,C0=CF.N(0,-.5,-1.25)*CF.A(0,M.R(-90),0)})
		end
		
		humanoid.Died:connect(function()
			Ragdoll(who)
		end)
		who.Parent = workspace

		local prt1,prtcl1 = Blood4(V3.N(.5,.5,.5),torso.CFrame)
		local prt2,prtcl2 = Blood4(V3.N(.5,.5,.5),torso.CFrame)
		prt1.Parent = FRArm;
		prt2.Parent = FLArm;
		local prt1W = NewInstance('Weld',FRArm,{Part0=prt1,Part1=FRArm,C0=CF.N(0,0,0)*CF.A(0,M.R(90),0)})
		local prt2W = NewInstance('Weld',FLArm,{Part0=prt2,Part1=FLArm,C0=CF.N(0,0,0)*CF.A(0,M.R(-90),0)})
		gWeld:destroy()
		humanoid.PlatformStand = false
		if(oRoot)then
			oRoot.Parent = who
			if(who:FindFirstChild('RootJoint',true))then
				oRoot.RootJoint.Part0 = oRoot
				oRoot.RootJoint.Part1 = torso
			else
				humanoid:BuildRigFromAttachments()
			end
		end
		
		
		for i = 0, 3, 0.1 do
			swait()
			local Alpha = .15
			RJ.C0 = clerp(RJ.C0,CFrame.new(3.20564755e-13, 0.00629412755, 1.41908095e-06, 0.999999225, 5.09317033e-11, 0, -4.38656264e-11, 0.999980271, -0.00628618058, 0, 0.00628617639, 0.999979496),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.496493757, -0.990819633, 0.021611426, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.498533875, -0.990984261, 0.0154613676, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.25778806, 0.320386261, -0.139421374, 0.690939784, 0.722859621, 0.00868486147, -0.400907725, 0.393146276, -0.827471495, -0.601560116, 0.568251252, 0.561440408),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.39739037, 0.354236364, -0.0289047062, 0.709462166, -0.704689503, 0.00868486147, 0.400770277, 0.393286407, -0.827471495, 0.579694867, 0.59054029, 0.561440408),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(8.16625652e-06, 1.49895275, -0.014400661, 0.999999225, 3.67464963e-07, -1.62050128e-07, -3.56478267e-07, 0.997964799, 0.0637686923, 1.8440187e-07, -0.0637686551, 0.997963905),Alpha)
		end
		Hum.WalkSpeed = 16
		Hum.JumpPower = 50
		Attack = false
		NeutralAnims = true
	end
end
function ScrewMe()
	Attack = true
	NeutralAnims = false
	for i = 0, 2, 0.1 do
		swait()
		local Alpha = .15
		RJ.C0 = clerp(RJ.C0,CFrame.new(-0.000601041073, 0.0062919003, -0.000300966523, 0.994017541, 0.000686608837, 0.109214716, 0, 0.99998033, -0.00628665462, -0.109216876, 0.00624904549, 0.993997931),Alpha)
		LH.C0 = clerp(LH.C0,CFrame.new(-0.502559602, -0.990627766, 0.0518152229, 0.995601892, 0, -0.0936849937, 0.000588965253, 0.99998033, 0.00625900552, 0.0936831385, -0.00628665462, 0.995582223),Alpha)
		RH.C0 = clerp(RH.C0,CFrame.new(0.501642942, -0.991074204, 0.000842738897, 0.995601892, 0, -0.0936849937, 0.000588965253, 0.99998033, 0.00625900552, 0.0936831385, -0.00628665462, 0.995582223),Alpha)
		LS.C0 = clerp(LS.C0,CFrame.new(-1.12979531, 0.241689205, 0.149894863, 0.813591897, -0.571708977, 0.105910838, 0.505802035, 0.785755217, 0.356024235, -0.286762208, -0.236088455, 0.928455591),Alpha)
		RS.C0 = clerp(RS.C0,CFrame.new(1.41494429, 0.493437499, 0.00856034085, 0.986078084, -0.165549055, 0.0156079903, 0.165468931, 0.986195028, 0.00630042888, -0.0164355561, -0.0036300756, 0.99985832),Alpha)
		NK.C0 = clerp(NK.C0,CFrame.new(-0.272200465, 1.60343766, -0.0909831151, -0.271778286, -0.29597038, 0.915717363, -0.178016067, 0.950573504, 0.254402429, -0.945752025, -0.0938713551, -0.311032623),Alpha)
	end
	local screwdriver = Part(Char,BrickColor.new'Really black',Enum.Material.SmoothPlastic,V3.N(2.158,0.29,0.312),RArm.CFrame,false,false)
	local driverMesh = Mesh(screwdriver,Enum.MeshType.FileMesh,"rbxassetid://70265804","rbxassetid://70265794",V3.N(1,.5,.5),V3.N())
	local driverWeld = NewInstance("Weld",Char,{Part0=LArm,Part1=screwdriver,C0=CF.N(0,-1.15,0)})
	for i = 1, 3 do
		for i = 0, 2, 0.1 do
			swait()
			local Alpha = .15
			RJ.C0 = clerp(RJ.C0,CFrame.new(-0.000597249367, 0.00629166188, -0.000301384629, 0.994017541, 0.000686608837, 0.109214716, 0, 0.99998033, -0.00628665462, -0.109216876, 0.00624904549, 0.993997931),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.502559602, -0.990627766, 0.0518152229, 0.995601892, 0, -0.0936849937, 0.000588965253, 0.99998033, 0.00625900552, 0.0936831385, -0.00628665462, 0.995582223),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.501639128, -0.991074204, 0.000842381269, 0.995601892, 0, -0.0936849937, 0.000588965253, 0.99998033, 0.00625900552, 0.0936831385, -0.00628665462, 0.995582223),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-0.971063137, 0.544531465, -0.856619298, 0.824469268, -0.565411985, 0.0236563906, 0.239681676, 0.311018854, -0.919684827, 0.512643158, 0.763921857, 0.391944379),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.36865759, 0.434063494, -0.243990004, 0.943695724, 0.286517411, 0.165366411, 0.0948955566, 0.244413704, -0.965016603, -0.316911817, 0.926374555, 0.203462943),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(0.309692234, 1.56599295, -0.184076563, 0.752268493, 0.275064707, -0.598691583, 0.0132474303, 0.902184188, 0.431147963, 0.658723474, -0.332270145, 0.675040722),Alpha)
			driverWeld.C0 = clerp(driverWeld.C0,CFrame.new(0.754458785, -0.945940197, 0.0140114268, -0.867547691, -0.497354031, 8.15391541e-05, -7.91847706e-05, 0.00030207634, 1, -0.49735406, 0.867547691, -0.000301415101),Alpha)
		end
		for i = 0, 2, 0.1 do
			swait()
			local Alpha = .15
			RJ.C0 = clerp(RJ.C0,CFrame.new(-0.000597249367, 0.00629166188, -0.000301384629, 0.994017541, 0.000686608837, 0.109214716, 0, 0.99998033, -0.00628665462, -0.109216876, 0.00624904549, 0.993997931),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.502559602, -0.990627766, 0.0518152229, 0.995601892, 0, -0.0936849937, 0.000588965253, 0.99998033, 0.00625900552, 0.0936831385, -0.00628665462, 0.995582223),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.501639128, -0.991074204, 0.000842381269, 0.995601892, 0, -0.0936849937, 0.000588965253, 0.99998033, 0.00625900552, 0.0936831385, -0.00628665462, 0.995582223),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-0.952282608, 0.388567954, -0.813911676, 0.824469686, -0.527844906, 0.204033226, 0.23967658, -0.000909555703, -0.970852435, 0.512645066, 0.849340379, 0.12576215),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.36865759, 0.434063494, -0.243990004, 0.943695724, 0.286517411, 0.165366411, 0.0948955566, 0.244413704, -0.965016603, -0.316911817, 0.926374555, 0.203462943),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(0.309692234, 1.56599295, -0.184076563, 0.752268493, 0.275064707, -0.598691583, 0.0132474303, 0.902184188, 0.431147963, 0.658723474, -0.332270145, 0.675040722),Alpha)
			driverWeld.C0 = clerp(driverWeld.C0,CFrame.new(0.75445646, -0.891306043, 0.317142308, -0.867489815, -0.183382571, -0.462420344, -0.159916192, -0.777427077, 0.608304381, -0.471050501, 0.601646185, 0.645084083),Alpha)
		end
	end
	for i = 0, 2, 0.1 do
		swait()
		local Alpha = .15
		RJ.C0 = clerp(RJ.C0,CFrame.new(-0.000601041073, 0.0062919003, -0.000300966523, 0.994017541, 0.000686608837, 0.109214716, 0, 0.99998033, -0.00628665462, -0.109216876, 0.00624904549, 0.993997931),Alpha)
		LH.C0 = clerp(LH.C0,CFrame.new(-0.502559602, -0.990627766, 0.0518152229, 0.995601892, 0, -0.0936849937, 0.000588965253, 0.99998033, 0.00625900552, 0.0936831385, -0.00628665462, 0.995582223),Alpha)
		RH.C0 = clerp(RH.C0,CFrame.new(0.501642942, -0.991074204, 0.000842738897, 0.995601892, 0, -0.0936849937, 0.000588965253, 0.99998033, 0.00625900552, 0.0936831385, -0.00628665462, 0.995582223),Alpha)
		LS.C0 = clerp(LS.C0,CFrame.new(-1.12979531, 0.241689205, 0.149894863, 0.813591897, -0.571708977, 0.105910838, 0.505802035, 0.785755217, 0.356024235, -0.286762208, -0.236088455, 0.928455591),Alpha)
		RS.C0 = clerp(RS.C0,CFrame.new(1.41494429, 0.493437499, 0.00856034085, 0.986078084, -0.165549055, 0.0156079903, 0.165468931, 0.986195028, 0.00630042888, -0.0164355561, -0.0036300756, 0.99985832),Alpha)
		NK.C0 = clerp(NK.C0,CFrame.new(-0.272200465, 1.60343766, -0.0909831151, -0.271778286, -0.29597038, 0.915717363, -0.178016067, 0.950573504, 0.254402429, -0.945752025, -0.0938713551, -0.311032623),Alpha)
	end
	screwdriver:destroy()
	Attack = false
	NeutralAnims = true
end
function SliceYou()
	Attack = true
	NeutralAnims = false
	local saw,weld = Equip_Sawblade()
	for i = 0, 2, 0.1 do
		swait()
		local Alpha = .15
		RJ.C0 = clerp(RJ.C0,CFrame.new(0.0029785831, 0.00629174896, 0.00529580005, 0.517270923, -0.00537902303, -0.855804324, 0, 0.99998033, -0.00628521619, 0.855821192, 0.00325116003, 0.517260671),Alpha)
		LH.C0 = clerp(LH.C0,CFrame.new(-0.524694026, -0.992068648, -0.177415758, 0.503846943, 0, 0.863792896, -0.00542912632, 0.99998033, 0.00316678779, -0.863775849, -0.00628521619, 0.503836989),Alpha)
		RH.C0 = clerp(RH.C0,CFrame.new(0.863649905, -0.990154982, 0.147100359, 0.503846943, 0, 0.863792896, -0.00542912632, 0.99998033, 0.00316678779, -0.863775849, -0.00628521619, 0.503836989),Alpha)
		LS.C0 = clerp(LS.C0,CFrame.new(-1.15776694, 0.555799365, -0.115642846, -0.0494773015, 0.838752568, -0.54226011, -0.986161113, -0.127040714, -0.106522933, -0.15823549, 0.529485285, 0.833430767),Alpha)
		RS.C0 = clerp(RS.C0,CFrame.new(1.41811252, 0.715449214, 0.00713690743, 0.924166977, -0.38166979, 0.0156050026, 0.381617904, 0.924298882, 0.00629791059, -0.0168274939, 0.00013487041, 0.999858379),Alpha)
		NK.C0 = clerp(NK.C0,CFrame.new(-0.0103359073, 1.49896884, -0.0121970959, 0.517271042, -0.0492044352, 0.854405463, -0.00537938019, 0.998139322, 0.0607386976, -0.855804205, -0.0360145383, 0.516043782),Alpha)
	end
	for i = 0, 3, 0.1 do
		swait()
		local Alpha = .3
		RJ.C0 = clerp(RJ.C0,CFrame.new(0.0750166476, 0.00629172707, 0.115993313, -0.407934308, 0.00573777966, 0.912992895, 0, 0.99998033, -0.00628445856, -0.913010895, -0.00256364676, -0.407926261),Alpha)
		LH.C0 = clerp(LH.C0,CFrame.new(-0.702545583, -0.991440296, -0.0774632096, -0.393630832, 0, -0.919268608, 0.00577710615, 0.99998033, -0.00247375714, 0.919250488, -0.00628445856, -0.393623054),Alpha)
		RH.C0 = clerp(RH.C0,CFrame.new(0.572302818, -0.991491556, -0.0655612499, -0.393630832, 0, -0.919268608, 0.00577710615, 0.99998033, -0.00247375714, 0.919250488, -0.00628445856, -0.393623054),Alpha)
		LS.C0 = clerp(LS.C0,CFrame.new(-1.42436278, 0.674626052, -0.273927838, 0.816972971, 0.196224883, -0.54226476, -0.298526257, 0.948434591, -0.106555678, 0.493393689, 0.248933315, 0.833423615),Alpha)
		RS.C0 = clerp(RS.C0,CFrame.new(1.39865923, 0.565930247, 0.00839936361, -0.125458091, -0.991975904, 0.0156244934, 0.992089748, -0.125373363, 0.00629395852, -0.00428455323, 0.0162905455, 0.99985826),Alpha)
		NK.C0 = clerp(NK.C0,CFrame.new(0.141048998, 1.4988662, -0.0285577606, -0.407934487, 0.0524925366, -0.911500514, 0.0057374211, 0.998473644, 0.054933507, 0.912992835, 0.0171796028, -0.40761295),Alpha)
	end
	local sound = Sound(Torso,367720620,false,false,false)
	sound:Play()
	for i = 0, 6, .1 do
		weld.C0 = weld.C0:lerp(weld.C0 * CF.A(0,0,M.R(25)),.3)
		swait()
	end
	for i = 0, 2, .1 do
		weld.C0 = weld.C0:lerp(weld.C0 * CF.A(0,0,M.R(5)),.3)
		swait()
	end
	sound:Play()
	for i = 0, 1, .1 do
		weld.C0 = weld.C0:lerp(weld.C0 * CF.A(0,0,M.R(25)),.3)
		swait()
	end
	sound:Play()
	for i = 0, 5, .1 do
		weld.C0 = weld.C0:lerp(weld.C0 * CF.A(0,0,M.R(55)),.3)
		swait()
	end
	for i = 1, 5 do
		Effect{
			Effect='Resize+AndFade',
			Color = BrickColor.new'Really red',
			Material = Enum.Material.Neon,
			Size=V3.N(3.5,3.5,3.5),
			CFrame=saw.CFrame*CF.A(M.RRNG(0,180),M.RRNG(0,180),M.RRNG(0,180)),
			FXSettings={
				EndSize=V3.N(.05,.05,.05),
				EndIsIncrement=true,
				
			}
		}
	end
	saw:destroy()
	Attack = false
	NeutralAnims = true
end
function Taunt()
	local tauntFuncs = {SliceYou,ScrewMe}
	local taunt = tauntFuncs[M.RNG(1,#tauntFuncs)]
	taunt()
end
function Aids()
	Music.Playing = false
	local DabSounds = {420701444,420701460,420701487}
	local DabSnd = Sound(Torso,DabSounds[M.RNG(1,#DabSounds)],1,5,false,false,false)
	repeat swait() until DabSnd.IsLoaded
	DabSnd:Play()
	DabSnd.Ended:connect(function()DabSnd:destroy()end)
	Attack = true
	NeutralAnims = false
	local a = 0
	for i = 0, DabSnd.TimeLength * Frame_Speed/DabSnd.Pitch do
		a = a + 1
		swait()
		local Alpha = .3
		RJ.C0 = clerp(RJ.C0,CFrame.new(0.0561925545, 0.006292901+.2*M.C(a/16), -0.00967639871, 0.961586297, 0.00172359415, 0.274496257, 0, 0.99998033, -0.00627899449, -0.274501652, 0.00603779452, 0.961567342),Alpha)
		LH.C0 = clerp(LH.C0,CFrame.new(-0.593769729, -0.99042201-.2*M.C(a/16), 0.0849506408, 0.965754986, 0, -0.259456009, 0.00162912265, 0.99998033, 0.00606396981, 0.259450912, -0.00627899449, 0.965735972),Alpha)
		RH.C0 = clerp(RH.C0,CFrame.new(0.468464553, -0.991293669-.2*M.C(a/16), -0.0339690484, 0.965754986, 0, -0.259456009, 0.00162912265, 0.99998033, 0.00606396981, 0.259450912, -0.00627899449, 0.965735972),Alpha)
		LS.C0 = clerp(LS.C0,CFrame.new(-1.15301001, 0.367895871, -0.145940349+.2*M.C(a/16), 0.375669211, 0.913452208, -0.156454355, -0.926753879, 0.37026915, -0.0634673014, -4.41223383e-05, 0.168837398, 0.985643983),Alpha)
		RS.C0 = clerp(RS.C0,CFrame.new(0.998128295, 0.633566499, -0.753388047+.2*M.C(a/16), 0.594308019, 0.804203451, 0.00742085278, -0.383671522, 0.29161948, -0.876215935, -0.706819832, 0.517895043, 0.481861711),Alpha)
		NK.C0 = clerp(NK.C0,CFrame.new(0.207638323, 1.47957158, -0.302699238, 0.745848298, 0.476892024, -0.465063959, 0.0606503561, 0.646653771, 0.760368645, 0.663349032, -0.595326006, 0.453382045),Alpha)
	end
	Music.Playing = true
	Attack = false
	NeutralAnims = true
end

function OnceWas(who)
	for _,v in next, who:children() do
		if(v:IsA'BasePart')then
			Effect{
				Parent=Effects, 
				Effect='Fade',
				Color = BrickColor.new'Crimson',
				Material = Enum.Material.Glass,
				Size = v.Size,
				CFrame=v.CFrame,
				Frames = 90,
			}
		end
	end
end

function Teleport(where)
	OnceWas(Char)
	Sound(Root,235097614,3,1,false,true,true)
	Sound(Root,75356820,2,1,false,true,true)
	Root.CFrame = CF.N(where.p)
	OnceWas(Char)
end

function Dash()
	Attack = true
	Sound(Root,235097614,3,1,false,true,true)
	Sound(Root,75356820,2,1,false,true,true)
	for i = 1, 5 do
		OnceWas(Char)
		Root.CFrame = Root.CFrame*CF.N(0,0,-5)
		swait()
	end
	Attack = false
end

function Shriek()
	Attack = true
	NeutralAnims = false
	local scream = Sound(Head,198165368,.5,10,false,false,false)
	local i = 0
	scream:Play()
	while scream.Playing do
		i = i + 1
		swait()
		coroutine.wrap(function()
			AOEFunction(Head.Position,30,function(who)
				local h,hd = who:FindFirstChildOfClass'Humanoid',who:FindFirstChild'Head'
				if(h and hd and h.Health > 0)then
					Sound(hd,429400881,1,1,false,true,true)
					
					workspace.non.FPart.Position = who["Torso"].Position	
				end
			end)
		end)()
		local Alpha = .15
		RJ.C0 = clerp(RJ.C0,CFrame.new(0.00956845004, -0.141102523, 0.612865508, 0.999947488, 0.00962571148, -0.00340035092, -0.00964800082, 0.782201111, -0.622951329, -0.00333659165, 0.622951448, 0.782252967),Alpha)
		LH.C0 = clerp(LH.C0,CFrame.new(-0.495904773, -1.0368886, 0.0598222613, 0.999878109, -0.00964800082, 0.012275002, -0.000100981888, 0.782201111, 0.623026073, -0.0156124765, -0.622951329, 0.78210485),Alpha)
		RH.C0 = clerp(RH.C0,CFrame.new(0.499093086, -1.03124118, 0.0517056584, 0.999878109, -0.00964800082, 0.012275002, -0.000100981888, 0.782201111, 0.623026073, -0.0156124765, -0.622951329, 0.78210485),Alpha)
		LS.C0 = clerp(LS.C0,CFrame.new(-1.23829794, 0.600065649, 0.16030249, -0.8319574, 0.546545088, -0.0955789387, 0.0976095572, -0.0254041255, -0.994900525, -0.54618609, -0.837044299, -0.0322128981),Alpha)
		RS.C0 = clerp(RS.C0,CFrame.new(1.40538526, 0.413302839, 0.119919479, 0.97065413, -0.226111293, -0.0818808898, 0.0516543165, -0.13650623, 0.989291787, -0.23486729, -0.96448946, -0.120820649),Alpha)
		NK.C0 = clerp(NK.C0,CFrame.new(3.62367791e-06, 1.56057274, 0.233575165, 1, 3.8058497e-06, -3.58493999e-05, -1.91188519e-05, 0.899042785, -0.437860936, 3.05641443e-05, 0.437861085, 0.899042606),Alpha)
	end
	Attack = false
	NeutralAnims = true
end

function SawMeDaddy()
	local humanoid, torso = ClosestHumanoid(Torso.CFrame.p,5)
	if(torso)then
		Attack = true
		NeutralAnims = false
		local who = torso.Parent
		who.Parent = Char
		Hum.WalkSpeed = 0
		Hum.JumpPower = 0
		humanoid.WalkSpeed = 0
		humanoid.JumpPower = 0
		local saw,weld = Equip_Sawblade()
		local gWeld = NewInstance("Weld",Char,{Part0=Root,Part1=torso,C0=CF.N(0,0,-3)*CF.A(0,M.R(180),0)})
		for i = 0, 6, 0.1 do
			swait()
			weld.C0 = weld.C0:lerp(weld.C0 * CF.A(0,0,M.R(5)),.3)
			local Alpha = .15
			RJ.C0 = clerp(RJ.C0,CFrame.new(-0.00836368278, 0.00629167072, 0.00190571044, 0.0349976346, 0.00628316449, 0.99936235, 0, 0.99998033, -0.00628704997, -0.999382019, 0.000220031856, 0.0349969491),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.503456116, -0.990501761, 0.0718512386, 0.0505957417, 0, -0.998714209, 0.00627896562, 0.99998033, 0.00031809794, 0.998694539, -0.00628704997, 0.0505947471),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.539414704, -0.991044283, 0.00562152406, 0.0505957417, 0, -0.998714209, 0.00627896562, 0.99998033, 0.00031809794, 0.998694539, -0.00628704997, 0.0505947471),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.40707266, 0.497466505, -0.00446076319, 0.980866492, 0.19405432, 0.0156163573, -0.19417055, 0.980947733, 0.00629086327, -0.0140980631, -0.00920273364, 0.999858439),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.31421685, 0.81056267, 0.00814598706, -0.489612877, -0.871799946, 0.0156333037, 0.871937394, -0.489577413, 0.00628277427, 0.00217639096, 0.0167073887, 0.999858201),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(0.00717293471, 1.49903798, -0.00130830682, 0.0349974521, 0.0574585311, -0.997728944, 0.00628280686, 0.998313606, 0.057712581, 0.99936235, -0.00828839932, 0.0345774256),Alpha)
		end
		Sound(Torso,367720620,1,1,false,true,true)
		coroutine.wrap(function()
			repeat swait()
				weld.C0 = weld.C0:lerp(weld.C0 * CF.A(0,0,M.R(45)),.3)
			until not saw.Parent
		end)()
		swait(60)
		local slicing = Sound(saw,1013673726,1,1,true,false,true)
		Sound(torso,429400881,1,1,false,true,true)
		local prt1,prtcl1 = Blood4(V3.N(.5,.5,.5),torso.CFrame)
		prt1.Parent = torso;
		local prt1W = NewInstance('Weld',torso,{Part0=prt1,Part1=torso,C0=CF.A(0,M.R(180),0)})
		for i = 0, .3, 0.001 do
			swait()
			
			humanoid.Health = humanoid.Health - .5
			if(humanoid.Health <= 0)then
				gWeld:destroy()
				Sound(torso,429400881,1,1,false,true,true)
				break
			end
			local Alpha = i
			RJ.C0 = clerp(RJ.C0,CFrame.new(-0.00836368278, 0.00629167072, 0.00190571044, 0.0349976346, 0.00628316449, 0.99936235, 0, 0.99998033, -0.00628704997, -0.999382019, 0.000220031856, 0.0349969491),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.503456116, -0.990501761, 0.0718512386, 0.0505957417, 0, -0.998714209, 0.00627896562, 0.99998033, 0.00031809794, 0.998694539, -0.00628704997, 0.0505947471),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.539414704, -0.991044283, 0.00562152406, 0.0505957417, 0, -0.998714209, 0.00627896562, 0.99998033, 0.00031809794, 0.998694539, -0.00628704997, 0.0505947471),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.40707266, 0.497466505, -0.00446076319, 0.980866492, 0.19405432, 0.0156163573, -0.19417055, 0.980947733, 0.00629086327, -0.0140980631, -0.00920273364, 0.999858439),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.18219912, 0.268655062, 0.0136158429, 0.6882689, -0.725287437, 0.0156234093, 0.725293934, 0.688410699, 0.00629597344, -0.0153217092, 0.00699824095, 0.99985826),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(0.00717293471, 1.49903798, -0.00130830682, 0.0349974521, 0.0574585311, -0.997728944, 0.00628280686, 0.998313606, 0.057712581, 0.99936235, -0.00828839932, 0.0345774256),Alpha)
		end
		humanoid.Health = 0
		who.Parent = workspace
		Ragdoll(who)
		slicing:destroy()
		for i = 1, 5 do
			Effect{
				Effect='Resize+AndFade',
				Color = BrickColor.new'Really red',
				Material = Enum.Material.Neon,
				Size=V3.N(3.5,3.5,3.5),
				CFrame=saw.CFrame*CF.A(M.RRNG(0,180),M.RRNG(0,180),M.RRNG(0,180)),
				FXSettings={
					EndSize=V3.N(.05,.05,.05),
					EndIsIncrement=true,
					
				}
			}
		end
		Hum.WalkSpeed = 16
		Hum.JumpPower = 50
		saw:destroy()
		Attack = false
		NeutralAnims = true
	end
end
function The_End()
	local humanoid, torso = ClosestHumanoid(Torso.CFrame.p,5)
	
	if(torso)then
		Attack = true
		NeutralAnims = false
		local who = torso.Parent
		Hum.WalkSpeed = 0
		Hum.JumpPower = 0
		humanoid.WalkSpeed = 0
		humanoid.JumpPower = 0
		who.Parent = Char
		pcall(function() who.HumanoidRootPart:destroy() end)
		local gWeld = NewInstance("Weld",Char,{Part0=Root,Part1=torso,C0=CF.N(0,0,-1.35)})
		for i = 0, 2, 0.1 do
			swait()
			local Alpha = .3
			RJ.C0 = clerp(RJ.C0,CFrame.new(0.00184797007, 0.00629393011, 0.00175395911, 0.916352093, -0.00251661055, -0.400364727, 0, 0.99998033, -0.00628567068, 0.400372595, 0.0057598874, 0.916333973),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.565588713, -0.991164684, -0.032800708, 0.909990132, 0, 0.414630055, -0.00260622799, 0.99998033, 0.00571989827, -0.41462189, -0.00628567068, 0.909972131),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.562351584, -0.990811467, 0.0429569148, 0.909990132, 0, 0.414630055, -0.00260622799, 0.99998033, 0.00571989827, -0.41462189, -0.00628567068, 0.909972131),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.479936, 0.442725629, -0.241928637, 0.997844577, 0.0469278991, -0.0458690971, -0.0638397709, 0.532425106, -0.844066501, -0.015188396, 0.845175505, 0.534273386),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.32794857, 0.365926802, 0.17400004, 0.584510565, -0.811339498, 0.00870320201, 0.447906405, 0.331590444, 0.830317855, -0.676555634, -0.481431335, 0.557222128),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(-0.00438193232, 1.49895084, -0.014841184, 0.916352212, -0.0230187047, 0.399710178, -0.00251696701, 0.997995079, 0.0632432774, -0.400364548, -0.0589591675, 0.914456904),Alpha)
		end
		Sound(Torso,200065377,1.3,4,false,true,true)
		for i = 0, 1, 0.1 do
			swait()
			local Alpha = .2
			RJ.C0 = clerp(RJ.C0,CFrame.new(0.0928741172, 0.00629402744, 0.0566893518, 0.948310614, 0.00199300773, 0.317336231, 0, 0.99998033, -0.00628030393, -0.31734252, 0.00595567934, 0.948291838),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.645890057, -0.990359426, 0.0953748077, 0.953149736, 0, -0.302498937, 0.00189978536, 0.99998033, 0.00598607073, 0.302492946, -0.00628030393, 0.953130901),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.44459179, -0.991404057, -0.0513649136, 0.953149736, 0, -0.302498937, 0.00189978536, 0.99998033, 0.00598607073, 0.302492946, -0.00628030393, 0.953130901),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.47928679, 0.367728233, 0.116084039, 0.997845054, 0.0248440802, 0.0607300103, -0.0638346076, 0.581721425, 0.810879469, -0.0151824057, -0.813008547, 0.582053781),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.48636484, 0.465858519, -0.373306572, -0.95769608, 0.284951091, -0.0402629375, -0.130770594, -0.306276649, 0.942917705, 0.256353855, 0.908293724, 0.330583185),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(-0.068510659, 1.4984324, -0.0973624364, 0.948310554, 0.0182456542, -0.316817731, 0.00199265103, 0.997983873, 0.0634387434, 0.31733641, -0.0607909337, 0.946362138),Alpha)
		end
		gWeld:destroy()
		local gWeld = NewInstance("Weld",Char,{Part0=RArm,Part1=torso,C0=CF.N(0,-1.15,0)*CF.A(M.R(90),0,M.R(180))})
		for i = 0, 1, 0.1 do
			swait()
			local Alpha = .3
			humanoid.PlatformStand = true
			RJ.C0 = clerp(RJ.C0,CFrame.new(3.20394752e-13, 0.00629078969, 1.39809708e-06, 0.999999225, 5.09317033e-11, 0, -4.38656264e-11, 0.999980271, -0.00628618058, 0, 0.00628617639, 0.999979496),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.496493757, -0.990819752, 0.021611426, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.498526245, -0.990984261, 0.0154614868, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.29056597, 0.680865526, -0.0074476786, -0.953151584, -0.302089065, 0.0156119959, 0.302213609, -0.953219652, 0.0062854127, 0.0129829049, 0.0107091125, 0.999858022),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.26373434, 0.722399652, 0.00951428805, -0.951173186, 0.308261454, 0.0156119959, -0.308199704, -0.951300979, 0.0062854127, 0.0167892575, 0.0011669076, 0.999858022),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(-1.17865966e-07, 1.4989531, -0.0143954754, 0.999999642, 2.11689621e-05, 1.13360584e-05, -1.50896085e-07, 0.477647185, -0.878551781, -2.40113586e-05, 0.878551543, 0.477646947),Alpha)
		end
		gWeld:destroy()
		local gWeld = NewInstance("Weld",Char,{Part0=Root,Part1=torso,C0=CF.N(0,2.35,0)*CF.A(M.R(90),0,M.R(90))})
		for i = 0, 6, 0.1 do
			swait()
			local Alpha = .3
			humanoid.PlatformStand = true
			RJ.C0 = clerp(RJ.C0,CFrame.new(3.20394752e-13, 0.00629078969, 1.39809708e-06, 0.999999225, 5.09317033e-11, 0, -4.38656264e-11, 0.999980271, -0.00628618058, 0, 0.00628617639, 0.999979496),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.496493757, -0.990819752, 0.021611426, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.498526245, -0.990984261, 0.0154614868, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.29056597, 0.680865526, -0.0074476786, -0.953151584, -0.302089065, 0.0156119959, 0.302213609, -0.953219652, 0.0062854127, 0.0129829049, 0.0107091125, 0.999858022),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.26373434, 0.722399652, 0.00951428805, -0.951173186, 0.308261454, 0.0156119959, -0.308199704, -0.951300979, 0.0062854127, 0.0167892575, 0.0011669076, 0.999858022),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(-1.17865966e-07, 1.4989531, -0.0143954754, 0.999999642, 2.11689621e-05, 1.13360584e-05, -1.50896085e-07, 0.477647185, -0.878551781, -2.40113586e-05, 0.878551543, 0.477646947),Alpha)
		end
		Sound(torso,1093102664,.85,5,false,true,true)
		Sound(torso,429400881,1,1,false,true,true)
		gWeld:destroy()
		Blood(torso.Size,torso.CFrame*CF.A(0,M.R(180),0),250)
		humanoid.Health = 0
		for _,v in next, who:children() do
			if(v:IsA'LocalScript' or v:IsA'Script')then
				v.Disabled = true
				v:destroy()
			end
		end
		Ragdoll(who,true)
		
	
		if(not VoidSB)then
			coroutine.wrap(function()
				repeat swait()
					BloodDrop(torso.CFrame * CF.N(0,-torso.Size.Y/2,0).p,(torso.CFrame * CF.N(0,-torso.Size.Y,0)).p,15)
				until not who or not who.Parent
			end)()
			coroutine.wrap(function()
				local LT = who:FindFirstChild'LowerTorso'
				if(LT)then
					repeat swait()
						BloodDrop(LT.CFrame * CF.N(0,LT.Size.Y/2,0).p,(LT.CFrame * CF.N(0,LT.Size.Y,0)).p,15)
					until not who or not who.Parent
				end
			end)()
		end
		
		for i = 0, 1, 0.1 do
			swait()
			local Alpha = .3
			humanoid.PlatformStand = true
			RJ.C0 = clerp(RJ.C0,CFrame.new(3.20394752e-13, 0.00629078969, 1.39809708e-06, 0.999999225, 5.09317033e-11, 0, -4.38656264e-11, 0.999980271, -0.00628618058, 0, 0.00628617639, 0.999979496),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.496493757, -0.990819752, 0.021611426, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.498526245, -0.990984261, 0.0154614868, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.19203663, 0.569933176, 0.0160028264, -0.81626749, 0.577462554, 0.0156119959, -0.577441692, -0.816407859, 0.0062854127, 0.016375348, -0.0038844361, 0.999858022),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.22609437, 0.679628015, 0.010370885, -0.77247268, -0.634855568, 0.0156119959, 0.634996474, -0.772489607, 0.0062854127, 0.00806977227, 0.0147688743, 0.999858022),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(-1.17865966e-07, 1.4989531, -0.0143954754, 0.999999642, 2.11689621e-05, 1.13360584e-05, -1.50896085e-07, 0.477647185, -0.878551781, -2.40113586e-05, 0.878551543, 0.477646947),Alpha)
		end
		for i = 0, 4, 0.1 do
			swait()
			local Alpha = .3
			RJ.C0 = clerp(RJ.C0,CFrame.new(3.20394752e-13, 0.00629078969, 1.39809708e-06, 0.999999225, 5.09317033e-11, 0, -4.38656264e-11, 0.999980271, -0.00628618058, 0, 0.00628617639, 0.999979496)*CF.A(M.RRNG(-5,5),M.RRNG(-5,5),M.RRNG(-5,5)),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.496493757, -0.990819752, 0.021611426, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022)*CF.A(M.RRNG(-5,5),M.RRNG(-5,5),M.RRNG(-5,5)),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.498526245, -0.990984261, 0.0154614868, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022)*CF.A(M.RRNG(-5,5),M.RRNG(-5,5),M.RRNG(-5,5)),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.19203663, 0.569933176, 0.0160028264, -0.81626749, 0.577462554, 0.0156119959, -0.577441692, -0.816407859, 0.0062854127, 0.016375348, -0.0038844361, 0.999858022)*CF.A(M.RRNG(-5,5),M.RRNG(-5,5),M.RRNG(-5,5)),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.22609437, 0.679628015, 0.010370885, -0.77247268, -0.634855568, 0.0156119959, 0.634996474, -0.772489607, 0.0062854127, 0.00806977227, 0.0147688743, 0.999858022)*CF.A(M.RRNG(-5,5),M.RRNG(-5,5),M.RRNG(-5,5)),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(-1.17865966e-07, 1.4989531, -0.0143954754, 0.999999642, 2.11689621e-05, 1.13360584e-05, -1.50896085e-07, 0.477647185, -0.878551781, -2.40113586e-05, 0.878551543, 0.477646947)*CF.A(M.RRNG(-5,5),M.RRNG(-5,5),M.RRNG(-5,5)),Alpha)
		end
		who.Parent = workspace
		Attack = false
		NeutralAnims = true
		Hum.WalkSpeed = 16
		Hum.JumpPower = 50
	end
end

function ThrowArms()
	Attack = true
	NeutralAnims = false
	for i = 0, 3, 0.1 do
		swait()
		local Alpha = .15
		RJ.C0 = clerp(RJ.C0,CFrame.new(3.20552612e-13, 0.00629388914, 1.4175821e-06, 0.999999225, 5.09317033e-11, 0, -4.38656264e-11, 0.999980271, -0.00628618058, 0, 0.00628617639, 0.999979496),Alpha)
		LH.C0 = clerp(LH.C0,CFrame.new(-0.496493757, -0.990822613, 0.0216114447, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
		RH.C0 = clerp(RH.C0,CFrame.new(0.498533875, -0.990984261, 0.0154613676, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
		LS.C0 = clerp(LS.C0,CFrame.new(-1.49870801, 0.639989734, 0.342571348, 0.999877751, -0.0114739574, -0.0105869146, -9.81397825e-05, -0.682732999, 0.730668128, -0.0156116877, -0.730577767, -0.682650685),Alpha)
		RS.C0 = clerp(RS.C0,CFrame.new(1.50170219, 0.685996532, 0.261634499, 0.999877751, -0.0114739574, -0.0105869146, -9.81397825e-05, -0.682732999, 0.730668128, -0.0156116877, -0.730577767, -0.682650685),Alpha)
		NK.C0 = clerp(NK.C0,CFrame.new(8.16625652e-06, 1.4989531, -0.0144006833, 0.999999225, 3.67464963e-07, -1.62050128e-07, -3.56478267e-07, 0.997964799, 0.0637686923, 1.8440187e-07, -0.0637686551, 0.997963905),Alpha)
	end
	Sound()
	FLArmW:destroy()
	FRArmW:destroy()
	local BV1 = NewInstance("BodyVelocity", FRArm, {
		velocity = Vector3.new(0, 10, 0) + Mouse.Hit.lookVector * 50,
		P = 5000,
		maxForce = Vector3.new(8000, 8000, 8000),
	})
	local BV2 = NewInstance("BodyVelocity", FLArm, {
		velocity = Vector3.new(0, 10, 0) + Mouse.Hit.lookVector * 50,
		P = 5000,
		maxForce = Vector3.new(8000, 8000, 8000),
	})
	Sound(Torso,541909763,.8,5,false,true,true)
	S.Debris:AddItem(BV1, 0.05)
	S.Debris:AddItem(BV2, 0.05)
	FRArm.CanCollide = true
	FLArm.CanCollide = true
	S.Debris:AddItem(FRArm, 5)
	S.Debris:AddItem(FLArm, 5)
	FRArm = nil
	FLArm = nil
	for i = 0, 1, 0.1 do
		swait()
		local Alpha = .3
		RJ.C0 = clerp(RJ.C0,CFrame.new(3.20552612e-13, 0.00629388914, 1.4175821e-06, 0.999999225, 5.09317033e-11, 0, -4.38656264e-11, 0.999980271, -0.00628618058, 0, 0.00628617639, 0.999979496),Alpha)
		LH.C0 = clerp(LH.C0,CFrame.new(-0.496493757, -0.990822613, 0.0216114447, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
		RH.C0 = clerp(RH.C0,CFrame.new(0.498533875, -0.990984261, 0.0154613676, 0.999877751, -4.38656264e-11, 0.0156119959, -9.81397825e-05, 0.999980271, 0.0062854127, -0.0156116877, -0.00628618058, 0.999858022),Alpha)
		LS.C0 = clerp(LS.C0,CFrame.new(-1.50884342, 0.499208659, -0.305685878, 0.999877751, 0.0152528696, -0.00332931988, -9.81397825e-05, -0.20710893, -0.978317916, -0.0156116877, 0.978198647, -0.207082108),Alpha)
		RS.C0 = clerp(RS.C0,CFrame.new(1.4918015, 0.444425255, -0.370944679, 0.999877751, 0.0152528696, -0.00332931988, -9.81397825e-05, -0.20710893, -0.978317916, -0.0156116877, 0.978198647, -0.207082108),Alpha)
		NK.C0 = clerp(NK.C0,CFrame.new(8.16625652e-06, 1.4989531, -0.0144006833, 0.999999225, 3.67464963e-07, -1.62050128e-07, -3.56478267e-07, 0.997964799, 0.0637686923, 1.8440187e-07, -0.0637686551, 0.997963905),Alpha)
	end
	Attack = false
	NeutralAnims = true
end
Mouse.KeyDown:connect(function(k)
	if(Attack)then return end
	if(k == 'q')then Teleport(Mouse.Hit*CF.N(0,3.25,0)) end
	if(k == 'e')then Dash() end
	if(not FLArm and not FRArm)then
		if(k == 'z')then The_Necc() end
		if(k == 'x')then The_End() end
		if(k == 'c')then Hands_Off() end
		if(k == 'v')then SawMeDaddy() end
		if(k == 'b')then Shriek() end
		if(k == 't')then Taunt() end
	end
end)

Mouse.Button1Down:connect(function()
	if(Attack)then return end
	if(FLArm and FRArm)then
		ThrowArms()
	end
end)
Plr.Chatted:connect(function(m)
	if(m == '/e aeiou')then Sound(Torso,221792881,1,5,false,true,true) end 
	if(m == '/e earthquake')then Sound(Torso,1205111204,1,5,false,true,true) end 
	if(Attack)then return end
	if(m == '/e dab')then Aids() end
end)

--// Wrap it all up \\--

while true do
	swait()
	if(not Music or not Music.Parent)then
		local a = Music.TimePosition
		Music = Sound(Char,MusicID,MusicPitch,2,true,false,true)
		Music.Name = 'Music'
		Music.TimePosition = a
	end
	if(Music.Volume ~= 2)then Music.Volume = 2 end
	RArm.Transparency = 1
	Sine = Sine + Change
	local hitfloor,posfloor = workspace:FindPartOnRay(Ray.new(Root.CFrame.p,((CFrame.new(Root.Position,Root.Position - Vector3.new(0,1,0))).lookVector).unit * 4), Char)
	local Walking = (math.abs(Root.Velocity.x) > 1 or math.abs(Root.Velocity.z) > 1)
	local State = (Hum.PlatformStand and 'Paralyzed' or Hum.Sit and 'Sit' or not hitfloor and Root.Velocity.y < -1 and "Fall" or not hitfloor and Root.Velocity.y > 1 and "Jump" or hitfloor and Walking and "Walk" or hitfloor and "Idle")
	if(State == 'Walk')then
		local wsVal = 7 / (Hum.WalkSpeed/16)
		local Alpha = math.min(.2*(Hum.WalkSpeed/16),1)
		--RH.C1 = RH.C1:lerp(CF.N(0,.925+.5*M.C(Sine/wsVal)/2,0+.5*M.C(Sine/wsVal)/2)*CF.A(-M.R(-15-35*M.C(Sine/wsVal) + -M.S(Sine/wsVal)/2.5),0,0),Alpha)
		--RH.C0 = clerp(RH.C0, CF(1, -0.925 - 0.5 * Cos(sine / 7) / 2, 0.5 * Cos(sine / 7) / 2) * angles(Rad(-15 - 35 * Cos(sine / 7)) - rl.RotVelocity.Y / 75 + -Sin(sine / 7) / 2.5, Rad(90 - 0.1 * Cos(sine / 7)), Rad(0)) * angles(Rad(0 + 0.1 * Cos(sine / 7)), Rad(0), Rad(0)), 0.3)--
		RH.C1 = RH.C1:lerp(CF.N(0,.95+.5*M.C(Sine/wsVal)/2,.5*M.C(Sine/wsVal)/2) * CF.A(M.R(15-45*M.C(Sine/wsVal)) + M.S(Sine/wsVal)/2.5,0,0)*CF.A(M.R(0+.1*M.C(Sine/wsVal)),0,0),Alpha)
		LH.C1 = LH.C1:lerp(CF.N(0,.95-.5*M.C(Sine/wsVal)/2,-.5*M.C(Sine/wsVal)/2) * CF.A(M.R(15+45*M.C(Sine/wsVal)) + -M.S(Sine/wsVal)/2.5,0,0)*CF.A(M.R(0+.1*M.C(Sine/wsVal)),0,0),Alpha)	
	else
		RH.C1 = RH.C1:lerp(CF.N(0,1,0),.3)
		LH.C1 = LH.C1:lerp(CF.N(0,1,0),.3)
	end	
	if(Idle > Frame_Speed*10)then
		--idk i'll do something
	end
	if(NeutralAnims and not Attack and State == 'Idle')then
		Idle = Idle + 1
	else
		Idle = 0
	end
	for v,_ in next, Stunned do
		if(v.Parent)then
			local h = v:FindFirstChildOfClass'Humanoid'
			for _,c in next, v:children() do
				if(c:IsA'Script' or c:IsA'LocalScript')then
					c.Disabled = false
				end
			end
			if(h)then
				h.Name = 'no escape lol'
				h.PlatformStand = true
			else
				Stunned[v] = nil
			end
		else
			Stunned[v] = nil
		end
	end
	if(NeutralAnims)then	
		if(State == 'Idle')then
			Change = 1
			local Alpha = .3
			RJ.C0 = clerp(RJ.C0,CFrame.new(0.00232864846, 0.00629545515+.2*M.C(Sine/16), 0.00257661846, 0.838281333, -0.00342716719, -0.545226395, 0, 0.99998033, -0.00628564507, 0.545237184, 0.00526913954, 0.838264763),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.725328565, -0.990803361-.2*M.C(Sine/16), 0.0247094855, 0.82966727, 0, 0.558258176, -0.00350901252, 0.99998033, 0.00521499431, -0.558247149, -0.00628564507, 0.829650879),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.576427579, -0.99124372-.2*M.C(Sine/16), -0.02560886, 0.82966727, 0, 0.558258176, -0.00350901252, 0.99998033, 0.00521499431, -0.558247149, -0.00628564507, 0.829650879),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.46491873, 0.505438805+.2*M.C(Sine/16), -0.00360340625, 0.996807694, 0.0782995075, 0.0156106055, -0.0784052685, 0.996901929, 0.00628136564, -0.0150704384, -0.0074852705, 0.999858379)*CF.A(-M.R(0+5*M.S(Sine/16)),0,M.R(0+5*M.C(Sine/16))),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.44824493, 0.497874349+.2*M.C(Sine/16), 0.00803661905, 0.994963646, -0.0990139842, 0.0156099498, 0.0989264548, 0.995075107, 0.00628477754, -0.0161553323, -0.00470888987, 0.999858439)*CF.A(-M.R(0+5*M.S(Sine/16)),0,-M.R(0+5*M.C(Sine/16))),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(-0.00607250631, 1.49895012, -0.0144915879, 0.838281453, -0.0313475803, 0.544335127, -0.00342752389, 0.998023272, 0.0627533421, -0.545226216, -0.0544706844, 0.836516857)*CF.A(M.R(0+5*M.C(Sine/16)),0,0),Alpha)
		elseif(State == 'Walk')then
			local wsVal = 7 / (Hum.WalkSpeed/16)
			local Alpha = math.min(.2*(Hum.WalkSpeed/16),1)
			RJ.C0 = RJ.C0:lerp(RJC0*CF.N(0,-0.175 + 0.025 * M.C(Sine/(wsVal/2)) + -M.S(Sine/(wsVal/2)) / 7,0)*CF.A(0,M.R(0+8*M.C(Sine/wsVal)),M.R(0+2*M.C(Sine/wsVal))),Alpha)
			RH.C0 = RH.C0:lerp(RHC0,Alpha)
			LH.C0 = LH.C0:lerp(LHC0,Alpha)
			RS.C0 = RS.C0:lerp(RSC0*CF.A(M.R(0-45*M.C(Sine/wsVal)),0,M.R(5+10*M.C(Sine/wsVal))),Alpha)
			LS.C0 = LS.C0:lerp(LSC0*CF.A(M.R(0+45*M.C(Sine/wsVal)),0,M.R(-5+10*M.C(Sine/wsVal))),Alpha)
			NK.C0 = NK.C0:lerp(NKC0,Alpha)
		elseif(State == 'Jump' or State == 'Fall')then
			if(Walking)then
				local Alpha = .2
				RJ.C0 = clerp(RJ.C0,RJC0*CF.A(math.min(math.max(Root.Velocity.Y/100,-M.R(65)),M.R(65)),0,0),Alpha)
				LH.C0 = clerp(LH.C0,CFrame.new(-0.497912645, -1.0987643, -0.0683324337, 0.999878228, 0.00860835519, 0.0130246133, -0.00010142161, 0.837816596, -0.545952022, -0.015611981, 0.545884132, 0.837715328),Alpha)
				RH.C0 = clerp(RH.C0,CFrame.new(0.499978393, -1.16382337, 0.109293163, 0.999878228, -0.0120433727, 0.00993486121, -0.00010142161, 0.631323814, 0.775519371, -0.015611981, -0.775425911, 0.631245613),Alpha)
				LS.C0 = clerp(LS.C0,CFrame.new(-1.55211556, 0.576563478, -0.00269976072, 0.976067662, 0.216906726, 0.0156116467, -0.217024669, 0.976145923, 0.00628317893, -0.0138763804, -0.00952091813, 0.999858499),Alpha)
				RS.C0 = clerp(RS.C0,CFrame.new(1.50182188, 0.636661649, 0.00632623257, 0.977592707, -0.209926367, 0.0156121543, 0.209851891, 0.977713108, 0.00628198683, -0.016582964, -0.00286500831, 0.999858439),Alpha)
				NK.C0 = clerp(NK.C0,CFrame.new(1.14440072e-05, 1.49924362, -0.0143961608, 1.00000024, -5.82076609e-11, 0, 1.23691279e-10, 0.997964919, 0.0637660474, 0, -0.0637660623, 0.997965038),Alpha)
			else
				local Alpha = .2
				RJ.C0 = clerp(RJ.C0,RJC0*CF.A(math.min(math.max(Root.Velocity.Y/100,-M.R(65)),M.R(65)),0,0),Alpha)
				LH.C0 = clerp(LH.C0,CFrame.new(-0.504374504, -0.291219354, -0.487436086, 0.999878228, -0.00438931212, 0.0149825988, -0.00010142161, 0.957819223, 0.287371844, -0.015611981, -0.287338346, 0.957701981),Alpha)
				RH.C0 = clerp(RH.C0,CFrame.new(0.453094482, -0.871358454, 0.0898642987, 0.985589385, -0.168456957, 0.0153662469, 0.162863791, 0.969548643, 0.182895929, -0.0457084104, -0.177757636, 0.983012319),Alpha)
				LS.C0 = clerp(LS.C0,CFrame.new(-1.55211556, 0.576563478, -0.00269976072, 0.976067662, 0.216906726, 0.0156116467, -0.217024669, 0.976145923, 0.00628317893, -0.0138763804, -0.00952091813, 0.999858499),Alpha)
				RS.C0 = clerp(RS.C0,CFrame.new(1.50182188, 0.636661649, 0.00632623257, 0.977592707, -0.209926367, 0.0156121543, 0.209851891, 0.977713108, 0.00628198683, -0.016582964, -0.00286500831, 0.999858439),Alpha)
				NK.C0 = clerp(NK.C0,CFrame.new(1.14440072e-05, 1.49924362, -0.0143961608, 1.00000024, -5.82076609e-11, 0, 1.23691279e-10, 0.997964919, 0.0637660474, 0, -0.0637660623, 0.997965038),Alpha)			
			end
		elseif(State == 'Paralyzed')then
			local Alpha = .3
			RJ.C0 = RJ.C0:lerp(RJC0,Alpha)
			RH.C0 = RH.C0:lerp(RHC0*CF.A(M.RRNG(-10,10),M.RRNG(-10,10),M.RRNG(-10,10)),Alpha)
			LH.C0 = LH.C0:lerp(LHC0*CF.A(M.RRNG(-10,10),M.RRNG(-10,10),M.RRNG(-10,10)),Alpha)
			RS.C0 = RS.C0:lerp(RSC0*CF.A(M.RRNG(-10,10),M.RRNG(-10,10),M.RRNG(-5,15)),Alpha)
			LS.C0 = LS.C0:lerp(LSC0*CF.A(M.RRNG(-10,10),M.RRNG(-10,10),M.RRNG(-15,5)),Alpha)
			NK.C0 = NK.C0:lerp(NKC0,Alpha)
		elseif(State == 'Sit')then
			local Alpha = .3
			RJ.C0 = clerp(RJ.C0,CFrame.new(3.2050404e-13, 0.00629293546, 1.41158671e-06, 0.999999225, 5.09317033e-11, 0, -4.38656264e-11, 0.999980271, -0.00628618058, 0, 0.00628617639, 0.999979496),Alpha)
			LH.C0 = clerp(LH.C0,CFrame.new(-0.686911047, -1.01880026, -0.25455457, 0.980693579, 0.195502773, 0.00425194856, -0.0504306704, 0.273862094, -0.960446, -0.188934311, 0.941688716, 0.278434128),Alpha)
			RH.C0 = clerp(RH.C0,CFrame.new(0.557953715, -1.03419244, -0.293038249, 0.986133933, -0.165894628, 0.00425344985, 0.0502241589, 0.273924351, -0.960439026, 0.158166528, 0.947335124, 0.278457999),Alpha)
			LS.C0 = clerp(LS.C0,CFrame.new(-1.50518143, 0.551521897, -0.0714710951, 0.999877751, 0.0137732355, 0.00735067623, -9.81397825e-05, 0.47637102, -0.879244447, -0.0156116877, 0.879136324, 0.476314098),Alpha)
			RS.C0 = clerp(RS.C0,CFrame.new(1.4960835, 0.497820318, -0.0970379114, 0.999877751, 0.0137732355, 0.00735067623, -9.81397825e-05, 0.47637102, -0.879244447, -0.0156116877, 0.879136324, 0.476314098),Alpha)
			NK.C0 = clerp(NK.C0,CFrame.new(4.35156289e-06, 1.49895275, -0.0144044831, 0.999999225, 3.67464963e-07, -1.62050128e-07, -3.56478267e-07, 0.997964799, 0.0637686923, 1.8440187e-07, -0.0637686551, 0.997963905),Alpha)
		end
	end
end
