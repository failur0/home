_G.CustomUI = false

if not _G.CustomUI then _G.CustomUI = false end
VERSION = "1.0.4"

if AlreadyLoaded then
    return 
end
getgenv().AlreadyLoaded = true -- So that you can't execute the script twice

if not game:IsLoaded() then
  print("Homebrew Admin is waiting for the game to load..")
	game.Loaded:Wait()
end
prefix = ";" -- After running hb admin for the first time changing this won't do anything.
local Players = game:GetService("Players") -- pls use this incase the game devs rename Players to something else
local Player = Players.LocalPlayer
function _G.getPlayer(shortcut)
local player
local g = Players:GetPlayers()
for i = 1, #g do
  if string.lower(string.sub(g[i].Name, 1, string.len(shortcut))) == string.lower(shortcut) then
    player = g[i]
    break
  elseif string.lower(string.sub(g[i].DisplayName, 1, string.len(shortcut))) == string.lower(shortcut) then
    player = g[i]
    break
  end
end
return player
end

getPlayer = _G.getPlayer

-- Destroys UI for Custom UI's
function ToCustomUI()
  if game.CoreGui.HBADMIN then
    game.CoreGui.HBADMIN:Destroy() 
  end
end

plr = Player
char = plr.Character
Character = char
local Torso = Character:FindFirstChild("Torso") or Character:FindFirstChild("UpperTorso")
Humanoid = char.Humanoid

plr.CharacterAdded:Connect(
function(newchar)
	Character = newchar
	char = newchar
	newchar:WaitForChild("Humanoid").Died:Connect(
  function()
    _G.spawn = newchar.HumanoidRootPart.CFrame -- For the dpos command.
  end
  )
end
)


function _G.notify(text) -- Notification system with args as text
  coroutine.wrap(
  function()
    local ScreenGui = Instance.new("ScreenGui")
    ScreenGui.Parent = game.CoreGui
    local Frame = Instance.new("Frame")
    local TextLabel = Instance.new("TextLabel")
    local PenumbraShadow = Instance.new("ImageLabel")
    local TextLabel_2 = Instance.new("TextLabel")
    local TextLabel_3 = Instance.new("TextLabel")
    local ImageLabel = Instance.new("ImageLabel")
    local ImageLabel_2 = Instance.new("ImageLabel")
    Frame.Parent = ScreenGui
    Frame.AnchorPoint = Vector2.new(0.5, 0.5)
    Frame.BackgroundColor3 = Color3.fromRGB(5, 11, 24)
    Frame.Position = UDim2.new(-0.039212832, 0, 0.906705499, 0)
    Frame.Size = UDim2.new(0, 356, 0, 106)
    Frame.ZIndex = 2
    TextLabel.Parent = Frame
    TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    TextLabel.BackgroundTransparency = 1.000
    TextLabel.Position = UDim2.new(0.0646068305, 0, 0.0693927407, 0)
    TextLabel.Size = UDim2.new(0, 131, 0, 36)
    TextLabel.ZIndex = 2
    TextLabel.Font = Enum.Font.GothamBlack
    TextLabel.Text = "HOMEBREW ADMIN"
    TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
    TextLabel.TextSize = 16.000
    PenumbraShadow.Name = "PenumbraShadow"
    PenumbraShadow.Parent = Frame
    PenumbraShadow.Active = true
    PenumbraShadow.AnchorPoint = Vector2.new(0.5, 0.5)
    PenumbraShadow.BackgroundTransparency = 1.000
    PenumbraShadow.BorderSizePixel = 0
    PenumbraShadow.Position = UDim2.new(0.5, 0, 0.5, 1)
    PenumbraShadow.Size = UDim2.new(1, 18, 1, 18)
    PenumbraShadow.Image = "rbxassetid://1316045217"
    PenumbraShadow.ImageColor3 = Color3.fromRGB(0, 0, 0)
    PenumbraShadow.ImageTransparency = 0.880
    PenumbraShadow.ScaleType = Enum.ScaleType.Slice
    PenumbraShadow.SliceCenter = Rect.new(10, 10, 118, 118)
    TextLabel_2.Parent = Frame
    TextLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    TextLabel_2.BackgroundTransparency = 1.000
    TextLabel_2.Position = UDim2.new(0.0646068305, 0, 0.406026393, 0)
    TextLabel_2.Size = UDim2.new(0, 56, 0, 9)
    TextLabel_2.ZIndex = 2
    TextLabel_2.Font = Enum.Font.Gotham
    TextLabel_2.Text = "Notification"
    TextLabel_2.TextColor3 = Color3.fromRGB(255, 255, 255)
    TextLabel_2.TextSize = 14.000
    TextLabel_2.TextTransparency = 0.100
    TextLabel_3.Parent = Frame
    TextLabel_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    TextLabel_3.BackgroundTransparency = 1.000
    TextLabel_3.Position = UDim2.new(0.418539405, 0, 0.632441521, 0)
    TextLabel_3.Size = UDim2.new(0, 56, 0, 9)
    TextLabel_3.ZIndex = 2
    TextLabel_3.Font = Enum.Font.Gotham
    TextLabel_3.Text = text
    TextLabel_3.TextColor3 = Color3.fromRGB(255, 255, 255)
    TextLabel_3.TextSize = 14.000
    ImageLabel.Parent = Frame
    ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    ImageLabel.BackgroundTransparency = 1.000
    ImageLabel.Position = UDim2.new(0, 0, 0.6324417, 0)
    ImageLabel.Size = UDim2.new(0, 101, 0, 48)
    ImageLabel.ZIndex = 2
    ImageLabel.Image = "http://www.roblox.com/asset/?id=217370037"
    ImageLabel.ImageTransparency = 0.600
    ImageLabel_2.Parent = Frame
    ImageLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    ImageLabel_2.BackgroundTransparency = 1.000
    ImageLabel_2.Position = UDim2.new(0.716292143, 0, -0.0468035638, 0)
    ImageLabel_2.Rotation = 180.000
    ImageLabel_2.Size = UDim2.new(0, 101, 0, 48)
    ImageLabel_2.ZIndex = 2
    ImageLabel_2.Image = "http://www.roblox.com/asset/?id=217370037"
    ImageLabel_2.ImageTransparency = 0.600
    Frame:TweenPosition(UDim2.new(0.139212832, 0, 0.906705499, 0), "Out", "Back", "1")
    wait(3)
    Frame:TweenPosition(UDim2.new(-1.039212832, 0, 0.906705499, 0), "Out", "Back", "1")
    wait(10)
    ScreenGui:Destroy()
  end
  )()
end
notify = _G.notify

function changelog() -- Changelog everytime a new script is executed.
local ScreenGui = Instance.new("ScreenGui")
local Changelog = Instance.new("Frame")
local Penumbra = Instance.new("ImageLabel")
local ImageLabel = Instance.new("ImageLabel")
local CMDTITLE = Instance.new("TextLabel")
local ImageLabel_2 = Instance.new("ImageLabel")
local MAOWQ = Instance.new("TextLabel")
local ImageLabel_3 = Instance.new("ImageLabel")
local Chanelog = Instance.new("TextLabel")

--Properties:

ScreenGui.Parent = game.CoreGui
ScreenGui.Name = "HBLOG"

Changelog.Name = "Changelog"
Changelog.Parent = ScreenGui
Changelog.AnchorPoint = Vector2.new(0.5, 0.5)
Changelog.BackgroundColor3 = Color3.fromRGB(5, 11, 24)
Changelog.Position = UDim2.new(0.499635637, 0, 1.499820173, 0)
Changelog.Size = UDim2.new(0, 479, 0, 288)
Changelog.ZIndex = 2
Changelog.Visible = true

Penumbra.Name = "Penumbra"
Penumbra.Parent = Changelog
Penumbra.Active = true
Penumbra.AnchorPoint = Vector2.new(0.5, 0.5)
Penumbra.BackgroundTransparency = 1.000
Penumbra.BorderSizePixel = 0
Penumbra.Position = UDim2.new(0.45726496, 0, 0.584302306, 1)
Penumbra.Size = UDim2.new(1, 18, 1, 18)
Penumbra.Image = "rbxassetid://1316045217"
Penumbra.ImageColor3 = Color3.fromRGB(0, 0, 0)
Penumbra.ImageTransparency = 0.880
Penumbra.ScaleType = Enum.ScaleType.Slice
Penumbra.SliceCenter = Rect.new(10, 10, 118, 118)

ImageLabel.Parent = Changelog
ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel.BackgroundTransparency = 1.000
ImageLabel.Position = UDim2.new(-0.0132315634, 0, 0.770409405, 0)
ImageLabel.Size = UDim2.new(0, 101, 0, 83)
ImageLabel.ZIndex = 2
ImageLabel.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel.ImageTransparency = 0.600

CMDTITLE.Name = "CMDTITLE"
CMDTITLE.Parent = Changelog
CMDTITLE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
CMDTITLE.BackgroundTransparency = 1.000
CMDTITLE.Position = UDim2.new(0.362217844, 0, 0.074537456, 0)
CMDTITLE.Size = UDim2.new(0, 131, 0, 36)
CMDTITLE.ZIndex = 2
CMDTITLE.Font = Enum.Font.GothamBlack
CMDTITLE.Text = "HOMEBREW ADMIN"
CMDTITLE.TextColor3 = Color3.fromRGB(255, 255, 255)
CMDTITLE.TextSize = 20.000

ImageLabel_2.Parent = Changelog
ImageLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel_2.BackgroundTransparency = 1.000
ImageLabel_2.Position = UDim2.new(0.16108036, 0, 0.810999811, 0)
ImageLabel_2.Size = UDim2.new(0, 88, 0, 61)
ImageLabel_2.ZIndex = 2
ImageLabel_2.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel_2.ImageTransparency = 0.800

MAOWQ.Name = "MAOWQ"
MAOWQ.Parent = Changelog
MAOWQ.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
MAOWQ.BackgroundTransparency = 1.000
MAOWQ.Position = UDim2.new(0.440408856, 0, 0.197908744, 0)
MAOWQ.Size = UDim2.new(0, 56, 0, 23)
MAOWQ.ZIndex = 2
MAOWQ.Font = Enum.Font.Gotham
MAOWQ.Text = "CHANGELOG // "..VERSION
MAOWQ.TextColor3 = Color3.fromRGB(255, 255, 255)
MAOWQ.TextSize = 12.000

ImageLabel_3.Parent = Changelog
ImageLabel_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel_3.BackgroundTransparency = 1.000
ImageLabel_3.Position = UDim2.new(0.20083572, 0, 0.89956069, 0)
ImageLabel_3.Size = UDim2.new(0, 105, 0, 37)
ImageLabel_3.ZIndex = 2
ImageLabel_3.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel_3.ImageTransparency = 0.800

Chanelog.Name = "Chanelog"
Chanelog.Parent = Changelog
Chanelog.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Chanelog.BackgroundTransparency = 1.000
Chanelog.Position = UDim2.new(0.0921858922, 0, 0.276124328, 0)
Chanelog.Size = UDim2.new(0, 391, 0, 194)
Chanelog.ZIndex = 2
Chanelog.Font = Enum.Font.Gotham
Chanelog.Text = loadstring(game:HttpGet(('https://raw.githubusercontent.com/mgamingpro/HomebrewAdmin/master/scripts/changelog.lua'),true))()
Chanelog.TextColor3 = Color3.fromRGB(255, 255, 255)
Chanelog.TextScaled = true
Chanelog.TextSize = 12.000
Chanelog.TextWrapped = true

local Close = Instance.new("TextButton")
Close.Name = "Close"
Close.Parent = Changelog
Close.BackgroundColor3 = Color3.fromRGB(5, 11, 24)
Close.BorderSizePixel = 0
Close.Position = UDim2.new(0.93, 0, 0, 0)
Close.Size = UDim2.new(0, 32, 0, 28)
Close.Font = Enum.Font.SourceSansLight
Close.Text = "X"
Close.TextColor3 = Color3.fromRGB(255, 255, 255)
Close.TextSize = 23.000
Close.TextWrapped = true
Close.ZIndex = 2
-- Scripts:
-- Close Button Function
local function JRNGOD_fake_script() -- Close.hover 
	local script = Instance.new('LocalScript', Close)

	script.Parent.MouseEnter:Connect(function()
		game:GetService("TweenService"):Create(script.Parent, TweenInfo.new(0.25), {
			['BackgroundColor3'] = Color3.fromRGB(255, 0, 0)
		}):Play()
		game:GetService("TweenService"):Create(script.Parent.Parent.Close, TweenInfo.new(0.25), {
			['BackgroundColor3'] = Color3.fromRGB(255, 0, 0)
		}):Play()
	end)
	
	script.Parent.MouseLeave:Connect(function()
		game:GetService("TweenService"):Create(script.Parent, TweenInfo.new(0.25), {
			['BackgroundColor3'] = Color3.fromRGB(5, 11, 24)
		}):Play()
		game:GetService("TweenService"):Create(script.Parent.Parent.Close, TweenInfo.new(0.25), {
			['BackgroundColor3'] = Color3.fromRGB(5, 11, 24)
		}):Play()
	end)
