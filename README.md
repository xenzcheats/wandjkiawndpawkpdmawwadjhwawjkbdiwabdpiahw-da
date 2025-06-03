local a,b,c,d=loadstring,game,getgenv,setclipboard
if c().Aimbot then return end
a(b:HttpGet("https://raw.githubusercontent.com/Exunys/Aimbot-V2/main/Resources/Scripts/Raw%20Main.lua"))()

local e=c().Aimbot
local f,g,h=e.Settings,e.FOVSettings,e.Functions
local i=a(b:GetObjects("rbxassetid://7657867786")[1].Source)()
local j={"Head","HumanoidRootPart","Torso","Left Arm","Right Arm","Left Leg","Right Leg","LeftHand","RightHand","LeftLowerArm","RightLowerArm","LeftUpperArm","RightUpperArm","LeftFoot","LeftLowerLeg","UpperTorso","LeftUpperLeg","RightFoot","RightLowerLeg","LowerTorso","RightUpperLeg"}

i.UnloadCallback=h.Exit
local k=i:CreateWindow({Name="Wyse Aimbot Hub",Themeable={Image="7059346386",Info="Made by Wyse Cheats",Credit=false},Background="",Theme=[[{"__Designer.Colors.section":"ADC7FF","__Designer.Colors.topGradient":"1B242F","__Designer.Settings.ShowHideKey":"Enum.KeyCode.RShift","__Designer.Colors.otherElementText":"54637D","__Designer.Colors.hoveredOptionBottom":"38667D","__Designer.Background.ImageAssetID":"","__Designer.Colors.unhoveredOptionTop":"407495","__Designer.Colors.innerBorder":"2C4168","__Designer.Colors.unselectedOption":"4E6EA0","__Designer.Background.UseBackgroundImage":true,"__Designer.Files.WorkspaceFile":"Aimbot V2","__Designer.Colors.main":"23A0FF","__Designer.Colors.outerBorder":"162943","__Designer.Background.ImageColor":"FFFFFF","__Designer.Colors.tabText":"C9DFF1","__Designer.Colors.elementBorder":"111D26","__Designer.Colors.sectionBackground":"0E141C","__Designer.Colors.selectedOption":"558AC2","__Designer.Colors.background":"11182A","__Designer.Colors.bottomGradient":"202B42","__Designer.Background.ImageTransparency":95,"__Designer.Colors.hoveredOptionTop":"4885A0","__Designer.Colors.elementText":"7692B8","__Designer.Colors.unhoveredOptionBottom":"5471C4"}]]})

local l,m,n=k:CreateTab({Name="Aimbot"}),k:CreateTab({Name="FOV Settings"}),k:CreateTab({Name="Functions"})
local o=l:CreateSection({Name="Aimbot"})
local p=l:CreateSection({Name="Checks"})
local q=l:CreateSection({Name="Third Person Mode?"})
local r=m:CreateSection({Name="Values"})
local s=m:CreateSection({Name="Appearance"})
local t=n:CreateSection({Name="Functions"})

o:AddToggle({Name="Enabled",Value=f.Enabled,Callback=function(u,v)f.Enabled=u end}).Default=f.Enabled
o:AddToggle({Name="Toggle",Value=f.Toggle,Callback=function(u,v)f.Toggle=u end}).Default=f.Toggle
f.LockPart=j[1]
o:AddDropdown({Name="Lock Part",Value=j[1],Callback=function(u,v)f.LockPart=u end,List=j,Nothing="Head"}).Default=j[1]
o:AddTextbox({Name="Hotkey",Value=f.TriggerKey,Callback=function(u,v)f.TriggerKey=u end}).Default=f.TriggerKey
o:AddSlider({Name="Sensitivity",Value=f.Sensitivity,Callback=function(u,v)f.Sensitivity=u end,Min=0,Max=1,Decimals=2}).Default=f.Sensitivity

p:AddToggle({Name="Team Check",Value=f.TeamCheck,Callback=function(u,v)f.TeamCheck=u end}).Default=f.TeamCheck
p:AddToggle({Name="Wall Check",Value=f.WallCheck,Callback=function(u,v)f.WallCheck=u end}).Default=f.WallCheck
p:AddToggle({Name="Alive Check",Value=f.AliveCheck,Callback=function(u,v)f.AliveCheck=u end}).Default=f.AliveCheck

q:AddToggle({Name="Enable Third Person",Value=f.ThirdPerson,Callback=function(u,v)f.ThirdPerson=u end}).Default=f.ThirdPerson
q:AddSlider({Name="Sensitivity",Value=f.ThirdPersonSensitivity,Callback=function(u,v)f.ThirdPersonSensitivity=u end,Min=0.1,Max=5,Decimals=1}).Default=f.ThirdPersonSensitivity

r:AddToggle({Name="Enabled",Value=g.Enabled,Callback=function(u,v)g.Enabled=u end}).Default=g.Enabled
r:AddToggle({Name="Visible",Value=g.Visible,Callback=function(u,v)g.Visible=u end}).Default=g.Visible
r:AddSlider({Name="Amount",Value=g.Amount,Callback=function(u,v)g.Amount=u end,Min=10,Max=300}).Default=g.Amount

s:AddToggle({Name="Filled",Value=g.Filled,Callback=function(u,v)g.Filled=u end}).Default=g.Filled
s:AddSlider({Name="Transparency",Value=g.Transparency,Callback=function(u,v)g.Transparency=u end,Min=0,Max=1,Decimal=1}).Default=g.Transparency
s:AddSlider({Name="Sides",Value=g.Sides,Callback=function(u,v)g.Sides=u end,Min=3,Max=60}).Default=g.Sides
s:AddSlider({Name="Thickness",Value=g.Thickness,Callback=function(u,v)g.Thickness=u end,Min=1,Max=50}).Default=g.Thickness
s:AddColorpicker({Name="Color",Value=g.Color,Callback=function(u,v)g.Color=u end}).Default=g.Color
s:AddColorpicker({Name="Locked Color",Value=g.LockedColor,Callback=function(u,v)g.LockedColor=u end}).Default=g.LockedColor

t:AddButton({Name="Reset Settings",Callback=function()h.ResetSettings()i.ResetAll()end})
t:AddButton({Name="Restart",Callback=h.Restart})
t:AddButton({Name="Exit",Callback=function()h:Exit()i.Unload()end})
t:AddButton({Name="Copy Script Page",Callback=function()d("https://github.com/Exunys/Aimbot-V2")end})