end
coroutine.wrap(JRNGOD_fake_script)()
local function HHNIX_fake_script() -- Close.LocalScript 
	local script = Instance.new('LocalScript', Close)

	script.Parent.MouseButton1Click:Connect(function()
	    wait()
		Changelog:TweenPosition(UDim2.new(0.499635637, 0, 1.499820173, 0), "Out", "Back", "1")
		wait(3)
		ScreenGui:Destroy()
	end)
end

coroutine.wrap(HHNIX_fake_script)()

Changelog:TweenPosition(UDim2.new(0.499635637, 0, 0.499820173, 0), "Out", "Back", "1")
end
-- Calls for changelog if new version is executed for the first time.
local valid = isfile("Admin/VERSION.hb")
if valid then
  contents = readfile("Admin/VERSION.hb")
  if contents == VERSION then
  else
   changelog()
  end
else
 changelog()
end

writefile("Admin/VERSION.hb", VERSION) -- Writes the version of the script used.


function whisper(player, text)
  wait()
  game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(
  "/w " .. player.Name .. " " .. text,
  "All"
  )
end

local plr = Player

local admins = {}

_G.commands = {
  a = {
    name = "reset",
    args = 0,
    aliases = {"re","refresh"},
    description = "resets you",
    command = function()
    Player.Character.Humanoid.Health = 0
  end
}
}

function addcommand(named, desc, Args, Aliases, command)
cmd = {
  name = named,
  args = Args,
  description = desc,
  aliases = Aliases,
  command = command
}
table.insert(commands, cmd)
end

local created = false
if isfolder("Admin") then
created = true
for _,pluginz in pairs(listfiles("Admin/plugins")) do
    local succ,err = pcall(function()
    local plug = loadfile(pluginz)()
    for index, data in pairs(plug.commands) do
        table.insert(_G.commands,data)
    end
end)
end
end

local Plugin = {
    author = "Mizt",
    name = "Who is net",
    commands = {
        whoisnet = {
            name = "whoisnet",
            args = 0,
            description = "notify you who have net.",
            aliases = {'win'},
            command = function()
                local plrChild = Players:GetChildren()
                local finalTab = {}
                for i=1,#plrChild do
                    local semiC = plrChild[i]
                    if gethiddenproperty(semiC,"SimulationRadius") > 1000 then
                        table.insert(finalTab,semiC.Name)
                    end
                end
                if #finalTab == 0 then
                    _G.notify('Net Player',"None")
                else
                    _G.notify('Net Players',table.concat(finalTab,","))
                end
            end
        },
        whoisnetchat = {
            name = "whoisnetchat",
            args = 0,
            description = "Chat who have net.",
            aliases = {'winchat'},
            command = function()
                local plrChild = Players:GetChildren()
                local finalTab = {}
                for i=1,#plrChild do
                    local semiC = plrChild[i]
                    if gethiddenproperty(semiC,"SimulationRadius") > 1000 then
                        table.insert(finalTab,semiC.Name)
                    end
                end
                if #finalTab == 0 then
                    game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer("Net Player: None","All")
                else
                    game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer("Net Players: "..table.concat(finalTab,","),"All")
                end
            end
        },
        whoisbiggestnet = {
            name = "whoisbiggestnet",
            args = 0,
            description = "notify you who have the biggest net.",
            aliases = {'winbig'},
            command = function()
                local plrChild = Players:GetChildren()
                local finalNum = 0
                local finalPlr = 0
                for i=1,#plrChild do
                    local semiC = plrChild[i]
                    local semiN = gethiddenproperty(semiC,"SimulationRadius")
                    if semiN > finalNum then
                        finalPlr = i
                        finalNum = semiN
                    end
                end
                if finalPlr ~= 0 then
                    _G.notify('Biggest player net',plrChild[finalPlr].Name.." :"..finalNum)
                else
                    _G.notify('Biggest player net',"None")
                end
            end
        },
        whoissmallestnet = {
            name = "whoissmallestnet",
            args = 0,
            description = "notify you who have the smallest net.",
            aliases = {'winsmall'},
            command = function()
                local plrChild = Players:GetChildren()
                local finalNum = 100000000
                local finalPlr = 0
                for i=1,#plrChild do
                    local semiC = plrChild[i]
                    local semiN = gethiddenproperty(semiC,"SimulationRadius")
                    if semiN < finalNum then
                        finalPlr = i
                        finalNum = semiN
                    end
                end
                if finalPlr ~= 0 then
                    _G.notify('Smallest player net',plrChild[finalPlr].Name.." :"..finalNum)
                else
                    _G.notify('Smallest player net',"None")
                end
            end
        },
        howmuchnet = {
            name = "howmuchnet",
            args = 1,
            description = "notify you other ppl net.",
            aliases = {'nt'},
            command = function(target)
                local succ,err = pcall(function()
                local plr = _G.getPlayer(target)
                local user = plr.Name
                print(user)
                    _G.notify('Player net '..user.." : "..gethiddenproperty(plr,"SimulationRadius"))
                end)
                if err then
                    _G.notify('Player net ',err)
                end
            end
        }
    }
}
for index, data in pairs(Plugin.commands) do
        table.insert(_G.commands,data)
end
-- Inserting plugin into commands
_G.utils = {}

commands = _G.commands
utils = _G.utils


if created == false then
makefolder("Admin")
writefile("Admin/Settings.hb", "Settings: Default.")
writefile("Admin/Prefix.hb", prefix)
end
function preffire()
writefile("Admin/Prefix.hb", prefix)
end
function keyfire(keyf)
getgenv().apikey = keyf
writefile("Admin/SpotifyAPI.hb",keyf)
end
function readk()
local suc,err = pcall(function()
textb = readfile("/Admin/SpotifyAPI.hb")
end)
if suc then
  getgenv().apikey = textb
else
  getgenv().apikey = nil
end
end
readk()
local defsetting = false
local text = readfile("/Admin/Settings.hb")
if text == "Settings: Default." then
defsetting = true
end
function update()
local text = readfile("/Admin/Prefix.hb")
prefix = text
end
update()






function addutil(named, command)
util = {
  name = named,
  command = command
}
table.insert(commands, cmd)
end

local created = false
if isfolder("Admin") and isfolder("Admin/plugins") then
created = true
end

if created == false then
makefolder("Admin")
makefolder("Admin/plugins")
writefile("Admin/Settings.hb", "Settings: Default.")
end

local defsetting = false
local text = readfile("/Admin/Settings.hb")
if text == "Settings: Default." then
defsetting = true
end

addcommand(
"tfling",
"makes your tool fling (dont equip)",
0,
{"toolfling"},
function()
notify("Equip your tool.")
Tool = Player.Backpack:FindFirstChildWhichIsA("Tool")
if not Tool then
repeat wait() Tool = Player.Backpack:FindFirstChildWhichIsA("Tool") until Tool
end
Tool.Handle.Massless = true
Tool.GripPos = Vector3.new(0, -10000, 0)
end
)

local arms = {
"Left Arm",
"Right Arm",
"LeftUpperArm",
"RightUpperArm",
}
addcommand(
"noarms",
"removes your arms",
0,
{},
function()
notify("Removing arms..")
local succ, err =
pcall(
function()
  for i,v in pairs(arms) do
	if plr.Character and plr.Character:FindFirstChild(v) then
	plr.Character[v]:Destroy()
	end
	end
end
)
if err then
  notify("Uh oh, something went wrong.")
end
end
)

addcommand(
"creeper",
"makes you a creeper",
0,
{},
function()
notify("Making you a creeper..")
local succ, err =
pcall(
function()
  for i,v in pairs(arms) do
	if plr.Character and plr.Character:FindFirstChild(v) then
	plr.Character[v]:Destroy()
	end
	end
  Player.Character.Head.Mesh:Destroy()
end
)
if err then
  notify("Uh oh, something went wrong.")
end
end
)

addcommand(
"blockhead",
"removes your heads mesh",
0,
{"nomeshhead"},
function()
local succ, err =
pcall(
function()
  Player.Character.Head.Mesh:Destroy()
end
)
if succ then
  notify("Destroyed mesh.")
else
  notify("Something went wrong..")
end
end
)

addcommand(
"nohats",
"removes your hats",
0,
{"removehats"},
function()
for _, hat in pairs(Player.Character:GetDescendants()) do
  if hat:IsA("Accessory") then
    hat.Handle.AccessoryWeld:Destroy()
    hat.Handle.Velocity = Vector3.new(math.huge,math.huge,math.huge)
  end
end
end
)

-- fencing only
if game.PlaceId == 12109643 then
addcommand(
"killall",
"Kills everyone.",
0,
{"spraykillall"},
function()
local Players = game:GetService("Players")
local Player = Player
local Character = Player.Character
local Humanoid = Character:FindFirstChildOfClass("Humanoid")
local RootPart = Humanoid.RootPart
local Handle = workspace:FindFirstChild("Handle")

if not Character or not Humanoid or not RootPart or not Handle or not Character:FindFirstChild("Right Arm") then return end

local Old = RootPart.CFrame

RootPart.CFrame = CFrame.new(0,8e9,0)

for i = 1,#Players:GetPlayers() - 1 do
    firetouchinterest(RootPart,Handle,0)
    firetouchinterest(RootPart,Handle,1)
    Character:WaitForChild("Spray").Parent = workspace
    game:GetService("RunService").Heartbeat:wait()
end
for _,x in next, workspace:GetChildren() do
    if x:IsA("Tool") and x.Name == "Spray" then
        firetouchinterest(RootPart,x.Handle,0)
    end
end

RootPart.Velocity = Vector3.new()
RootPart.CFrame = Old
repeat game:GetService("RunService").Heartbeat:wait() until Character:FindFirstChild("Spray")
wait(.25)
local NewHumanoid = Humanoid:Clone()
Humanoid:Destroy()
NewHumanoid.Parent = Character

NewHumanoid:UnequipTools()
repeat game:GetService("RunService").Heartbeat:wait() until not Character:FindFirstChild("Spray")
wait(.25)
for _,x in next, Player.Backpack:GetChildren() do
    if x:IsA("Tool") and x.Name == "Spray" then
        x.Parent = Character
        if Players:GetPlayers()[_] and Players:GetPlayers()[_].Character and Players:GetPlayers()[_].Character:FindFirstChildOfClass("Humanoid") and not Players:GetPlayers()[_].Character:FindFirstChildOfClass("Humanoid").Sit and Players:GetPlayers()[_].Character:FindFirstChildOfClass("Humanoid").Health > 0 and Players:GetPlayers()[_].Character:FindFirstChild("Right Arm") then
            firetouchinterest(x.Handle,Players:GetPlayers()[_].Character.PrimaryPart,0)
            firetouchinterest(x.Handle,Players:GetPlayers()[_].Character.PrimaryPart,1)
            game:GetService("RunService").Stepped:wait()
        end
    end
end
Player.Character = nil
NewHumanoid.Health = 0
end
)
end

addcommand(
"spotify",
"unlocks the spotify api",
0,
{"spoti"},
function()
if getgenv().apikey == nil then
  notify("No api key! Please apply one with spotikey.")
else
  notify("Unlocking api..")
end
_G.requests = {
  ["CurrentlyPlaying"] = {
    Url = "https://api.spotify.com/v1/me/player/currently-playing",
    Method = "GET",
    Headers = {
      ["Accept"] = "application/json",
      ["Authorization"] = "Bearer " .. apikey,
      ["Content-Type"] = "application/json"
    }
  },
  ["NextSong"] = {
    Url = "https://api.spotify.com/v1/me/player/next",
    Method = "POST",
    Headers = {
      ["Accept"] = "application/json",
      ["Authorization"] = "Bearer " .. apikey,
      ["Content-Type"] = "application/json"
    }
  },
  ["LastSong"] = {
    Url = "https://api.spotify.com/v1/me/player/previous",
    Method = "POST",
    Headers = {
      ["Accept"] = "application/json",
      ["Authorization"] = "Bearer " .. apikey,
      ["Content-Type"] = "application/json"
    }
  },
  ["Pause"] = {
    Url = "https://api.spotify.com/v1/me/player/pause",
    Method = "PUT",
    Headers = {
      ["Accept"] = "application/json",
      ["Authorization"] = "Bearer " .. apikey,
      ["Content-Type"] = "application/json"
    }
  },
  ["Play"] = {
    Url = "https://api.spotify.com/v1/me/player/play",
    Method = "PUT",
    Headers = {
      ["Accept"] = "application/json",
      ["Authorization"] = "Bearer " .. apikey,
      ["Content-Type"] = "application/json"
    }
  },
}

end
)

addcommand(
"spotinext",
"goes to the next song on spotify",
0,
{"spotifynext"},
function()
local succ,err = pcall(function()
syn.request(_G.requests["NextSong"])
end)
if err then
  notify("Spotify api not unlocked..")
end
end
)


addcommand(
"spotipause",
"pauses the song on spotify",
0,
{"spotifypause"},
function()
local succ,err = pcall(function()
syn.request(_G.requests["Pause"])
end)
if err then
  notify("Spotify api not unlocked..")
end
end
)

addcommand(
"spotiplay",
"plays/unpauses the song on spotify",
0,
{"spotifyplay"},
function()
local succ,err = pcall(function()
syn.request(_G.requests["Play"])
end)
if err then
  notify("Spotify api not unlocked..")
end
end
)


addcommand(
"spotilast",
"goes to the last song on spotify",
0,
{"spoti"},
function()
local succ,err = pcall(function()
syn.request(_G.requests["LastSong"])
end)
if err then
  notify("Spotify api not unlocked..")
end
end
)



addcommand(
"amongus",
"susifies you",
0,
{"susify", "amogus"},
function()
function weldit(part0, part1, offset)
  a0 = Instance.new("Attachment", part0)
  if offset then
    a0.Position = offset
  end
  a1 = Instance.new("Attachment", part1)
  a2 = Instance.new("Attachment", part0)
  part0.AlignPosition.Attachment0 = a0
  part0.AlignPosition.Attachment1 = a1
  part0.AlignOrientation.Attachment0 = a2
  part0.AlignOrientation.Attachment1 = a1
end
function align(part)
  alignPosition = Instance.new("AlignPosition", part)
  alignPosition.RigidityEnabled = false
  alignPosition.ApplyAtCenterOfMass = false
  alignPosition.MaxForce = 9e35
  alignPosition.MaxVelocity = 9e99
  alignPosition.ReactionForceEnabled = false
  alignPosition.Responsiveness = 9e99
  alignOr = Instance.new("AlignOrientation", part)
  alignOr.MaxTorque = 9e99
  alignOr.MaxAngularVelocity = 9e99
  alignOr.PrimaryAxisOnly = false
  alignOr.ReactionTorqueEnabled = false
  alignOr.Responsiveness = 200
  alignOr.RigidityEnabled = false
end
notify("Susifying you..")
local succ, err =
pcall(
function()
  for i, v in next, game:GetService("Players").LocalPlayer.Character:GetDescendants() do
    if v:IsA("BasePart") and v.Name ~= "HumanoidRootPart" then
      game:GetService("RunService").Heartbeat:connect(
      function()
        Player.Character["Left Arm"].Velocity = Vector3.new(0, 45.005, 0)
        Player.Character["Right Arm"].Velocity = Vector3.new(0, 45.005, 0)
      end
      )
    end
  end
  if Player.Character.Humanoid.RigType == Enum.HumanoidRigType.R6 then
    align(Player.Character["Left Arm"])
    align(Player.Character["Right Arm"])
    Player.Character["Torso"]["Right Shoulder"]:Destroy()
    weldit(
    Player.Character["Right Arm"],
    Player.Character.Torso,
    Vector3.new(0.3, 0, -1)
    )
    Player.Character["Torso"]["Left Shoulder"]:Destroy()
    weldit(
    Player.Character["Left Arm"],
    Player.Character.Torso,
    Vector3.new(-0.3, 0, -1)
    )
  elseif Player.Character.Humanoid.RigType == Enum.HumanoidRigType.R15 then
    notify("R15 only!")
  end
  Player.Character.Head.Mesh:Destroy()
end
)
if err then
  notify("Uh oh, something went wrong.")
end
end
)

addcommand(
"nolegs",
"removes your legs",
0,
{},
function()
notify("Removing legs..")
local succ, err =
pcall(
function()
  if Player.Character.Humanoid.RigType == Enum.HumanoidRigType.R6 then
    Player.Character["Left Leg"]:Destroy()
    Player.Character["Right Leg"]:Destroy()
  elseif Player.Character.Humanoid.RigType == Enum.HumanoidRigType.R15 then
    Player.Character["LeftUpperLeg"]:Destroy()
    Player.Character["RightUpperLeg"]:Destroy()
  end
end
)
if err then
  notify("Uh oh, something went wrong.")
end
end
)

addcommand(
"nolimbs",
"removes your limbs",
0,
{},
function()
notify("Removing limbs..")
local succ, err =
pcall(
function()
  if Player.Character.Humanoid.RigType == Enum.HumanoidRigType.R6 then
    Player.Character["Left Arm"]:Destroy()
    Player.Character["Right Arm"]:Destroy()
    Player.Character["Left Leg"]:Destroy()
    Player.Character["Right Leg"]:Destroy()
  elseif Player.Character.Humanoid.RigType == Enum.HumanoidRigType.R15 then
    Player.Character["LeftUpperArm"]:Destroy()
    Player.Character["RightUpperArm"]:Destroy()
    Player.Character["LeftUpperLeg"]:Destroy()
    Player.Character["RightUpperLeg"]:Destroy()
  end
end
)
if err then
  notify("Uh oh, something went wrong.")
end
end
)

addcommand(
"freezeanims",
"freezes animations",
0,
{"freezeanim"},
function()
notify("Freezing animations..")
local ActiveTracks = Player.Character.Humanoid:GetPlayingAnimationTracks()
for _, v in pairs(ActiveTracks) do
  v:AdjustSpeed(0)
end
end
)

addcommand(
"unfreezeanims",
"freezes animations",
0,
{"unfreezeanim"},
function()
notify("Unfreezing animations..")
local ActiveTracks = Player.Character.Humanoid:GetPlayingAnimationTracks()
for _, v in pairs(ActiveTracks) do
  v:AdjustSpeed(1)
end
end
)

addcommand(
"fakechat",
"fake chats as a user with specified message (you need to chat too)",
3,
{"falsechat"},
function(user,chat,ychat)
notify("Faking chat..")
local A_1   = ychat.."                                                                                                                                              ".."["..user.."]"..":".."".. " "..chat
local A_2   = "All"
local Event = game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest
Event:FireServer(A_1, A_2)
end
)


-- Changelog

local ScreenGui = Instance.new("ScreenGui")
local Changelog = Instance.new("Frame")
local Penumbra = Instance.new("ImageLabel")
local ImageLabel = Instance.new("ImageLabel")
local CMDTITLE = Instance.new("TextLabel")
local ImageLabel_2 = Instance.new("ImageLabel")
local MAOWQ = Instance.new("TextLabel")
local ImageLabel_3 = Instance.new("ImageLabel")
local Chanelog = Instance.new("TextLabel")

--Properties:

ScreenGui.Parent = game.CoreGui
ScreenGui.Name = "HBLOG"

Changelog.Name = "Changelog"
Changelog.Parent = ScreenGui
Changelog.AnchorPoint = Vector2.new(0.5, 0.5)
Changelog.BackgroundColor3 = Color3.fromRGB(5, 11, 24)
Changelog.Position = UDim2.new(0.499635637, 0, 0.499820173, 0)
Changelog.Size = UDim2.new(0, 479, 0, 288)
Changelog.ZIndex = 2
Changelog.Visible = false

Penumbra.Name = "Penumbra"
Penumbra.Parent = Changelog
Penumbra.Active = true
Penumbra.AnchorPoint = Vector2.new(0.5, 0.5)
Penumbra.BackgroundTransparency = 1.000
Penumbra.BorderSizePixel = 0
Penumbra.Position = UDim2.new(0.45726496, 0, 0.584302306, 1)
Penumbra.Size = UDim2.new(1, 18, 1, 18)
Penumbra.Image = "rbxassetid://1316045217"
Penumbra.ImageColor3 = Color3.fromRGB(0, 0, 0)
Penumbra.ImageTransparency = 0.880
Penumbra.ScaleType = Enum.ScaleType.Slice
Penumbra.SliceCenter = Rect.new(10, 10, 118, 118)

ImageLabel.Parent = Changelog
ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel.BackgroundTransparency = 1.000
ImageLabel.Position = UDim2.new(-0.0132315634, 0, 0.770409405, 0)
ImageLabel.Size = UDim2.new(0, 101, 0, 83)
ImageLabel.ZIndex = 2
ImageLabel.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel.ImageTransparency = 0.600

CMDTITLE.Name = "CMDTITLE"
CMDTITLE.Parent = Changelog
CMDTITLE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
CMDTITLE.BackgroundTransparency = 1.000
CMDTITLE.Position = UDim2.new(0.362217844, 0, 0.074537456, 0)
CMDTITLE.Size = UDim2.new(0, 131, 0, 36)
CMDTITLE.ZIndex = 2
CMDTITLE.Font = Enum.Font.GothamBlack
CMDTITLE.Text = "HOMEBREW ADMIN"
CMDTITLE.TextColor3 = Color3.fromRGB(255, 255, 255)
CMDTITLE.TextSize = 20.000

ImageLabel_2.Parent = Changelog
ImageLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel_2.BackgroundTransparency = 1.000
ImageLabel_2.Position = UDim2.new(0.16108036, 0, 0.810999811, 0)
ImageLabel_2.Size = UDim2.new(0, 88, 0, 61)
ImageLabel_2.ZIndex = 2
ImageLabel_2.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel_2.ImageTransparency = 0.800

MAOWQ.Name = "MAOWQ"
MAOWQ.Parent = Changelog
MAOWQ.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
MAOWQ.BackgroundTransparency = 1.000
MAOWQ.Position = UDim2.new(0.440408856, 0, 0.197908744, 0)
MAOWQ.Size = UDim2.new(0, 56, 0, 23)
MAOWQ.ZIndex = 2
MAOWQ.Font = Enum.Font.Gotham
MAOWQ.Text = "CHANGELOG //"
MAOWQ.TextColor3 = Color3.fromRGB(255, 255, 255)
MAOWQ.TextSize = 12.000

ImageLabel_3.Parent = Changelog
ImageLabel_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel_3.BackgroundTransparency = 1.000
ImageLabel_3.Position = UDim2.new(0.20083572, 0, 0.89956069, 0)
ImageLabel_3.Size = UDim2.new(0, 105, 0, 37)
ImageLabel_3.ZIndex = 2
ImageLabel_3.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel_3.ImageTransparency = 0.800

Chanelog.Name = "Chanelog"
Chanelog.Parent = Changelog
Chanelog.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Chanelog.BackgroundTransparency = 1.000
Chanelog.Position = UDim2.new(0.0921858922, 0, 0.276124328, 0)
Chanelog.Size = UDim2.new(0, 391, 0, 194)
Chanelog.ZIndex = 2
Chanelog.Font = Enum.Font.Gotham
Chanelog.Text = ""
Chanelog.TextColor3 = Color3.fromRGB(255, 255, 255)
Chanelog.TextScaled = true
Chanelog.TextSize = 12.000
Chanelog.TextWrapped = true

addcommand(
"2007anims",
"changes your characters animations to 2007 animations",
0,
{"2007anim"},
function()
loadstring(game:HttpGet(('https://raw.githubusercontent.com/mgamingpro/HomebrewAdmin/master/scripts/2007anims.lua'),true))()
end
)


addcommand(
"r15v2",
"gives you v2 r15 animations from 2016",
0,
{},
function()
if Player.Character.Humanoid.RigType == Enum.HumanoidRigType.R15 then
  notify("Loading V2 R15 Animations..")
  Player.Character.Animate:Destroy()
  local a = game:GetObjects("rbxassetid://6816103163")[1]
  local function b()
    local c = Instance.new("LocalScript", Close)
    c.Name = "Animate"
    c.Parent = Player.Character
    for d, e in next, a:GetDescendants() do
      if e:IsA("StringValue") then
        e.Parent = c
      end
    end
    function waitForChild(f, g)
      local h = nil
      local i = f:findFirstChild(g)
      if i then
        return i
      end
      while true do
        h = f.ChildAdded:wait()
        if h.Name == g then
          break
        end
      end
      return h
    end
    local j = c.Parent
    local k = waitForChild(j, "Humanoid")
    k.CameraOffset = Vector3.new(0, 0.5, 0)
    math.randomseed(tick())
    local l = {}
    function configureAnimationSet(m, n)
      if l[m] ~= nil then
        local o, p, q = pairs(l[m].connections)
        while true do
          local r, s = o(p, q)
          if r then
          else
            break
          end
          q = r
          s:disconnect()
        end
      end
      l[m] = {}
      l[m].count = 0
      l[m].totalWeight = 0
      l[m].connections = {}
      local t = c:FindFirstChild(m)
      if t ~= nil then
        table.insert(
        l[m].connections,
        t.ChildAdded:connect(
        function(u)
          configureAnimationSet(m, n)
        end
        )
        )
        table.insert(
        l[m].connections,
        t.ChildRemoved:connect(
        function(v)
          configureAnimationSet(m, n)
        end
        )
        )
        local w = 1
        local x, y, z = pairs(t:GetChildren())
        while true do
          local A, B = x(y, z)
          if A then
          else
            break
          end
          z = A
          if B:IsA("Animation") then
            table.insert(
            l[m].connections,
            B.Changed:connect(
            function(C)
              configureAnimationSet(m, n)
            end
            )
            )
            l[m][w] = {}
            l[m][w].anim = B
            local D = B:FindFirstChild("Weight")
            if D == nil then
              l[m][w].weight = 1
            else
              l[m][w].weight = D.Value
            end
            l[m].count = l[m].count + 1
            l[m].totalWeight = l[m].totalWeight + l[m][w].weight
            w = w + 1
          end
        end
      end
      if l[m].count <= 0 then
        local E, F, G = pairs(n)
        while true do
          local H, I = E(F, G)
          if H then
          else
            break
          end
          G = H
          l[m][H] = {}
          l[m][H].anim = Instance.new("Animation")
          l[m][H].anim.Name = m
          l[m][H].anim.AnimationId = I.id
          l[m][H].weight = I.weight
          l[m].count = l[m].count + 1
          l[m].totalWeight = l[m].totalWeight + I.weight
        end
      end
    end
    local J = {
      idle = {
        {id = "rbxasset://R15021216/idle_stretch.xml", weight = 1},
        {id = "rbxasset://R15021216/idle_look.xml", weight = 1},
        {id = "rbxasset://R15021216/idle.xml", weight = 9}
      },
      walk = {{id = "rbxasset://R15021216/run.xml", weight = 10}},
      run = {{id = "rbxasset://R15021216/run.xml", weight = 10}},
      jump = {{id = "rbxasset://R15021216/jump.xml", weight = 10}},
      fall = {{id = "rbxasset://R15021216/falling.xml", weight = 10}},
      climb = {{id = "rbxasset://R15021216/climb.xml", weight = 10}},
      sit = {{id = "http://www.roblox.com/asset/?id=393915321", weight = 10}},
      toolnone = {{id = "http://www.roblox.com/asset/?id=393915542", weight = 10}},
      toolslash = {{id = "http://www.roblox.com/asset/?id=393915542", weight = 10}},
      toollunge = {{id = "http://www.roblox.com/asset/?id=393915542", weight = 10}},
      wave = {{id = "http://www.roblox.com/asset/?id=393915710", weight = 10}},
      point = {{id = "http://www.roblox.com/asset/?id=393915866", weight = 10}},
      dance = {
        {id = "http://www.roblox.com/asset/?id=393916260", weight = 10},
        {id = "http://www.roblox.com/asset/?id=393916456", weight = 10},
        {id = "http://www.roblox.com/asset/?id=393916635", weight = 10}
      },
      dance2 = {
        {id = "http://www.roblox.com/asset/?id=393916791", weight = 10},
        {id = "http://www.roblox.com/asset/?id=393916989", weight = 10},
        {id = "http://www.roblox.com/asset/?id=393917195", weight = 10}
      },
      dance3 = {
        {id = "http://www.roblox.com/asset/?id=393917375", weight = 10},
        {id = "http://www.roblox.com/asset/?id=393917556", weight = 10},
        {id = "http://www.roblox.com/asset/?id=393917721", weight = 10}
      },
      laugh = {{id = "http://www.roblox.com/asset/?id=393916166", weight = 10}},
      cheer = {{id = "http://www.roblox.com/asset/?id=393916016", weight = 10}}
    }
    function scriptChildModified(K)
      local L = J[K.Name]
      if L ~= nil then
        configureAnimationSet(K.Name, L)
      end
    end
    c.ChildAdded:connect(scriptChildModified)
    c.ChildRemoved:connect(scriptChildModified)
    for M, N in pairs(J) do
      configureAnimationSet(M, N)
    end
    local O = ""
    local P = {
      wave = false,
      point = false,
      dance = true,
      dance2 = true,
      dance3 = true,
      laugh = false,
      cheer = false
    }
    local Q = nil
    local R = nil
    local S = nil
    function stopAllAnimations()
      local T = O
      if P[T] ~= nil then
        if P[T] == false then
          T = "idle"
        end
      end
      O = ""
      Q = nil
      if R ~= nil then
        R:disconnect()
      end
      if S ~= nil then
        S:Stop()
        S:Destroy()
        S = nil
      end
      return T
    end
    local U = 1
    function setAnimationSpeed(V)
      if V ~= U then
        U = V
        S:AdjustSpeed(U)
      end
    end
    function keyFrameReachedFunc(W)
      if W == "End" then
        local X = O
        if P[X] ~= nil then
          if P[X] == false then
            X = "idle"
          end
        end
        playAnimation(X, 0.15, k)
        setAnimationSpeed(U)
      end
    end
    function playAnimation(Y, Z, _)
      local a0 = math.random(1, l[Y].totalWeight)
      local a1 = 1
      while true do
        if l[Y][a1].weight < a0 then
        else
          break
        end
        a0 = a0 - l[Y][a1].weight
        a1 = a1 + 1
      end
      local a2 = l[Y][a1].anim
      if a2 ~= Q then
        if S ~= nil then
          S:Stop(Z)
          S:Destroy()
        end
        U = 1
        S = _:LoadAnimation(a2)
        S:Play(Z)
        O = Y
        Q = a2
        if R ~= nil then
          R:disconnect()
        end
        R = S.KeyframeReached:connect(keyFrameReachedFunc)
      end
    end
    local a3 = ""
    function toolKeyFrameReachedFunc(a4)
      if a4 == "End" then
        playToolAnimation(a3, 0, k)
      end
    end
    local a5 = nil
    local a6 = nil
    local a7 = nil
    function playToolAnimation(a8, a9, aa)
      local ab = math.random(1, l[a8].totalWeight)
      local ac = 1
      while true do
        if l[a8][ac].weight < ab then
        else
          break
        end
        ab = ab - l[a8][ac].weight
        ac = ac + 1
      end
      local ad = l[a8][ac].anim
      if a5 ~= ad then
        if a6 ~= nil then
          a6:Stop()
          a6:Destroy()
          a9 = 0
        end
        a6 = aa:LoadAnimation(ad)
        a6:Play(a9)
        a3 = a8
        a5 = ad
        a7 = a6.KeyframeReached:connect(toolKeyFrameReachedFunc)
      end
    end
    function stopToolAnimations()
      if a7 ~= nil then
        a7:disconnect()
      end
      a3 = ""
      a5 = nil
      if a6 ~= nil then
        a6:Stop()
        a6:Destroy()
        a6 = nil
      end
      return a3
    end
    local ae = "Standing"
    function onRunning(af)
      if 0.01 < af then
      else
        playAnimation("idle", 0.1, k)
        ae = "Standing"
        return
      end
      playAnimation("walk", 0.1, k)
      setAnimationSpeed(af / 15)
      ae = "Running"
    end
    function onDied()
      ae = "Dead"
    end
    local ag = 0
    function onJumping()
      playAnimation("jump", 0.1, k)
      ag = 0.31
      ae = "Jumping"
    end
    function onClimbing(ah)
      playAnimation("climb", 0.1, k)
      setAnimationSpeed(ah / 2)
      ae = "Climbing"
    end
    function onGettingUp()
      ae = "GettingUp"
    end
    function onFreeFall()
      if ag <= 0 then
        playAnimation("fall", 0.2, k)
      end
      ae = "FreeFall"
    end
    function onFallingDown()
      ae = "FallingDown"
    end
    function onSeated()
      ae = "Seated"
    end
    function onPlatformStanding()
      ae = "PlatformStanding"
    end
    function onSwimming(ai)
      if 0 < ai then
        ae = "Running"
        return
      end
      ae = "Standing"
    end
    function getTool()
      local aj, ak, al = ipairs(j:GetChildren())
      while true do
        local am, an = aj(ak, al)
        if am then
        else
          break
        end
        al = am
        if an.className == "Tool" then
          return an
        end
      end
      return nil
    end
    function getToolAnim(ao)
      local ap, aq, ar = ipairs(ao:GetChildren())
      while true do
        local as, at = ap(aq, ar)
        if as then
        else
          break
        end
        ar = as
        if at.Name == "toolanim" then
          if at.className == "StringValue" then
            return at
          end
        end
      end
      return nil
    end
    local au = "None"
    function animateTool()
      if au == "None" then
        playToolAnimation("toolnone", 0.1, k)
        return
      end
      if au == "Slash" then
        playToolAnimation("toolslash", 0, k)
        return
      end
      if au == "Lunge" then
      else
        return
      end
      playToolAnimation("toollunge", 0, k)
    end
    function moveSit()
      RightShoulder.MaxVelocity = 0.15
      LeftShoulder.MaxVelocity = 0.15
      RightShoulder:SetDesiredAngle(1.57)
      LeftShoulder:SetDesiredAngle(-1.57)
      RightHip:SetDesiredAngle(1.57)
      LeftHip:SetDesiredAngle(-1.57)
    end
    local av = 0
    local aw = 0
    function move(ax)
      av = ax
      if 0 < ag then
        ag = ag - (ax - av)
      end
      if ae == "FreeFall" then
        if ag <= 0 then
          playAnimation("fall", 0.2, k)
        else
          if ae == "Seated" then
            playAnimation("sit", 0.5, k)
            return
          end
          if ae == "Running" then
            playAnimation("walk", 0.1, k)
          elseif ae ~= "Dead" then
            if ae ~= "GettingUp" then
              if ae ~= "FallingDown" then
                if ae ~= "Seated" then
                  if ae == "PlatformStanding" then
                    stopAllAnimations()
                  end
                else
                  stopAllAnimations()
                end
              else
                stopAllAnimations()
              end
            else
              stopAllAnimations()
            end
          else
            stopAllAnimations()
          end
        end
      else
        if ae == "Seated" then
          playAnimation("sit", 0.5, k)
          return
        end
        if ae == "Running" then
          playAnimation("walk", 0.1, k)
        elseif ae ~= "Dead" then
          if ae ~= "GettingUp" then
            if ae ~= "FallingDown" then
              if ae ~= "Seated" then
                if ae == "PlatformStanding" then
                  stopAllAnimations()
                end
              else
                stopAllAnimations()
              end
            else
              stopAllAnimations()
            end
          else
            stopAllAnimations()
          end
        else
          stopAllAnimations()
        end
      end
      local ay = getTool()
      if ay then
      else
        stopToolAnimations()
        au = "None"
        a5 = nil
        aw = 0
        return
      end
      animStringValueObject = getToolAnim(ay)
      if animStringValueObject then
        au = animStringValueObject.Value
        animStringValueObject.Parent = nil
        aw = ax + 0.3
      end
      if aw < ax then
        aw = 0
        au = "None"
      end
      animateTool()
    end
    k.Died:connect(onDied)
    k.Running:connect(onRunning)
    k.Jumping:connect(onJumping)
    k.Climbing:connect(onClimbing)
    k.GettingUp:connect(onGettingUp)
    k.FreeFalling:connect(onFreeFall)
    k.FallingDown:connect(onFallingDown)
    k.Seated:connect(onSeated)
    k.PlatformStanding:connect(onPlatformStanding)
    k.Swimming:connect(onSwimming)
    Player.Chatted:connect(
    function(az)
      local aA = ""
      if string.sub(az, 1, 3) == "/e " then
        aA = string.sub(az, 4)
      elseif string.sub(az, 1, 7) == "/emote " then
        aA = string.sub(az, 8)
      end
      if ae == "Standing" and P[aA] ~= nil then
        playAnimation(aA, 0.1, k)
      end
    end
    )
    local aB = game:service("RunService")
    playAnimation("idle", 0.1, k)
    ae = "Standing"
    while j.Parent ~= nil do
      local aC, aD = wait(0.1)
      move(aD)
    end
  end
  coroutine.wrap(b)()
else
  notify("Must be R15.")
end
end
)
addcommand(
"whisper",
"sends a pm to specified player with specified text",
2,
{},
function(player, text)
user = getPlayer(player)
plr = user.Name
notify("Whispering to " .. plr .. ", " .. text .. ".")
whisper(user, text)
end
)

addcommand(
"tornado",
"Tornadoes specified player [TOOL REQUIRED]",
1,
{"cuff"},
function(player)
Target = player
local function Message(MTitle, MText, Time)
  -- game:GetService("StarterGui"):SetCore("SendNotification",{Title = MTitle;Text = MText;Duration = Time;})
  notify(MText)
end

if not getPlayer(Target) then
  return Message("Error", ">   Player does not exist.", 5)
end

repeat
  game:GetService("RunService").Heartbeat:wait()
until getPlayer(Target).Character and getPlayer(Target).Character:FindFirstChildOfClass("Humanoid").Health > 0 or
not getPlayer(Target)

local Player = game:GetService("Players").LocalPlayer
local Character = Player.Character
local Humanoid
local HumanoidRootPart
local Torso
local Tool
local Handle

local TPlayer = getPlayer(Target)
local TCharacter = TPlayer.Character
local THumanoid
local THumanoidRootPart
local TTorso

if Character:FindFirstChild("HumanoidRootPart") then
  HumanoidRootPart = Character.HumanoidRootPart
end
if Character:FindFirstChild("Torso") then
  Torso = Character.Torso
end
if Character:FindFirstChildOfClass("Humanoid") then
  Humanoid = Character:FindFirstChildOfClass("Humanoid")
end
if Character:FindFirstChildOfClass("Tool") then
  Tool = Character:FindFirstChildOfClass("Tool")
elseif Player.Backpack:FindFirstChildOfClass("Tool") and Humanoid then
  Tool = Player.Backpack:FindFirstChildOfClass("Tool")
  Humanoid:EquipTool(Player.Backpack:FindFirstChildOfClass("Tool"))
end
if Tool and Tool:FindFirstChild("Handle") then
  Handle = Tool.Handle
end
if TCharacter:FindFirstChild("HumanoidRootPart") then
  THumanoidRootPart = TCharacter.HumanoidRootPart
end
if TCharacter:FindFirstChild("Torso") then
  TTorso = TCharacter.Torso
elseif TCharacter:FindFirstChild("UpperTorso") then
  TTorso = TCharacter.UpperTorso
end
if TCharacter:FindFirstChildOfClass("Humanoid") then
  THumanoid = Character:FindFirstChildOfClass("Humanoid")
end
if not HumanoidRootPart then
  Message("Error", ">   Missing HumanoidRootPart, Trying Torso.", 5)
  wait(1)
  if Torso then
    Message("Succes", ">   Torso found.", 5)
    wait(1)
  else
    Message("Error", ">   Missing Torso")
    return
  end
end
if Humanoid.RigType == Enum.HumanoidRigType.R15 then
  Message("Error", ">   This command doesn't work on R15.", 5)
  wait(1)
  return
end
if not Tool then
  Message("Error", ">   You have no tools.", 5)
  wait(1)
  return
end
if not Handle then
  Message("Error", ">   Tool doesn't have handle.", 5)
  wait(1)
  return
end
if not THumanoidRootPart then
  Message("Error", ">   Missing HumanoidRootPart on Target, Trying Torso.", 5)
  wait(1)
  if Torso then
    Message("Succes", ">   Torso found on Target.", 5)
    wait(1)
  else
    Message("Error", ">   Missing Torso on Target", 5)
    return
  end
end

Humanoid:Destroy()
local NewHumanoid = Instance.new("Humanoid", Character)
NewHumanoid:UnequipTools()
NewHumanoid:EquipTool(Tool)
Tool.Parent = workspace

repeat
  Tool.Grip = CFrame.new()
  Tool.Grip = Handle.CFrame:ToObjectSpace(TTorso.CFrame):Inverse()
  firetouchinterest(Handle, TTorso, 0)
  firetouchinterest(Handle, TTorso, 1)
  game:GetService("RunService").Heartbeat:wait()
until Tool.Parent ~= Character
NewHumanoid.WalkSpeed = 30
end
)

addcommand(
"tkill",
"kills specified player [TOOL REQUIRED]",
1,
{"kill"},
function(player)
Target = player
local function Message(MTitle, MText, Time)
  -- game:GetService("StarterGui"):SetCore("SendNotification",{Title = MTitle;Text = MText;Duration = Time;})
  notify(MText)
end

if not getPlayer(Target) then
  return Message("Error", ">   Player does not exist.", 5)
end

repeat
  game:GetService("RunService").Heartbeat:wait()
until getPlayer(Target).Character and getPlayer(Target).Character:FindFirstChildOfClass("Humanoid").Health > 0 or
not getPlayer(Target)

local Player = game:GetService("Players").LocalPlayer
local Character = Player.Character
local Humanoid
local HumanoidRootPart
local Torso
local Tool
local Handle

local TPlayer = getPlayer(Target)
local TCharacter = TPlayer.Character
local THumanoid
local THumanoidRootPart
local TTorso

if Character:FindFirstChild("HumanoidRootPart") then
  HumanoidRootPart = Character.HumanoidRootPart
end
if Character:FindFirstChild("Torso") then
  Torso = Character.Torso
end
if Character:FindFirstChildOfClass("Humanoid") then
  Humanoid = Character:FindFirstChildOfClass("Humanoid")
end
if Character:FindFirstChildOfClass("Tool") then
  Tool = Character:FindFirstChildOfClass("Tool")
elseif Player.Backpack:FindFirstChildOfClass("Tool") and Humanoid then
  Tool = Player.Backpack:FindFirstChildOfClass("Tool")
  Humanoid:EquipTool(Player.Backpack:FindFirstChildOfClass("Tool"))
end
if Tool and Tool:FindFirstChild("Handle") then
  Handle = Tool.Handle
end
if TCharacter:FindFirstChild("HumanoidRootPart") then
  THumanoidRootPart = TCharacter.HumanoidRootPart
end
if TCharacter:FindFirstChild("Torso") then
  TTorso = TCharacter.Torso
elseif TCharacter:FindFirstChild("UpperTorso") then
  TTorso = TCharacter.UpperTorso
end
if TCharacter:FindFirstChildOfClass("Humanoid") then
  THumanoid = Character:FindFirstChildOfClass("Humanoid")
end
if not HumanoidRootPart then
  Message("Error", ">   Missing HumanoidRootPart, Trying Torso.", 5)
  wait(1)
  if Torso then
    Message("Succes", ">   Torso found.", 5)
    wait(1)
  else
    Message("Error", ">   Missing Torso")
    return
  end
end
if Humanoid.RigType == Enum.HumanoidRigType.R15 then
  Message("Error", ">  Please use kill2 on r15.", 5)
  local cmd = getCommand("kill2") cmd.command(unpack(TPlayer))
  wait(1)
  return
end
if not Tool then
  Message("Error", ">   You have no tools.", 5)
  wait(1)
  return
end
if not Handle then
  Message("Error", ">   Tool doesn't have handle.", 5)
  wait(1)
  return
end
if not THumanoidRootPart then
  Message("Error", ">   Missing HumanoidRootPart on Target, Trying Torso.", 5)
  wait(1)
  if Torso then
    Message("Succes", ">   Torso found on Target.", 5)
    wait(1)
  else
    Message("Error", ">   Missing Torso on Target", 5)
    return
  end
end

Humanoid:Destroy()
local NewHumanoid = Instance.new("Humanoid", Character)
NewHumanoid:UnequipTools()
NewHumanoid:EquipTool(Tool)
Tool.Parent = workspace

repeat
  Tool.Grip = CFrame.new()
  Tool.Grip = Handle.CFrame:ToObjectSpace(TTorso.CFrame):Inverse()
  firetouchinterest(Handle, TTorso, 0)
  firetouchinterest(Handle, TTorso, 1)
  game:GetService("RunService").Heartbeat:wait()
until Tool.Parent ~= Character
Player.Character = nil
NewHumanoid.Health = 0
end
)

addcommand(
"antifling",
"prevents people from flinging you but you keep collisions with objects",
0,
{},
function()
notify("Changing collisions..")
plrs = Players
function nocollision(prt, plr)
  for i, v in pairs(plr:GetDescendants()) do
    if v:IsA("BasePart") then
      e = Instance.new("NoCollisionConstraint", v)
      e.Part0 = v
      e.Part1 = prt
    end
  end
end
for i, yes in pairs(Player.Character:GetDescendants()) do
  if yes:IsA("BasePart") then
    if yes:IsA("BasePart") then
      for i, v in pairs(plrs:GetDescendants()) do
        if v:IsA("Player") then
          nocollision(yes, v.Character)
        end
      end
    end
  end
end
end
)

addcommand(
"unantifling",
"gain back normal collisions",
0,
{},
function()
notify("Giving back normal collisions..")
for i, v in pairs(workspace:GetDescendants()) do
  if v:IsA("NoCollisionConstraint") then
    v:Destroy()
  end
end
end
)
addcommand(
"anim",
"plays an animation",
1,
{"loadanim"},
function(animid)
Animate = Player.Character.Animate
Anim = Instance.new("Animation")
rbxasset = true
local suc, err =
pcall(
function()
  animid = Animate:FindFirstChild(animid):FindFirstChildOfClass("Animation").AnimationId
end
)
if suc then
  rbxasset = false
end
print(animid)
if rbxasset == true then
  notify("Playing animation id " .. animid .. "!")
  Anim.AnimationId = ("rbxassetid://" .. animid)
else
  notify("Playing animation id" .. animid .. "!")
  Anim.AnimationId = (animid)
end
Hi = Player.Character.Humanoid:LoadAnimation(Anim)
Hi:Play()
Hi:AdjustSpeed(1)
end
)
addcommand(
"dance",
"plays a dance animation",
0,
{},
function()
local humanoid = game:GetService("Players").LocalPlayer.Character.Humanoid
Anim = Instance.new("Animation")
if humanoid.RigType == Enum.HumanoidRigType.R15 then
  r15dances = {4555808220, 4555782893, 3333432454, 4049037604}
  local value = math.random(1, #r15dances)
  picked_value = r15dances[value]
else
  r6dances = {33796059, 429730430, 429730430, 45834924}
  local value = math.random(1, #r6dances)
  picked_value = r6dances[value]
end
notify("Playing dance animation! ID: " .. picked_value)
Anim.AnimationId = ("rbxassetid://" .. picked_value)
Hi = Player.Character.Humanoid:LoadAnimation(Anim)
Hi:Play()
Hi:AdjustSpeed(1)
end
)

addcommand(
"undance",
"stops the dance animation",
0,
{},
function()
notify("Undancing..")
local ActiveTracks = Player.Character.Humanoid:GetPlayingAnimationTracks()
for _, v in pairs(ActiveTracks) do
  v:Stop()
end
end
)

addcommand(
"ui",
"changes ui to one of options",
1,
{"changeui"},
function(name)
if name == "v4" then
  ToCustomUI()
  loadstring(
  game:HttpGetAsync("https://raw.githubusercontent.com/mgamingpro/HomebrewAdmin/master/uis/v4hbadmin.lua")
  )()
elseif name == "normal" then
  ToCustomUI()
  createui()
 elseif name == "destroy" then
  ToCustomUI()
 elseif name == "custom" then
  ToCustomUI()
end
end
)

addcommand(
"stopanims",
"stops the current playing anim tracks",
0,
{"stoptracks"},
function()
notify("Stopping animations..")
local ActiveTracks = Player.Character.Humanoid:GetPlayingAnimationTracks()
for _, v in pairs(ActiveTracks) do
  v:Stop()
end
end
)

addcommand(
"chat",
"chats specified message",
1,
{},
function(msg)
notify("Chatting " .. msg .. "!")
wait()
game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer("" .. msg, "All")
end
)

addcommand(
"loopchat",
"loop chats specified message",
1,
{},
function(msg)
notify("Loop chatting " .. msg .. "!")
wait()
_G.chattin = true
chattin =
game:GetService("RunService").Heartbeat:connect(
function()
  if _G.chattin == true then
    game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(
    "" .. msg,
    "All"
    )
  else
    chattin:Disconnect()
  end
end
)
end
)

addcommand(
"unloopchat",
"unloop chats the previous message",
0,
{},
function()
notify("Unloop chatting!")
_G.chattin = false
end
)
addcommand(
"animspeed",
"adjusts the current animation's speed",
1,
{"anispeed"},
function(Speed)
notify("Adjusting speed..")
local ActiveTracks = Player.Character.Humanoid:GetPlayingAnimationTracks()
for _, v in pairs(ActiveTracks) do
  v:AdjustSpeed(Speed)
end
end
)

addcommand(
"music",
"players music [clientsided]",
1,
{},
function(id)
notify("Playing " .. id)
music = Instance.new("Sound", Player.Character.HumanoidRootPart)
music.Volume = 100
music.TimePosition = 0
music.PlaybackSpeed = 1
music.Pitch = 1
music.SoundId = ("rbxassetid://" .. id)
music.Name = "wrecked"
music.Looped = true
music:Play()
end
)

addcommand(
"nomusic",
"stops playing music",
0,
{"unmusic"},
function()
local succ, err =
pcall(
function()
  Player.Character.HumanoidRootPart.wrecked:Destroy()
end
)
if succ then
  notify("Stoped playing music.")
else
  notify("You aren't playing music!")
end
end
)

addcommand(
"changeprefix",
"changes your prefix to specified key",
1,
{"newprefix", "prefixchange","prefix"},
function(symbol)
if (symbol:match("%A")) then
  notify("Prefix set to: " .. symbol)
  prefix = symbol
  fireui()
  preffire()
else
  notify("Must be a symbol!")
end
end
)

addcommand(
"spotikey",
"changes your spotify api key to specified text",
1,
{"spotifykey", "spotifyapikey"},
function(k)
notify("Updating key.. (renew after an hour)")
keyfire(k)
end
)

addcommand(
"rj",
"rejoins your game",
0,
{"rejoin"},
function()
count = #Players:getPlayers()
if count <= 1 then
  game:GetService("TeleportService"):Teleport(game.PlaceId, Player)
else
  game:GetService("TeleportService"):TeleportToPlaceInstance(
  game.PlaceId,
  game.JobId,
  Player
  )
end
end
)

addcommand(
"banish",
"banishes player [needs tool]",
1,
{"punish", "stuckvoid"},
function(name)
user = getPlayer(name)
plr = user.name
notify("Banishing " .. plr .. "!")
Target = plr
Player.Character.Humanoid.Name = 1
local l = Player.Character["1"]:Clone()
l.Parent = Player.Character
l.Name = "Humanoid"
wait()
Player.Character["1"]:Destroy()
game.Workspace.CurrentCamera.CameraSubject = Player.Character
Player.Character.Animate.Disabled = true
wait()
Player.Character.Animate.Disabled = false
Player.Character.Humanoid.DisplayDistanceType = "None"
for i, v in pairs(game:GetService "Players".LocalPlayer.Backpack:GetChildren()) do
  Player.Character.Humanoid:EquipTool(v)
end
wait()
Player.Character.HumanoidRootPart.CFrame =
Players[Target].Character.HumanoidRootPart.CFrame
wait()
Player.Character.HumanoidRootPart.CFrame =
Players[Target].Character.HumanoidRootPart.CFrame
wait()
Player.Character.HumanoidRootPart.CFrame =
CFrame.new(Vector3.new(-100000, 1000000000000000000000, -100000))
wait()
local prt = Instance.new("Model", workspace)
Instance.new("Part", prt).Name = "Torso"
Instance.new("Part", prt).Name = "Head"
Instance.new("Humanoid", prt).Name = "Humanoid"
Player.Character = prt
end
)

addcommand(
"void",
"voids player [needs tool]",
1,
{"kill2"},
function(name)
user = getPlayer(name)
plr = user.name
notify("Voiding " .. plr .. "!")
Target = plr
Player.Character.Humanoid.Name = 1
local l = Player.Character["1"]:Clone()
l.Parent = Player.Character
l.Name = "Humanoid"
wait()
Player.Character["1"]:Destroy()
game.Workspace.CurrentCamera.CameraSubject = Player.Character
Player.Character.Animate.Disabled = true
wait()
Player.Character.Animate.Disabled = false
Player.Character.Humanoid.DisplayDistanceType = "None"
for i, v in pairs(game:GetService "Players".LocalPlayer.Backpack:GetChildren()) do
  Player.Character.Humanoid:EquipTool(v)
end
wait()
Player.Character.HumanoidRootPart.CFrame =
Players[Target].Character.HumanoidRootPart.CFrame
wait()
Player.Character.HumanoidRootPart.CFrame =
Players[Target].Character.HumanoidRootPart.CFrame
wait()
Player.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(-100000, -100, -100000))
wait()
local prt = Instance.new("Model", workspace)
Instance.new("Part", prt).Name = "Torso"
Instance.new("Part", prt).Name = "Head"
Instance.new("Humanoid", prt).Name = "Humanoid"
Player.Character = prt
end
)

addcommand(
"unbanish",
"unbanishes player [needs tool]",
1,
{"unpunish", "unstuckvoid"},
function(name)
user = getPlayer(name)
plr = user.name
notify("Unbanishing " .. plr .. "!")
Target = plr
Player.Character.Humanoid.Name = 1
local l = Player.Character["1"]:Clone()
l.Parent = Player.Character
l.Name = "Humanoid"
wait()
Player.Character["1"]:Destroy()
game.Workspace.CurrentCamera.CameraSubject = Player.Character
Player.Character.Animate.Disabled = true
wait()
Player.Character.Animate.Disabled = false
Player.Character.Humanoid.DisplayDistanceType = "None"
for i, v in pairs(game:GetService "Players".LocalPlayer.Backpack:GetChildren()) do
  Player.Character.Humanoid:EquipTool(v)
end
wait()
Player.Character.HumanoidRootPart.CFrame =
Players[Target].Character.HumanoidRootPart.CFrame
wait()
Player.Character.HumanoidRootPart.CFrame =
Players[Target].Character.HumanoidRootPart.CFrame
wait()
Player.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(0, 0, 0))
wait()
local prt = Instance.new("Model", workspace)
Instance.new("Part", prt).Name = "Torso"
Instance.new("Part", prt).Name = "Head"
Instance.new("Humanoid", prt).Name = "Humanoid"
Player.Character = prt
end
)

addcommand(
"freefall",
"freefalls player [needs tool]",
1,
{"skydive"},
function(name)
user = getPlayer(name)
plr = user.name
notify("Freefalling " .. plr .. "!")
Target = plr
Player.Character.Humanoid.Name = 1
local l = Player.Character["1"]:Clone()
l.Parent = Player.Character
l.Name = "Humanoid"
wait()
Player.Character["1"]:Destroy()
game.Workspace.CurrentCamera.CameraSubject = Player.Character
Player.Character.Animate.Disabled = true
wait()
Player.Character.Animate.Disabled = false
Player.Character.Humanoid.DisplayDistanceType = "None"
for i, v in pairs(game:GetService "Players".LocalPlayer.Backpack:GetChildren()) do
  Player.Character.Humanoid:EquipTool(v)
end
wait()
Player.Character.HumanoidRootPart.CFrame =
Players[Target].Character.HumanoidRootPart.CFrame
wait()
Player.Character.HumanoidRootPart.CFrame =
Players[Target].Character.HumanoidRootPart.CFrame
wait()
Player.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(0, 5000, 0))
wait()
local prt = Instance.new("Model", workspace)
Instance.new("Part", prt).Name = "Torso"
Instance.new("Part", prt).Name = "Head"
Instance.new("Humanoid", prt).Name = "Humanoid"
Player.Character = prt
end
)

addcommand(
"fly",
"makes your character fly",
0,
{},
function()
notify("Flying character..")
getgenv().Flying = true

local function Fly()
  Flying = true
  local Speed = 0
  local keys = {a = false, d = false, w = false, s = false}
  local Part = Instance.new("Part")
  local Weld = Instance.new("Weld", Part)
  Weld.Part0 = Part
  local Player = game:GetService("Players").LocalPlayer
  local Character = Player.Character
  repeat
    game:GetService("RunService").Heartbeat:wait()
  until Character:FindFirstChildOfClass("Humanoid")
  local HumanoidRootPart = Character.Humanoid.RootPart
  Part.Parent = workspace
  Weld.Parent = Part
  Part.Size = HumanoidRootPart.Size
  Part.CanCollide = false
  Part.Transparency = 1
  Weld.Part1 = HumanoidRootPart

  local pos = Instance.new("BodyPosition", Part)
  local gyro = Instance.new("BodyGyro", Part)

  pos.Name = "homebrew admin"
  gyro.Name = "winning"
  pos.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
  pos.Position = HumanoidRootPart.Position
  gyro.MaxTorque = Vector3.new(9e9, 9e9, 9e9)
  gyro.CFrame = HumanoidRootPart.CFrame

  local UserInputService = game:GetService("UserInputService")

  local ConnectA =
  UserInputService.InputBegan:Connect(
  function(Input, GameProcess)
    if not GameProcess then
      if Input.KeyCode == Enum.KeyCode.W then
        keys.w = true
      elseif Input.KeyCode == Enum.KeyCode.S then
        keys.s = true
      elseif Input.KeyCode == Enum.KeyCode.A then
        keys.a = true
      elseif Input.KeyCode == Enum.KeyCode.D then
        keys.d = true
      end
    end
  end
  )

  local ConnectB =
  UserInputService.InputEnded:Connect(
  function(Input, GameProcess)
    if not GameProcess then
      if Input.KeyCode == Enum.KeyCode.W then
        keys.w = false
      elseif Input.KeyCode == Enum.KeyCode.S then
        keys.s = false
      elseif Input.KeyCode == Enum.KeyCode.A then
        keys.a = false
      elseif Input.KeyCode == Enum.KeyCode.D then
        keys.d = false
      end
    end
  end
  )

  repeat
    game:GetService("RunService").Heartbeat:wait()
    Character:FindFirstChildOfClass("Humanoid").PlatformStand = true
    local new = gyro.cframe - gyro.cframe.p + pos.position
    if not keys.w and not keys.s and not keys.a and not keys.d then
      Speed = 1
    end

    if keys.w then
      new = new + workspace.CurrentCamera.CoordinateFrame.lookVector * Speed
      Speed = Speed + 0.01
    end

    if keys.s then
      new = new - workspace.CurrentCamera.CoordinateFrame.lookVector * Speed
      Speed = Speed + 0.01
    end

    if keys.d then
      new = new * CFrame.new(Speed, 0, 0)
      Speed = Speed + 0.01
    end

    if keys.a then
      new = new * CFrame.new(-Speed, 0, 0)
      Speed = Speed + 0.01
    end

    if Speed > 5 then
      Speed = 5
    end

    pos.position = new.p

    if keys.w then
      gyro.cframe = workspace.CurrentCamera.CoordinateFrame
    elseif keys.s then
      gyro.cframe = workspace.CurrentCamera.CoordinateFrame
    else
      gyro.cframe = workspace.CurrentCamera.CoordinateFrame
    end
  until not Flying

  if gyro then
    gyro:Destroy()
  end
  if pos then
    pos:Destroy()
  end
  Part:Destroy()
  Character:FindFirstChildOfClass("Humanoid").PlatformStand = false
  Speed = 0
  ConnectA:Disconnect()
  ConnectB:Disconnect()
end
Fly()
end
)

addcommand(
"unfly",
"makes your character unfly",
0,
{},
function()
Flying = false
notify("Unflying character..")
end
)

addcommand(
"speed",
"manipulates your humanoids speed",
1,
{"ws"},
function(speed)
notify("Changing humanoid speed to " .. speed .. "!")
Player.Character.Humanoid.WalkSpeed = speed
end
)

addcommand(
"jp",
"manipulates your humanoids jump power",
1,
{"jumppower"},
function(power)
notify("Changing humanoid jump power to " .. power .. "!")
Player.Character.Humanoid.UseJumpPower = true
Player.Character.Humanoid.JumpPower = power
end
)


addcommand(
"totalcmds",
"notifies total cmds",
0,
{},
function()
notify("Total of: " .. #commands .. " commands in version " .. '"' .. VERSION .. '"' .. "!")
end
)

addcommand(
"currentver",
"notifies current version",
0,
{"version"},
function()
notify("Current Version is " .. '"' .. VERSION .. '"' .. "!")
end
)

addcommand(
"admin",
"admins specified user",
1,
{"op", "whitelist"},
function(user)
local suc, err =
pcall(
function()
  user = getPlayer(user)
end
)
if err then
  notify("That player doesn't exist!")
else
end
_G.addadmin(user.Name)
end
)
addcommand(
"unadmin",
"removes admin from specified user",
1,
{"deop", "unwhitelist"},
function(user)
user = getPlayer(user)
_G.removeadmin(user.Name)
pcall(
function()
  whisper(user, "[HA] Your access to homebrew admin has been removed.")
end
)
end
)

addcommand(
"goto",
"teleports to specified user",
1,
{"tpto"},
function(user)
user = getPlayer(user)
plr = user.Name
notify("Going to " .. plr .. "!")
targ = workspace:FindFirstChild(plr)
Player.Character:SetPrimaryPartCFrame(targ:FindFirstChildOfClass("Part").CFrame)
end
)

addcommand(
"realname",
"gets the real username of target",
1,
{"rname","getname"},
function(user)
pl = getPlayer(user)
notify(user.."'s real name is "..pl.."!")
end
)


addcommand(
"dpos",
"Teleports to the last place you died",
0,
{"deathpoint", "oldpos"},
function()
dpos = _G.spawn
local suc, err =
pcall(
function()
  dp = _G.spawn.X .. "  " .. _G.spawn.Y, "  " .. _G.spawn.Z
end
)
if suc then
  notify("Teleporting to " .. dp .. "!")
  Player.Character:SetPrimaryPartCFrame(dpos)
else
  notify("You have not died yet!")
end
end
)
addcommand(
"loopgoto",
"loop teleports to specified user",
1,
{"looptpto"},
function(user)
user = getPlayer(user)
plr = user.Name
notify("Loop-going to " .. plr .. "!")
targ = workspace:FindFirstChild(plr)
_G.looping = true
loopin =
game:GetService("RunService").Heartbeat:connect(
function()
  if _G.looping == true then
    Player.Character:SetPrimaryPartCFrame(targ.HumanoidRootPart.CFrame)
  else
    loopin:Disconnect()
  end
end
)
end
)

addcommand(
"noclip",
"turns off collisions for your bodyparts",
0,
{"nocol"},
function(user)
if Player.Character.HumanoidRootPart.CanCollide == false then
  notify("You are already noclipped!")
else
  notify("Noclipping..")
end
local function nocl()
  for _, part in pairs(Player.Character:GetDescendants()) do
    if part:IsA("BasePart") and part.CanCollide == true then
      part.CanCollide = false
    end
  end
end
connectcl = game:GetService("RunService").Stepped:Connect(nocl)
end
)
addcommand(
"clip",
"turns on collisions for your bodyparts",
0,
{"col"},
function(user)
if connectcl then
  notify("Clipping..")
  connectcl:Disconnect()
else
  notify("You are already clipped!")
end
end
)
addcommand(
"unloopgoto",
"unloop teleports to specified user",
0,
{"unlooptpto"},
function()
notify("Unlooping " .. "!")
_G.looping = false
end
)

local function getCommand(name)
for _, command in pairs(commands) do
  if command.name == name then
    return command
  end
  for _, aliase in pairs(command.aliases) do
    if aliase == name then
      return command
    end
  end
end
end

function _G.addadmin(name)
user = getPlayer(name)
admined = false
if table.find(admins, Players[name].UserId) then
  notify(name .. " is already an admin!")
  admined = true
else
  local suc, err =
  pcall(
  function()
    table.insert(admins, Players[name].UserId)
  end
  )
  pcall(
  function()
    if suc then
      if not name == Player.Name then
        notify("Successfully whitelisted " .. name .. "!")
      end
      whisper(user, "[HA] You have been given access to homebrew admin commands.")
    else
      notify("Couldn't whitelist " .. name .. "!")
    end
  end
  )
end
connection =
Players[name].Chatted:Connect(
function(Message)
  if not table.find(admins, Players[name].UserId) then
    connection:Disconnect()
  else
    fl = string.sub(Message, 1, 1)
    if fl == prefix then
      NewMessage = Message:sub(2)
      args = NewMessage:split(" ")
    end
    if not args then
      return
    end
    if getCommand(args[1]) then
      local cmd = getCommand(args[1])
      table.remove(args, 1)
      pcall(function()
        cmd.command(unpack(args))
      end)
    end
  end
end
)
end

function _G.removeadmin(name)
local suc, err =
pcall(
function()
  table.remove(admins, table.find(admins, Players[name].UserId))
end
)
if suc then
  notify("Removed whitelist from " .. name .. "!")
else
  notify("There was an error while trying to remove admin from " .. name .. ".")
end
end

_G.addadmin(Player.Name)

_G.enterframe = function(meme)
meme.FocusLost:connect(
function(enterPressed)
if enterPressed then
  args = meme.Text:split(" ")
  if getCommand(args[1]) then
    local cmd = getCommand(args[1])
    table.remove(args, 1)
    pcall(function()
      cmd.command(unpack(args))
    end)
  end
end
end
)
end

if _G.CustomUI == false then
function createui()
    


-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local Frame_2 = Instance.new("Frame")
local UIGradient = Instance.new("UIGradient")
local TextLabel = Instance.new("TextLabel")
local Frame_3 = Instance.new("ImageLabel")
local TextLabel_2 = Instance.new("TextLabel")
local Frame_4 = Instance.new("ImageLabel")
local TextBox = Instance.new("TextBox")
local PenumbraShadow = Instance.new("ImageLabel")
local Frame_5 = Instance.new("Frame")
local TextLabel_3 = Instance.new("TextLabel")
local PenumbraShadow_2 = Instance.new("ImageLabel")
local TextLabel_4 = Instance.new("TextLabel")
local TextLabel_5 = Instance.new("TextLabel")
local ImageLabel = Instance.new("ImageLabel")
local ImageLabel_2 = Instance.new("ImageLabel")

--Properties:

ScreenGui.Parent = game.CoreGui
ScreenGui.Name = "HBADMIN"
Frame.AnchorPoint = Vector2.new(.5, .5)
Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(5, 11, 24)
Frame.BorderColor3 = Color3.fromRGB(27, 42, 53)
Frame.Position = UDim2.new(.5, 0, .875, 0)
Frame.Size = UDim2.new(0, 740, 0, 41)

Frame_2.Parent = Frame
Frame_2.BackgroundColor3 = Color3.fromRGB(177, 19, 229)
Frame_2.BorderColor3 = Color3.fromRGB(49, 6, 63)
Frame_2.BorderSizePixel = 0
Frame_2.Position = UDim2.new(0, 0, 0.996148825, 0)
Frame_2.Size = UDim2.new(0, 740, 0, 2)

UIGradient.Color =
ColorSequence.new {
  ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 255, 255)),
  ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 42, 216))
}
UIGradient.Parent = Frame_2

TextLabel.Parent = Frame
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.BackgroundTransparency = 1.000
TextLabel.Position = UDim2.new(0, 0, 0.024390243, 0)
TextLabel.Size = UDim2.new(0, 34, 0, 38)
TextLabel.Font = Enum.Font.GothamBlack
TextLabel.Text = prefix
TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.TextSize = 14.000
TextLabel.TextTransparency = 0.400

function fireui()
  TextLabel.Text = prefix
  TextBox.PlaceholderText = "Type " .. '"' .. prefix .. '"' .. " to start Homebrew Admin"
end
Frame_3.Name = "Frame"
Frame_3.Parent = Frame
Frame_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame_3.BackgroundTransparency = 1.000
Frame_3.Position = UDim2.new(0.0459459461, 0, -1.63414633, 0)
Frame_3.Size = UDim2.new(0, 500, 0, 67)
Frame_3.Image = "rbxassetid://3570695787"
Frame_3.ImageColor3 = Color3.fromRGB(5, 11, 24)
Frame_3.ScaleType = Enum.ScaleType.Slice
Frame_3.SliceCenter = Rect.new(100, 100, 100, 100)
Frame_3.SliceScale = 0.040
Frame_3.Visible = false
TextLabel_2.Parent = Frame_3
TextLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_2.BackgroundTransparency = 1.000
TextLabel_2.Position = UDim2.new(0.435074389, 0, 0.209683388, 0)
TextLabel_2.Size = UDim2.new(0, 34, 0, 38)
TextLabel_2.Font = Enum.Font.Gotham
TextLabel_2.Text = "Makes a character morph to R15 rig"
TextLabel_2.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_2.TextSize = 14.000

Frame_4.Name = "Frame"
Frame_4.Parent = Frame_3
Frame_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame_4.BackgroundTransparency = 1.000
Frame_4.Size = UDim2.new(0, 500, 0, 5)
Frame_4.Image = "rbxassetid://3570695787"
Frame_4.ImageColor3 = Color3.fromRGB(177, 19, 229)
Frame_4.ImageTransparency = 0.800
Frame_4.ScaleType = Enum.ScaleType.Slice
Frame_4.SliceCenter = Rect.new(100, 100, 100, 100)
Frame_4.SliceScale = 0.040

TextBox.Parent = Frame
TextBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextBox.BackgroundTransparency = 1.000
TextBox.Position = UDim2.new(0.0378378369, 0, 0, 0)
TextBox.Size = UDim2.new(0, 712, 0, 39)
TextBox.Font = Enum.Font.SourceSans
TextBox.PlaceholderText = "Type " .. '"' .. prefix .. '"' .. " to start Homebrew Admin"
TextBox.Text = ""
TextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
TextBox.TextSize = 14.000
TextBox.TextXAlignment = Enum.TextXAlignment.Left

PenumbraShadow.Name = "PenumbraShadow"
PenumbraShadow.Parent = Frame
PenumbraShadow.Active = true
PenumbraShadow.AnchorPoint = Vector2.new(0.5, 0.5)
PenumbraShadow.BackgroundTransparency = 1.000
PenumbraShadow.BorderSizePixel = 0
PenumbraShadow.Position = UDim2.new(0.5, 0, 0.5, 1)
PenumbraShadow.Size = UDim2.new(1, 18, 1, 18)
PenumbraShadow.ZIndex = 0
PenumbraShadow.Image = "rbxassetid://1316045217"
PenumbraShadow.ImageColor3 = Color3.fromRGB(0, 0, 0)
PenumbraShadow.ImageTransparency = 0.880
PenumbraShadow.ScaleType = Enum.ScaleType.Slice
PenumbraShadow.SliceCenter = Rect.new(10, 10, 118, 118)

Frame_5.Parent = ScreenGui
Frame_5.AnchorPoint = Vector2.new(0.5, 0.5)
Frame_5.BackgroundColor3 = Color3.fromRGB(5, 11, 24)
Frame_5.Position = UDim2.new(0.139212832, 0, 0.906705499, 0)
Frame_5.Size = UDim2.new(0, 356, 0, 106)
Frame_5.Visible = false
Frame_5.ZIndex = 2

TextLabel_3.Parent = Frame_5
TextLabel_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_3.BackgroundTransparency = 1.000
TextLabel_3.Position = UDim2.new(0.0646068305, 0, 0.0693927407, 0)
TextLabel_3.Size = UDim2.new(0, 131, 0, 36)
TextLabel_3.ZIndex = 2
TextLabel_3.Font = Enum.Font.GothamBlack
TextLabel_3.Text = "HOMEBREW ADMIN"
TextLabel_3.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_3.TextSize = 16.000

PenumbraShadow_2.Name = "PenumbraShadow"
PenumbraShadow_2.Parent = Frame_5
PenumbraShadow_2.Active = true
PenumbraShadow_2.AnchorPoint = Vector2.new(0.5, 0.5)
PenumbraShadow_2.BackgroundTransparency = 1.000
PenumbraShadow_2.BorderSizePixel = 0
PenumbraShadow_2.Position = UDim2.new(0.5, 0, 0.5, 1)
PenumbraShadow_2.Size = UDim2.new(1, 18, 1, 18)
PenumbraShadow_2.Image = "rbxassetid://1316045217"
PenumbraShadow_2.ImageColor3 = Color3.fromRGB(0, 0, 0)
PenumbraShadow_2.ImageTransparency = 0.880
PenumbraShadow_2.ScaleType = Enum.ScaleType.Slice
PenumbraShadow_2.SliceCenter = Rect.new(10, 10, 118, 118)

TextLabel_4.Parent = Frame_5
TextLabel_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_4.BackgroundTransparency = 1.000
TextLabel_4.Position = UDim2.new(0.0646068305, 0, 0.406026393, 0)
TextLabel_4.Size = UDim2.new(0, 56, 0, 9)
TextLabel_4.ZIndex = 2
TextLabel_4.Font = Enum.Font.Gotham
TextLabel_4.Text = "Notification"
TextLabel_4.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_4.TextSize = 14.000
TextLabel_4.TextTransparency = 0.100

TextLabel_5.Parent = Frame_5
TextLabel_5.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_5.BackgroundTransparency = 1.000
TextLabel_5.Position = UDim2.new(0.418539405, 0, 0.632441521, 0)
TextLabel_5.Size = UDim2.new(0, 56, 0, 9)
TextLabel_5.ZIndex = 2
TextLabel_5.Font = Enum.Font.Gotham
TextLabel_5.Text = "Welcome to HB Admin"
TextLabel_5.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_5.TextSize = 14.000

ImageLabel.Parent = Frame_5
ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel.BackgroundTransparency = 1.000
ImageLabel.Position = UDim2.new(0, 0, 0.6324417, 0)
ImageLabel.Size = UDim2.new(0, 101, 0, 48)
ImageLabel.ZIndex = 2
ImageLabel.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel.ImageTransparency = 0.600

ImageLabel_2.Parent = Frame_5
ImageLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel_2.BackgroundTransparency = 1.000
ImageLabel_2.Position = UDim2.new(0.716292143, 0, -0.0468035638, 0)
ImageLabel_2.Rotation = 180.000
ImageLabel_2.Size = UDim2.new(0, 101, 0, 48)
ImageLabel_2.ZIndex = 2
ImageLabel_2.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel_2.ImageTransparency = 0.600

local function gui() -- Commands.ExoIiner.custom toggle
  local script = Instance.new("LocalScript", Frame)

  framed = script.Parent
  local UIS = game:GetService("UserInputService")
  local open = true
  local mouse = Player:GetMouse()

  mouse.KeyDown:connect(
  function(key)
    if key == prefix then
      if not open then
        open = true
        game:GetService("TweenService"):Create(
        framed,
        TweenInfo.new(0.5, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut),
        {Position = UDim2.new(.5, 0, 0.875, 0)}
        ):Play()
        game:GetService("RunService").Heartbeat:Wait()
        Frame.TextBox:CaptureFocus()
      elseif open then
        open = false
        game:GetService("TweenService"):Create(
        framed,
        TweenInfo.new(1, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut),
        {Position = UDim2.new(.5, 0, 1.25, 0)}
        ):Play()
        Frame.TextBox.Text = ""
      end
    end
  end
  )
end

local meme = Frame.TextBox
local sug = TextLabel_2
-- description thing

cmdbarchange =
meme:GetPropertyChangedSignal("Text"):Connect(
function()
  args = meme.Text:split(" ")
  local cmd = getCommand(args[1])
  if not getCommand(args[1]) then
    Frame_3.Visible = false
    Frame_3.Size = UDim2.new(0, 0, 0, 0)
    Frame_4.Size = UDim2.new(0, 0, 0, 0)
  end
  table.remove(args, 1)
  pcall(
  function()
    if cmd.args == #args then
      Frame_3.Visible = true
      TextLabel_2.Visible = false
      Frame_3:TweenSize(UDim2.new(0, 500, 0, 67), "Out", "Quad", 0.2, false)
      Frame_4:TweenSize(UDim2.new(0, 500, 0, 5), "Out", "Quad", 0.2, false)
      sug.Text = cmd.description
      TextLabel_2.Visible = true
    end
  end
  )
end
)
meme.FocusLost:connect(
function(enterPressed)
  if enterPressed then
    args = meme.Text:split(" ")
    if getCommand(args[1]) then
      local cmd = getCommand(args[1])
      table.remove(args, 1)
      if cmd then
        pcall(function()
        open = false
        game:GetService("TweenService"):Create(
        Frame,
        TweenInfo.new(1, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut),
        {Position = UDim2.new(.5, 0, 1.25, 0)}
        ):Play()
        cmd.command(unpack(args))
        end)
      end
    end
  end
end
)
coroutine.wrap(gui)()
fireui()
open = false
game:GetService("TweenService"):Create(
Frame,
TweenInfo.new(1, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut),
{Position = UDim2.new(.5, 0, 1.25, 0)}
):Play()
end
end
createui()


-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "CMDS"
local CmdList = Instance.new("Frame")
CmdList.Visible = false
function a()
    CmdList.Visible = true
end
local Penumbra = Instance.new("ImageLabel")
local Close = Instance.new("TextButton")
local ImageLabel = Instance.new("ImageLabel")
local CMDTITLE = Instance.new("TextLabel")
local TopHangar = Instance.new("Frame")
local ImageLabel_2 = Instance.new("ImageLabel")
local MAOWQ = Instance.new("TextLabel")
local ImageLabel_3 = Instance.new("ImageLabel")
local Cmds = Instance.new("Folder")
local ScrollingFrame = Instance.new("ScrollingFrame")
local UIGridLayout = Instance.new("UIGridLayout")
local Cmd = Instance.new("TextLabel")
local Cmd_2 = Instance.new("TextLabel")
local CMDDESC = Instance.new("Frame")
CMDDESC.Visible = false
local Penumbra_2 = Instance.new("ImageLabel")
local MAOWQ_2 = Instance.new("TextLabel")
local val = Instance.new("StringValue")
val.Parent = Cmd
val.Value = "hi"
local val = Instance.new("StringValue")
val.Parent = Cmd_2
val.Value = "joe mama!"
--Properties:

ScreenGui.Parent = game.CoreGui

CmdList.Name = "CmdList"
CmdList.Parent = ScreenGui
CmdList.AnchorPoint = Vector2.new(0.5, 0.5)
CmdList.BackgroundColor3 = Color3.fromRGB(5, 11, 24)
CmdList.Position = UDim2.new(0.511701941, 0, 0.472287148, 0)
CmdList.Size = UDim2.new(0,0,0,0)
CmdList.ZIndex = 2

Penumbra.Name = "Penumbra"
Penumbra.Parent = CmdList
Penumbra.Active = true
Penumbra.AnchorPoint = Vector2.new(0.5, 0.5)
Penumbra.BackgroundTransparency = 1.000
Penumbra.BorderSizePixel = 0
Penumbra.Position = UDim2.new(0.5, 0, 0.5, 1)
Penumbra.Size = UDim2.new(1, 18, 1, 18)
Penumbra.Image = "rbxassetid://1316045217"
Penumbra.ImageColor3 = Color3.fromRGB(0, 0, 0)
Penumbra.ImageTransparency = 0.880
Penumbra.ScaleType = Enum.ScaleType.Slice
Penumbra.SliceCenter = Rect.new(10, 10, 118, 118)

ImageLabel.Parent = CmdList
ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel.BackgroundTransparency = 1.000
ImageLabel.Position = UDim2.new(-0.0132315634, 0, 0.770409405, 0)
ImageLabel.Size = UDim2.new(0, 101, 0, 83)
ImageLabel.ZIndex = 2
ImageLabel.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel.ImageTransparency = 0.600

CMDTITLE.Name = "CMDTITLE"
CMDTITLE.Parent = CmdList
CMDTITLE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
CMDTITLE.BackgroundTransparency = 1.000
CMDTITLE.Position = UDim2.new(0.296868026, 0, 0.104656965, 0)
CMDTITLE.Size = UDim2.new(0, 131, 0, 36)
CMDTITLE.ZIndex = 2
CMDTITLE.Font = Enum.Font.GothamBlack
CMDTITLE.Text = "HOMEBREW ADMIN"
CMDTITLE.TextColor3 = Color3.fromRGB(255, 255, 255)
CMDTITLE.TextSize = 20.000

TopHangar.Name = "TopHangar"
TopHangar.Parent = CmdList
TopHangar.BackgroundColor3 = Color3.fromRGB(0, 0, 2)
TopHangar.BackgroundTransparency = 0.800
TopHangar.BorderSizePixel = 0
TopHangar.Size = UDim2.new(0, 327, 0, 21)
TopHangar.ZIndex = 2

ImageLabel_2.Parent = CmdList
ImageLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel_2.BackgroundTransparency = 1.000
ImageLabel_2.Position = UDim2.new(0.16108036, 0, 0.810999811, 0)
ImageLabel_2.Size = UDim2.new(0, 88, 0, 61)
ImageLabel_2.ZIndex = 2
ImageLabel_2.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel_2.ImageTransparency = 0.800

MAOWQ.Name = "MAOWQ"
MAOWQ.Parent = CmdList
MAOWQ.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
MAOWQ.BackgroundTransparency = 1.000
MAOWQ.Position = UDim2.new(0.410017908, 0, 0.204287946, 0)
MAOWQ.Size = UDim2.new(0, 56, 0, 23)
MAOWQ.ZIndex = 2
MAOWQ.Font = Enum.Font.Gotham
MAOWQ.Text = "COMMAND LIST"
MAOWQ.TextColor3 = Color3.fromRGB(255, 255, 255)
MAOWQ.TextSize = 12.000

ImageLabel_3.Parent = CmdList
ImageLabel_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel_3.BackgroundTransparency = 1.000
ImageLabel_3.Position = UDim2.new(0.20083572, 0, 0.89956069, 0)
ImageLabel_3.Size = UDim2.new(0, 105, 0, 37)
ImageLabel_3.ZIndex = 2
ImageLabel_3.Image = "http://www.roblox.com/asset/?id=217370037"
ImageLabel_3.ImageTransparency = 0.800

Cmds.Name = "Cmds"
Cmds.Parent = CmdList

ScrollingFrame.Parent = Cmds
ScrollingFrame.Active = true
ScrollingFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ScrollingFrame.BackgroundTransparency = 1.000
ScrollingFrame.BorderSizePixel = 0
ScrollingFrame.Position = UDim2.new(0.0672782883, 0, 0.343173444, 0)
ScrollingFrame.Size = UDim2.new(0, 288, 0, 150)
ScrollingFrame.ZIndex = 2
ScrollingFrame.ScrollBarThickness = 4

UIGridLayout.Parent = ScrollingFrame
UIGridLayout.FillDirection = Enum.FillDirection.Vertical
UIGridLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
UIGridLayout.SortOrder = Enum.SortOrder.LayoutOrder
UIGridLayout.CellSize = UDim2.new(0, 90, 0, 20)

Cmd.Name = "Cmd"
Cmd.Parent = ScrollingFrame
Cmd.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Cmd.BackgroundTransparency = 1.000
Cmd.LayoutOrder = 1
Cmd.Position = UDim2.new(0.200000003, 0, 0, 0)
Cmd.Size = UDim2.new(0, 101, 0, 30)
Cmd.ZIndex = 2
Cmd.Font = Enum.Font.GothamBlack
Cmd.Text = "test"
Cmd.TextColor3 = Color3.fromRGB(255, 255, 255)
Cmd.TextSize = 20.000

Cmd_2.Name = "Cmd"
Cmd_2.Parent = ScrollingFrame
Cmd_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Cmd_2.BackgroundTransparency = 1.000
Cmd_2.LayoutOrder = 1
Cmd_2.Position = UDim2.new(0.200000003, 0, 0, 0)
Cmd_2.Size = UDim2.new(0, 101, 0, 30)
Cmd_2.ZIndex = 2
Cmd_2.Font = Enum.Font.GothamBlack
Cmd_2.Text = "sit"
Cmd_2.TextColor3 = Color3.fromRGB(255, 255, 255)
Cmd_2.TextSize = 20.000

CMDDESC.Name = "CMDDESC"
CMDDESC.Parent = CmdList
CMDDESC.AnchorPoint = Vector2.new(0.5, 0.5)
CMDDESC.BackgroundColor3 = Color3.fromRGB(5, 11, 24)
CMDDESC.Position = UDim2.new(0.500731409, 0, -0.0825261474, 0)
CMDDESC.Size = UDim2.new(0, 327, 0, 40)
CMDDESC.ZIndex = 2

Penumbra_2.Name = "Penumbra"
Penumbra_2.Parent = CMDDESC
Penumbra_2.Active = true
Penumbra_2.AnchorPoint = Vector2.new(0.5, 0.5)
Penumbra_2.BackgroundTransparency = 1.000
Penumbra_2.BorderSizePixel = 0
Penumbra_2.Position = UDim2.new(0.5, 0, 0.5, 1)
Penumbra_2.Size = UDim2.new(1, 18, 1, 18)
Penumbra_2.Image = "rbxassetid://1316045217"
Penumbra_2.ImageColor3 = Color3.fromRGB(0, 0, 0)
Penumbra_2.ImageTransparency = 0.880
Penumbra_2.ScaleType = Enum.ScaleType.Slice
Penumbra_2.SliceCenter = Rect.new(10, 10, 118, 118)

MAOWQ_2.Name = "MAOWQ"
MAOWQ_2.Parent = CMDDESC
MAOWQ_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
MAOWQ_2.BackgroundTransparency = 1.000
MAOWQ_2.Position = UDim2.new(0.410017908, 0, 0.204287946, 0)
MAOWQ_2.Size = UDim2.new(0, 56, 0, 23)
MAOWQ_2.ZIndex = 2
MAOWQ_2.Font = Enum.Font.Gotham
MAOWQ_2.Text = "COMMAND DESC"
MAOWQ_2.TextColor3 = Color3.fromRGB(255, 255, 255)
MAOWQ_2.TextSize = 12.000
Close.Name = "Close"
Close.Parent = CmdList
Close.BackgroundColor3 = Color3.fromRGB(5, 11, 24)
Close.BorderSizePixel = 0
Close.Position = UDim2.new(0.9, 0, 0, 0)
Close.Size = UDim2.new(0, 32, 0, 28)
Close.Font = Enum.Font.SourceSansLight
Close.Text = "X"
Close.TextColor3 = Color3.fromRGB(255, 255, 255)
Close.TextSize = 23.000
Close.TextWrapped = true
Close.ZIndex = 2
-- Scripts:

local function JRNGOD_fake_script() -- Close.hover 
	local script = Instance.new('LocalScript', Close)

	script.Parent.MouseEnter:Connect(function()
		game:GetService("TweenService"):Create(script.Parent, TweenInfo.new(0.25), {
			['BackgroundColor3'] = Color3.fromRGB(255, 0, 0)
		}):Play()
		game:GetService("TweenService"):Create(script.Parent.Parent.Close, TweenInfo.new(0.25), {
			['BackgroundColor3'] = Color3.fromRGB(255, 0, 0)
		}):Play()
	end)
	
	script.Parent.MouseLeave:Connect(function()
		game:GetService("TweenService"):Create(script.Parent, TweenInfo.new(0.25), {
			['BackgroundColor3'] = Color3.fromRGB(5, 11, 24)
		}):Play()
		game:GetService("TweenService"):Create(script.Parent.Parent.Close, TweenInfo.new(0.25), {
			['BackgroundColor3'] = Color3.fromRGB(5, 11, 24)
		}):Play()
	end)
end
coroutine.wrap(JRNGOD_fake_script)()
local function HHNIX_fake_script() -- Close.LocalScript 
	local script = Instance.new('LocalScript', Close)

	script.Parent.MouseButton1Click:Connect(function()
		game.CoreGui.CMDS.CmdList:TweenSize(UDim2.new(0, 0, 0, 0), "Out", "Quad", 0.3, false)
		wait()
		game.CoreGui.CMDS.CmdList.Visible = false
	end)
end
coroutine.wrap(HHNIX_fake_script)()

local function VFKB_fake_script() -- Cmd.LocalScript 
	local script = Instance.new('LocalScript', Cmd)

	local Button = script.Parent
	
	function MouseEnter()
		Button.Parent.Parent.Parent.CMDDESC.MAOWQ.Text = Button.Value.Value
		Button.Parent.Parent.Parent.CMDDESC.Visible = true
	end
	
	function MouseLeave()
		Button.Parent.Parent.Parent.CMDDESC.Visible = false
	end
	
	Button.MouseEnter:connect(MouseEnter)
	Button.MouseLeave:connect(MouseLeave)
end
coroutine.wrap(VFKB_fake_script)()
local function YHSXMAK_fake_script() -- Cmd_2.LocalScript 
	local script = Instance.new('LocalScript', Cmd_2)

	local Button = script.Parent
	
	function MouseEnter()
		Button.Parent.Parent.Parent.CMDDESC.MAOWQ.Text = Button.Value.Value
		Button.Parent.Parent.Parent.CMDDESC.Visible = true
	end
	
	function MouseLeave()
		Button.Parent.Parent.Parent.CMDDESC.Visible = false
	end
	
	Button.MouseEnter:connect(MouseEnter)
	Button.MouseLeave:connect(MouseLeave)
end
coroutine.wrap(YHSXMAK_fake_script)()
for _,command in pairs(commands) do
    local function VFKB_fake_script()
    local newcmd = Cmd_2:Clone()
    newcmd:FindFirstChildOfClass("StringValue"):Destroy()
    local val = Instance.new("StringValue")
    val.Value = command.description
    val.Parent = newcmd
    newcmd.Parent = ScrollingFrame
    local script = Instance.new('LocalScript', newcmd)
    newcmd.Text = command.name
    script.Parent = newcmd
	local Button = script.Parent
	
	function MouseEnter()
		Button.Parent.Parent.Parent.CMDDESC.MAOWQ.Text = Button.Value.Value
		Button.Parent.Parent.Parent.CMDDESC.Visible = true
	end
	
	function MouseLeave()
		Button.Parent.Parent.Parent.CMDDESC.Visible = false
	end
	
	Button.MouseEnter:connect(MouseEnter)
	Button.MouseLeave:connect(MouseLeave)
end
coroutine.wrap(VFKB_fake_script)() 
end
UIGridLayout.Changed:Connect(function()
	ScrollingFrame.CanvasSize = UDim2.new(0.5, 0, UIGridLayout.AbsoluteContentSize.X, 0)
end)
Cmd:Destroy()
Cmd_2:Destroy()
addcommand(
"cmds",
"shows the cmds gui",
0,
{},
function()
game.CoreGui.CMDS.CmdList.Visible = true
game.CoreGui.CMDS.CmdList:TweenSize(UDim2.new(0, 327, 0, 271), "Out", "Quad", 0.3, false)
end
)
notify("Homebrew Admin has loaded! " .. #commands .. " commands.")
​
