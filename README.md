repeat wait() until game:IsLoaded()
repeat wait() until game:GetService("Players")

----------------------------------- save
function loadcheck()
    if isfile("RebornXer Hub king Lagacy"..game.Players.LocalPlayer.Name..".json") then
    else
    writefile("RebornXer Hub king Lagacy"..game.Players.LocalPlayer.Name..".json",game:GetService("HttpService"):JSONEncode(_G.SaveSettings))
    return
    end
    end
    pcall(function()
        _G.SaveSettings = {
            Select_Weapon = "",
			Select_Method = "",
			DistanceMob = "10",
			Auto_Sea_King = false,
			Auto_Ghost_Ship = false,
			Auto_Hydra = false,
			Hop_Mix = false,
			Auto_Hydra_Hop = false,
			Auto_Sea_King_Hop = false,
			Auto_Ghost_Ship_Hop = false,
			Auto_Skill = false,
			Black_Screen = false
        }
    end)
    function LoadSetting()
        if isfile("RebornXer Hub king Lagacy"..game.Players.LocalPlayer.Name..".json") then
            -- โหลดไฟล์
            local fileContent = readfile("RebornXer Hub king Lagacy"..game.Players.LocalPlayer.Name..".json")
            print("Loaded file content: ", fileContent) -- ตรวจสอบเนื้อหาของไฟล์
            
            -- แปลงไฟล์จาก JSON
            local success, decoded = pcall(function()
                return game:GetService("HttpService"):JSONDecode(fileContent)
            end)
            
            if success then
                _G.SaveSettings = decoded
            else
            end
        else
            SaveSetting()
        end
    end
    function SaveSetting()

    if isfile("RebornXer Hub king Lagacy"..game.Players.LocalPlayer.Name..".json") then
    writefile("RebornXer Hub king Lagacy"..game.Players.LocalPlayer.Name..".json",game:GetService("HttpService"):JSONEncode(_G.SaveSettings))
    else
    loadcheck()
    end
    end
    
    loadcheck()
    LoadSetting()


	local ZenHub = Instance.new("ScreenGui")
	local Open = Instance.new("TextButton")
	local fuckshit = Instance.new("UICorner")
	local MODILEMAGE = Instance.new("ImageLabel")
	local posto = Instance.new("UIStroke")
	
	local ScreenGui = Instance.new("ScreenGui")
	local ImageButton = Instance.new("ImageButton")
	
	
	ScreenGui.Parent = game.CoreGui
	ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
	
	ImageButton.Parent = ScreenGui
	ImageButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	ImageButton.BorderSizePixel = 0
	ImageButton.Position = UDim2.new(0.120833337, 0, 0.0952890813, 0)
	ImageButton.Size = UDim2.new(0, 45, 0, 45)
	ImageButton.Draggable = true
	ImageButton.Image = ""
	ImageButton.MouseButton1Down:connect(function()
	game:GetService("VirtualInputManager"):SendKeyEvent(true,305,false,game)
	 game:GetService("VirtualInputManager"):SendKeyEvent(false,305,false,game)
	end)
	
	
	fuckshit.Parent = Open
	
	 MODILEMAGE.Name = "MODILEMAGE"
	 MODILEMAGE.Parent = Open
	 MODILEMAGE.BackgroundColor3 = Color3.fromRGB(51,255,255)
	 MODILEMAGE.BackgroundTransparency = 1.000
	 MODILEMAGE.BorderSizePixel = 0
	 MODILEMAGE.Position = UDim2.new(0, 0.5, 0, 0)
	 MODILEMAGE.Size = UDim2.new(0, 38, 0, 31)
	 MODILEMAGE.Image = "rbxassetid://"
	 
	posto.Name = "posto"
	 posto.Parent = Open
	 posto.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	 posto.Color = Color3.fromRGB(51,255,255)
	 posto.LineJoinMode = Enum.LineJoinMode.Round
	 posto.Thickness = 1
	 posto.Transparency = 0
	 posto.Enabled = true
	 posto.Archivable = true
	
	
	
	_G.WindowBackgroundColor = Color3.fromRGB(12,12,12)
	_G.BackgroundItemColor = Color3.fromRGB(20, 20, 20)
	_G.TabWindowColor = Color3.fromRGB(30, 30, 30)
	_G.ContainerColor = Color3.fromRGB(30, 30, 30)
	_G.TitleTextColor = Color3.fromRGB(150, 150, 150)
	_G.ImageColor = Color3.fromRGB(0, 0, 255)
	_G.LineThemeColor = Color3.fromRGB(150, 150, 150)
	_G.TabTextColor = Color3.fromRGB(150, 150, 150)
	_G.TabImageColor = Color3.fromRGB(150, 150, 150)
	_G.TabThemeColor = Color3.fromRGB(250, 0, 0)
	_G.SectionColor = Color3.fromRGB(0, 0, 255)
	_G.SectionImageColor = Color3.fromRGB(150, 150, 150)
	_G.SectionTextColor = Color3.fromRGB(0, 0, 255)
	_G.SectionOn = Color3.fromRGB(0, 250, 0)
	
	_G.Color1 = Color3.fromRGB(255,255,255)
	do local GUI = game.CoreGui:FindFirstChild("1xliiUI");if GUI then GUI:Destroy();end;if _G.Color == nil then
	_G.Color = Color3.fromRGB(255,255,255)
	end 
	end
	
	local tween = game:GetService("TweenService")
	local tweeninfo = TweenInfo.new
	local input = game:GetService("UserInputService")
	local run = game:GetService("RunService")
	local plr = game.Players.LocalPlayer
	local mouse = plr:GetMouse()
	
	local UserInputService = game:GetService("UserInputService")
	local TweenService = game:GetService("TweenService")
	
	local function MakeDraggable(topbarobject, object)
		local Dragging = nil
		local DragInput = nil
		local DragStart = nil
		local StartPosition = nil
	
		local function Update(input)
			local Delta = input.Position - DragStart
			local pos = UDim2.new(StartPosition.X.Scale, StartPosition.X.Offset + Delta.X, StartPosition.Y.Scale, StartPosition.Y.Offset + Delta.Y)
			local Tween = TweenService:Create(object, TweenInfo.new(0.15), {Position = pos})
			Tween:Play()
		end
	
		topbarobject.InputBegan:Connect(
			function(input)
				if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
					Dragging = true
					DragStart = input.Position
					StartPosition = object.Position
	
					input.Changed:Connect(
						function()
							if input.UserInputState == Enum.UserInputState.End then
								Dragging = false
							end
						end
					)
				end
			end
		)
	
		topbarobject.InputChanged:Connect(
			function(input)
				if
					input.UserInputType == Enum.UserInputType.MouseMovement or
					input.UserInputType == Enum.UserInputType.Touch
				then
					DragInput = input
				end
			end
		)
	
		UserInputService.InputChanged:Connect(
			function(input)
				if input == DragInput and Dragging then
					Update(input)
				end
			end
		)
	end
	
	local Update = {}
	
	function Update:AddWindow(name,logo,keybind)
		local uihide = false
		local abc = false
		local logo = logo or 0
		local currentpage = ""
		local keybind = keybind or Enum.KeyCode.RightControl
		local yoo = string.gsub(tostring(keybind),"Enum.KeyCode.","")
		
		local SOMEXHUB = Instance.new("ScreenGui")
		SOMEXHUB.Name = "1xliiUI"
		SOMEXHUB.Parent = game.CoreGui
		SOMEXHUB.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
	
	local osfunc = {}
	 local osfunc2 = {}
		local Main = Instance.new("Frame")
		local WindowStrokemain = Instance.new("UIStroke")
		Main.Name = "Main"
		Main.Parent = SOMEXHUB
		Main.ClipsDescendants = true
		Main.AnchorPoint = Vector2.new(0.5,0.5)
		Main.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
		Main.Position = UDim2.new(0.5, 0, 0.5, 0)
		Main.Size = UDim2.new(0, 0, 0, 0)
		
		WindowStrokemain.Name = "WindowStroke"
	 WindowStrokemain.Parent = Main
	 WindowStrokemain.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	 WindowStrokemain.Color = Color3.fromRGB(255,255,255)
	 WindowStrokemain.LineJoinMode = Enum.LineJoinMode.Round
	 WindowStrokemain.Thickness = 1
	 WindowStrokemain.Transparency = 0
	 WindowStrokemain.Enabled = true
	 WindowStrokemain.Archivable = true
		
		Main:TweenSize(UDim2.new(0, 600, 0, 400),"Out","Quad",0,true)
	
		local MCNR = Instance.new("UICorner")
		MCNR.Name = "MCNR"
		MCNR.Parent = Main
	
		local Top = Instance.new("Frame")
		Top.Name = "Top"
		Top.Position = UDim2.new(0,0,0,4)
		Top.Parent = Main
		Top.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
		Top.Size = UDim2.new(0, 560, 0, 28)
	
	
	
		local Logo = Instance.new("ImageLabel")
		Logo.Name = "Logo"
		Logo.Parent = Top
		Logo.BackgroundColor3 = Color3.fromRGB(255,255,255)
		Logo.BackgroundTransparency = 1.000
		Logo.Position = UDim2.new(0, 13, 0, 1)
		Logo.Size = UDim2.new(0, 30, 0, 25)
		Logo.Image = "rbxassetid://"..tostring(logo)
	
		local Name = Instance.new("TextLabel")
		Name.Name = "Name"
		Name.Parent = Top
		Name.BackgroundColor3 = Color3.fromRGB(0,255,255)
		Name.BackgroundTransparency = 1.000
		Name.Position = UDim2.new(0.1, 0, 0, 0)
		Name.Size = UDim2.new(0, 80, 0, 27)
		Name.Font = Enum.Font.Code
		Name.RichText = true;
		Name.Text = name
		Name.TextColor3 = Color3.fromRGB(225, 225, 225)
		Name.TextSize = 15.000
	
	local LocalizationService = game:GetService("LocalizationService")
	 local Players = game:GetService("Players")
	 local player = Players.LocalPlayer
	 local name = player.Name
	 local result, code = pcall(function()
		 return LocalizationService:GetCountryRegionForPlayerAsync(player)
	 end)
	 
	function osfunc:Refresh(textadd)
	 ServerTime.Text = textadd
	 end
	 function osfunc2:Refresh(textadd2)
	 ServerDate.Text = textadd2
	 end
	
	 
	local ListNof = Instance.new("Frame")
		local NofList = Instance.new("UIListLayout")
	
		ListNof.Name = "ListNof"
		ListNof.Parent = SOMEXHUB
		ListNof.BackgroundColor3 = Color3.fromRGB(255,255,255)
		ListNof.BackgroundTransparency = 1.000
		ListNof.Position = UDim2.new(0.778017223, 0, -0.00217864919, 0)
		ListNof.Size = UDim2.new(0, 206, 0, 400)
	
		NofList.Name = "NofList"
		NofList.Parent = ListNof
		NofList.SortOrder = Enum.SortOrder.LayoutOrder
		NofList.VerticalAlignment = Enum.VerticalAlignment.Top
		
		function Update:Nof(txt,tine)
			spawn(function()
				local Nof1 = Instance.new("Frame")
				local Nof2 = Instance.new("Frame")
				local Nof3 = Instance.new("Frame")
				local NofLabel = Instance.new("TextLabel")
				local slidenof = Instance.new("Frame")
				local Slide2 = Instance.new("Frame")
	
				Nof1.Name = "Nof1"
				Nof1.Parent = ListNof
				Nof1.BackgroundColor3 = Color3.fromRGB(51,255,255)
				Nof1.BackgroundTransparency = 1.000
				Nof1.BorderSizePixel = 0
				Nof1.Size = UDim2.new(0, 206, 0, 83)
	
				Nof2.Name = "Nof2"
				Nof2.Parent = Nof1
				Nof2.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				Nof2.BorderColor3 = Color3.fromRGB(0, 0, 0)
				Nof2.Position = UDim2.new(0, 0, 0.0120481923, 0)
				Nof2.Size = UDim2.new(0, 189, 0, 65)
				Instance.new("UICorner",Nof2)
				Instance.new("UICorner",slidenof)
				Instance.new("UICorner",Slide2)
	
	
				Nof3.Name = "Nof3"
				Nof3.Parent = Nof1
				Nof3.BackgroundColor3 = Color3.fromRGB(90, 90, 255)
				Nof3.BackgroundTransparency = 1
				Nof3.BorderSizePixel = 0
				Nof3.Position = UDim2.new(0, 0, 0.638554215, 0)
				Nof3.Size = UDim2.new(0, 189, 0, 7)
	
				NofLabel.Name = "NofLabel"
				NofLabel.Parent = Nof1
				NofLabel.BackgroundColor3 = Color3.fromRGB(51,255,255)
				NofLabel.BackgroundTransparency = 1.000
				NofLabel.BorderSizePixel = 0
				NofLabel.Position = UDim2.new(0, 0, 0.00463949936, 0)
				NofLabel.Size = UDim2.new(0, 188, 0, 52)
				NofLabel.ZIndex = 4
				NofLabel.Font = Enum.Font.Code
				NofLabel.TextColor3 = main_color or Color3.fromRGB(51,255,255)
				NofLabel.TextScaled = false
				NofLabel.TextSize = 18.000
				NofLabel.TextStrokeTransparency = 0.100
				NofLabel.TextTransparency = 0.100
				NofLabel.TextWrapped = true
				NofLabel.Text = txt or ""
	
				slidenof.Name = "slidenof"
				slidenof.Parent = Nof1
				slidenof.BackgroundColor3 = Color3.fromRGB(100, 100, 255)
				slidenof.BorderSizePixel = 0
				slidenof.Position = UDim2.new(0, 0, 0.638554215, 0)
				slidenof.Size = UDim2.new(0, 189, 0, 7)
	
				Slide2.Name = "Slide2"
				Slide2.Parent = Nof1
				Slide2.BorderSizePixel = 0
				Slide2.BackgroundColor3 = main_color or Color3.fromRGB(51,255,255)
				Slide2.BorderColor3 = Color3.fromRGB(0, 0, 0)
				Slide2.Position = UDim2.new(0, 0, 0.0120481923, 0)
				Slide2.Size = UDim2.new(0, 0, 0, 65)
				Slide2.ZIndex = 15
				Slide2.Visible = false
	
				tween:Create(slidenof,tweeninfo(tine or 2),{Size = UDim2.new(0, 0, 0, 7)}):Play()
				wait(tine or 2)
				Slide2.Visible = true
				tween:Create(Slide2,tweeninfo(0.2),{Size = UDim2.new(0, 190, 0, 65)}):Play()
				wait(0.2)
				tween:Create(Slide2,tweeninfo(0.2),{Size = UDim2.new(0, 0, 0, 65)}):Play()
				tween:Create(Nof3,tweeninfo(0.2),{Size = UDim2.new(0, 0, 0, 7)}):Play()
				tween:Create(NofLabel,tweeninfo(0.2),{Size = UDim2.new(0, 0, 0, 52)}):Play()
				tween:Create(Nof2,tweeninfo(0.2),{Size = UDim2.new(0, 0, 0, 65)}):Play()
				wait(0.2)
				Nof2.Visible = false
				game.Debris:AddItem(Nof1,0)
			end)
		end
	
	 
	 function Update:AddNotification(textdesc)
	 local NotificationFrame = Instance.new("Frame")
	 local OkayBtn = Instance.new("TextButton")
	 local OkayBtnCorner = Instance.new("UICorner")
	 local OkayBtnTitle = Instance.new("TextLabel")
	 local NotificationTitle = Instance.new("TextLabel")
	 local NotificationDesc = Instance.new("TextLabel")
	 local NotifCorner = Instance.new("UICorner")
	 local NotifHolderUIStroke = Instance.new("UIStroke")
	 local Line = Instance.new("Frame")
	 
	
	 
	 
	 
	 NotificationFrame.Name = "NotificationFrame"
	 NotificationFrame.Parent = SOMEXHUB
	 NotificationFrame.AnchorPoint = Vector2.new(0.5, 0.5)
	 NotificationFrame.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
	 NotificationFrame.BorderColor3 = _G.SectionColor
	 NotificationFrame.BorderSizePixel = 0
	 NotificationFrame.ClipsDescendants = true
	 NotificationFrame.Position = UDim2.new(0, 1200, 0, 20)
	 NotificationFrame.Size = UDim2.new(0, 0, 0, 0)		
	 
	 NotificationFrame:TweenSize(UDim2.new(0, 200, 0, 100), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
	 
	 NotifCorner.Name = "NotifCorner"
	 NotifCorner.Parent = NotificationFrame
	 NotifCorner.CornerRadius = UDim.new(0, 5)
	 
	 NotifHolderUIStroke.Name = "NotifHolderUIStroke"
	 NotifHolderUIStroke.Parent = NotificationFrame
	 NotifHolderUIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	 NotifHolderUIStroke.Color = _G.SectionColor
	 NotifHolderUIStroke.LineJoinMode = Enum.LineJoinMode.Round
	 NotifHolderUIStroke.Thickness = 1
	 NotifHolderUIStroke.Transparency = 0
	 NotifHolderUIStroke.Enabled = true
	 NotifHolderUIStroke.Archivable = true
	 
	 OkayBtn.Name = "OkayBtn"
	 OkayBtn.Parent = NotificationFrame
	 OkayBtn.BackgroundColor3 = Color3.fromRGB(190, 190, 190)
	 OkayBtn.BorderSizePixel = 1
	 OkayBtn.BorderColor3 = _G.SectionColor
	 OkayBtn.Position = UDim2.new(0, 180, 0, 5)
	 OkayBtn.Size = UDim2.new(0, 20, 0, 20)
	 OkayBtn.AutoButtonColor = true
	 OkayBtn.Font = Enum.Font.SourceSans
	 OkayBtn.Text = "X"
	 OkayBtn.TextColor3 = Color3.fromRGB(255, 0, 0)
	 OkayBtn.TextSize = 22.000
	 
	 OkayBtnCorner.CornerRadius = UDim.new(0, 5)
	 OkayBtnCorner.Name = "OkayBtnCorner"
	 OkayBtnCorner.Parent = OkayBtn
	 
	 OkayBtnTitle.Name = "OkayBtnTitle"
	 OkayBtnTitle.Parent = OkayBtn
	 OkayBtnTitle.BackgroundColor3 = _G.SectionColor
	 OkayBtnTitle.BackgroundTransparency = 1.000
	 OkayBtnTitle.Size = UDim2.new(0, 15, 0, 15)
	 OkayBtnTitle.Text = ""
	 OkayBtnTitle.Font = Enum.Font.Code
	 OkayBtnTitle.TextColor3 = Color3.fromRGB(0, 0, 0)
	 OkayBtnTitle.TextSize = 22.000
	 
	 NotificationTitle.Name = "NotificationTitle"
	 NotificationTitle.Parent = NotificationFrame
	 NotificationTitle.BackgroundColor3 = _G.SectionColor
	 NotificationTitle.BackgroundTransparency = 1.000
	 NotificationTitle.Position = UDim2.new(0, 0, 0, 10)
	 NotificationTitle.Size = UDim2.new(0, 200, 0, 25)
	 NotificationTitle.ZIndex = 3
	 NotificationTitle.Font = Enum.Font.Code
	 NotificationTitle.Text = "Notification"
	 NotificationTitle.TextColor3 = Color3.fromRGB(50, 255, 255)
	 NotificationTitle.TextSize = 22.000
	 
	 Line.Name = "Line"
	 Line.Parent = NotificationFrame
	 Line.BackgroundColor3 = _G.SectionColor
	 Line.BorderSizePixel = 0
	 Line.Position = UDim2.new(0, 0, 0, 40)
	 Line.Size = UDim2.new(0, 200, 0, 1)
	 
	 NotificationDesc.Name = "NotificationDesc"
	 NotificationDesc.Parent = NotificationFrame
	 NotificationDesc.BackgroundColor3 = _G.SectionColor
	 NotificationDesc.BackgroundTransparency = 1.000
	 NotificationDesc.Position = UDim2.new(0, 10, 0, 50)
	 NotificationDesc.Size = UDim2.new(0, 200, 0, 100)
	 NotificationDesc.Font = Enum.Font.Code
	 NotificationDesc.Text = textdesc
	NotificationDesc.TextScaled = false
	 NotificationDesc.TextColor3 = _G.SectionTextColor
	 NotificationDesc.TextSize = 16.000
	 NotificationDesc.TextWrapped = true
	 NotificationDesc.TextXAlignment = Enum.TextXAlignment.Center
	 NotificationDesc.TextYAlignment = Enum.TextYAlignment.Top
	 
	 OkayBtn.MouseEnter:Connect(function()
	TweenService:Create(OkayBtn, TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(30, 30, 30)}):Play()
	 end)
	 
	 OkayBtn.MouseLeave:Connect(function()
	TweenService:Create(OkayBtn, TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(25, 25, 25)}):Play()
	 end)
	 
	 OkayBtn.MouseButton1Click:Connect(function()
	NotificationFrame:TweenSize(UDim2.new(0, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
	 
	wait(0.4)
	 
	TweenService:Create(NotificationHold, TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundTransparency = 1}):Play()
	 
	wait(.3)
	 
	NotificationHold:Destroy()
	 end)
	 end
	
	
	local Tab = Instance.new("ImageLabel")
	local WindowStrokelol = Instance.new("UIStroke")
	 Tab.Name = "Tab"
	 Tab.Parent = Top
	 Tab.BackgroundColor3 = Color3.fromRGB(42, 42, 42)
	 Tab.ImageTransparency = 1
	 Tab.Position = UDim2.new(0, 160, 0, -2)
	 Tab.Size = UDim2.new(0, 410, 0, 29)
	 Tab.Image = "rbxassetid://6675147486"
	 
	 WindowStrokelol.Name = "WindowStroke"
	 WindowStrokelol.Parent = Tab
	 WindowStrokelol.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	 WindowStrokelol.Color = Color3.fromRGB(255,255,255)
	 WindowStrokelol.LineJoinMode = Enum.LineJoinMode.Round
	 WindowStrokelol.Thickness = 1
	 WindowStrokelol.Transparency = 0
	 WindowStrokelol.Enabled = true
	 WindowStrokelol.Archivable = true
	 
	 local TCNR = Instance.new("UICorner")
	 TCNR.Name = "TCNR"
	 TCNR.Parent = Tab
	 
	 local ScrollTab = Instance.new("ScrollingFrame")
	 ScrollTab.Name = "ScrollTab"
	 ScrollTab.Parent = Tab
	 ScrollTab.Active = true
	 ScrollTab.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
	 ScrollTab.BackgroundTransparency = 0
	 ScrollTab.Size = UDim2.new(0, 433, 0, 29)
	 ScrollTab.CanvasSize = UDim2.new(0, 0, 0, 0)
	 ScrollTab.ScrollBarThickness = 0
	 
	 local PLL = Instance.new("UIListLayout")
	 PLL.Name = "PLL"
	 PLL.Parent = ScrollTab
	 PLL.FillDirection = Enum.FillDirection.Horizontal
	 PLL.SortOrder = Enum.SortOrder.LayoutOrder
	 PLL.Padding = UDim.new(0)
	 
	 local PPD = Instance.new("UIPadding")
	 PPD.Name = "PPD"
	 PPD.Parent = ScrollTab
	 PPD.PaddingLeft = UDim.new(0.01)
	 
	 local Page = Instance.new("Frame")
	 local WindowStrokeshit = Instance.new("UIStroke")
	 Page.Name = "Page"
	 Page.Parent = Main
	 Page.BackgroundColor3 = Color3.fromRGB(42, 42, 42)
	 Page.BackgroundTransparency = 1
	 Page.Position = UDim2.new(0, 1, 0.100000003, -5)
	 Page.Size = UDim2.new(0, 300, 0, 380)
	 
	 WindowStrokeshit.Name = "WindowStroke"
	 WindowStrokeshit.Parent = Page
	 WindowStrokeshit.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	 WindowStrokeshit.Color = Color3.fromRGB(255,255,255)
	 WindowStrokeshit.LineJoinMode = Enum.LineJoinMode.Round
	 WindowStrokeshit.Thickness = 1
	 WindowStrokeshit.Transparency = 0
	 WindowStrokeshit.Archivable = false
	 WindowStrokeshit.Enabled = true
	 
	 local lolshit = Instance.new("UICorner")
	 
	 lolshit.Parent = Top1
	 
	 
	 local PCNR = Instance.new("UICorner")
	 PCNR.Name = "PCNR"
	 PCNR.Parent = Page
	 
	 local MainPage = Instance.new("Frame")
	 MainPage.Name = "MainPage"
	 MainPage.Parent = Page
	 MainPage.ClipsDescendants = true
	 MainPage.BackgroundColor3 = Color3.fromRGB(255,255,255)
	 MainPage.BackgroundTransparency = 1.000
	 MainPage.Size = UDim2.new(0, 300, 0, 380)
	 
	 local PageList = Instance.new("Folder")
	 PageList.Name = "PageList"
	 PageList.Parent = MainPage
	 
	 local UIPageLayout = Instance.new("UIPageLayout")
	 
	 UIPageLayout.Parent = PageList
	 UIPageLayout.SortOrder = Enum.SortOrder.LayoutOrder
	 UIPageLayout.EasingDirection = Enum.EasingDirection.InOut
	 UIPageLayout.EasingStyle = Enum.EasingStyle.Quad
	 UIPageLayout.FillDirection = Enum.FillDirection.Vertical
	 UIPageLayout.Padding = UDim.new(0, 15)
	 UIPageLayout.TweenTime = 0.400
	 UIPageLayout.GamepadInputEnabled = false
	 UIPageLayout.ScrollWheelInputEnabled = false
	 UIPageLayout.TouchInputEnabled = false
	
	local Page2 = Instance.new("Frame")
	 local WindowStrokeshit2 = Instance.new("UIStroke")
	 Page2.Name = "Page2"
	 Page2.Parent = Main
	 Page2.BackgroundColor3 = Color3.fromRGB(42, 42, 42)
	 Page2.BackgroundTransparency = 1
	 Page2.Position = UDim2.new(0, 302, 0.100000003, -5)
	 Page2.Size = UDim2.new(0, 300, 0, 378)
	 
	 WindowStrokeshit2.Name = "WindowStroke"
	 WindowStrokeshit2.Parent = Page2
	 WindowStrokeshit2.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	 WindowStrokeshit2.Color = Color3.fromRGB(255,255,255)
	 WindowStrokeshit2.LineJoinMode = Enum.LineJoinMode.Round
	 WindowStrokeshit2.Thickness = 1
	 WindowStrokeshit2.Transparency = 0
	 WindowStrokeshit2.Archivable = false
	 WindowStrokeshit2.Enabled = true
	 
	 local lolshit2 = Instance.new("UICorner")
	 
	 lolshit2.Parent = Top1
	 
	 
	 local PCNR2 = Instance.new("UICorner")
	 PCNR2.Name = "PCNR"
	 PCNR2.Parent = Page2
	 
	 local MainPage2 = Instance.new("Frame")
	 MainPage2.Name = "MainPage"
	 MainPage2.Parent = Page2
	 MainPage2.ClipsDescendants = true
	 MainPage2.BackgroundColor3 = Color3.fromRGB(255,255,255)
	 MainPage2.BackgroundTransparency = 1.000
	 MainPage2.Size = UDim2.new(0, 300, 0, 378)
	 
	 local PageList2 = Instance.new("Folder")
	 PageList2.Name = "PageList"
	 PageList2.Parent = MainPage2
	 
	 local UIPageLayout2 = Instance.new("UIPageLayout")
	 
	 UIPageLayout2.Parent = PageList2
	 UIPageLayout2.SortOrder = Enum.SortOrder.LayoutOrder
	 UIPageLayout2.EasingDirection = Enum.EasingDirection.InOut
	 UIPageLayout2.EasingStyle = Enum.EasingStyle.Quad
	 UIPageLayout2.FillDirection = Enum.FillDirection.Vertical
	 UIPageLayout2.Padding = UDim.new(0, 15)
	 UIPageLayout2.TweenTime = 0.400
	 UIPageLayout2.GamepadInputEnabled = false
	 UIPageLayout2.ScrollWheelInputEnabled = false
	 UIPageLayout2.TouchInputEnabled = false
	 
	 MakeDraggable(Top,Main)
	 
	 UserInputService.InputBegan:Connect(function(input)
	if input.KeyCode == Enum.KeyCode[yoo] then
	if uihide == false then
	 uihide = true
	 Main:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0,true)
	else
	 uihide = false
	 Main:TweenSize(UDim2.new(0, 600, 0, 400),"Out","Quad",0,true)
	end
	end
	 end)
		
	
	
	 
		local uitab = {}
		
		function uitab:AddTab(text, img)
			local TabButton = Instance.new("TextButton")
			local TabImage = Instance.new("ImageLabel")
			local WindowStroke = Instance.new("UIStroke")
			local Label3 = Instance.new("TextLabel")
			local LabelTitle = Instance.new("TextLabel")
	local LabelTitle = Instance.new("TextLabel")
	
			TabButton.Parent = ScrollTab
			TabButton.Name = text.."Server"
			TabButton.Text = text
			TabButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
			TabButton.BackgroundTransparency = 0.1
			TabButton.Position = UDim2.new(0, 2, 0, 0)
			TabButton.Size = UDim2.new(0, 100, 0, 28)
			TabButton.Font = Enum.Font.Code
			TabButton.TextColor3 = Color3.fromRGB(255, 225, 225)
			TabButton.TextSize = 12.000
			TabButton.TextTransparency = 0
			
			
	local MCNR1 = Instance.new("UICorner")
		MCNR1.Name = "MCNR"
		MCNR1.Parent = TabButton
	
	WindowStroke.Name = "WindowStroke"
	 WindowStroke.Parent = TabButton
	 WindowStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	 WindowStroke.Color = Color3.fromRGB(45,45,45)
	 WindowStroke.LineJoinMode = Enum.LineJoinMode.Round
	 WindowStroke.Thickness = 1
	 WindowStroke.Transparency = 0
	 WindowStroke.Enabled = true
	 WindowStroke.Archivable = true
	
			local MainFramePage = Instance.new("ScrollingFrame")
			MainFramePage.Name = text.."_Page"
			MainFramePage.Parent = PageList
			MainFramePage.Active = true
			MainFramePage.BackgroundColor3 = Color3.fromRGB(51,255,255)
			MainFramePage.BackgroundTransparency = 1.000
			MainFramePage.BorderSizePixel = 1
			MainFramePage.Size = UDim2.new(0, 390, 0, 370)
			MainFramePage.CanvasSize = UDim2.new(0, 0, 0, 0)
			MainFramePage.ScrollBarThickness = 0
			
	
			
			local UIPadding = Instance.new("UIPadding")
			local UIListLayout = Instance.new("UIListLayout")
			
			UIPadding.Parent = MainFramePage
			UIPadding.PaddingLeft = UDim.new(0, 10)
			UIPadding.PaddingTop = UDim.new(0, 10)
	
			UIListLayout.Padding = UDim.new(0,4)
			UIListLayout.Parent = MainFramePage
			UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
			
			TabButton.MouseButton1Click:Connect(function()
			Sound = Instance.new("Sound", game:GetService("Workspace")) -- ตรงนี้ไม่ต้องไปสน นาจา ;0;
	Sound.Name = "Notify" -- ชื่อเสียง \;
	Sound.SoundId = "rbxassetid://903267862" -- เลขขขขขเสียง ;/
	Sound.Looped = false -- วนลูป :>
	Sound.Playing = true -- เล่นเสียง :<
	Sound.Volume = 1 -- ระดับเสียงงงงงงง ;-;
				for i,v in next, ScrollTab:GetChildren() do
					if v:IsA("TextButton") then
						TweenService:Create(
							v,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0}
						):Play()
					end
					TweenService:Create(
						TabButton,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				for i,v in next, PageList:GetChildren() do
					currentpage = string.gsub(TabButton.Name,"Server","").."_Page"
					if v.Name == currentpage then
						UIPageLayout:JumpTo(v)
					end
				end
			end)
	
			if abc == false then
				
				for i,v in next, ScrollTab:GetChildren() do
					if v:IsA("TextButton") then
						TweenService:Create(
							v,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0}
						):Play()
					end
					TweenService:Create(
						TabButton,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				UIPageLayout:JumpToIndex(0)
				abc = true
			end
			
			game:GetService("RunService").Stepped:Connect(function()
				pcall(function()
					MainFramePage.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 20)
					ScrollTab.CanvasSize = UDim2.new(0,PLL.AbsoluteContentSize.X + 20,0,0)
				end)
			end)
	 
	 coroutine.wrap(function()
	 while wait() do
	 end
	 end)()
	 
		 
	 
	 coroutine.wrap(function()
	 while wait() do
	 end
	 end)()
		
		
		local MainFramePage2 = Instance.new("ScrollingFrame")
			MainFramePage2.Name = text.."_Page"
			MainFramePage2.Parent = PageList2
			MainFramePage2.Active = true
			MainFramePage2.BackgroundColor3 = Color3.fromRGB(51,255,255)
			MainFramePage2.BackgroundTransparency = 1.000
			MainFramePage2.BorderSizePixel = 0
			MainFramePage2.Size = UDim2.new(0, 320, 0, 370)
			MainFramePage2.CanvasSize = UDim2.new(0, 0, 0, 0)
			MainFramePage2.ScrollBarThickness = 0
			
			local UIPadding2 = Instance.new("UIPadding")
			local UIListLayout2 = Instance.new("UIListLayout")
			
			UIPadding2.Parent = MainFramePage2
			UIPadding2.PaddingLeft = UDim.new(0, 10)
			UIPadding2.PaddingTop = UDim.new(0, 10)
	
			UIListLayout2.Padding = UDim.new(0,4)
			UIListLayout2.Parent = MainFramePage2
			UIListLayout2.SortOrder = Enum.SortOrder.LayoutOrder
			
			TabButton.MouseButton1Click:Connect(function()
				for i,v in next, ScrollTab:GetChildren() do
					if v:IsA("TextButton") then
						TweenService:Create(
							v,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0}
						):Play()
					end
					TweenService:Create(
						TabButton,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				for i,v in next, PageList2:GetChildren() do
					currentpage = string.gsub(TabButton.Name,"Server","").."_Page"
					if v.Name == currentpage then
						UIPageLayout2:JumpTo(v)
					end
				end
			end)
	
			if abc == false then
				for i,v in next, ScrollTab:GetChildren() do
					if v:IsA("TextButton") then
						TweenService:Create(
							v,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0}
						):Play()
					end
					TweenService:Create(
						TabButton,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				UIPageLayout2:JumpToIndex(0)
				abc = true
			end
			
			game:GetService("RunService").Stepped:Connect(function()
				pcall(function()
					MainFramePage2.CanvasSize = UDim2.new(0,0,0,UIListLayout2.AbsoluteContentSize.Y + 20)
					ScrollTab.CanvasSize = UDim2.new(0,PLL.AbsoluteContentSize.X + 20,0,0)
				end)
			end)
	 
	 coroutine.wrap(function()
	 while wait() do
	 end
	 end)()
	 
		 
	 
	 coroutine.wrap(function()
	 while wait() do
	 end
	 end)()
		local abcd = false
		 function uitab:AddTabH(text,img)
		 local mainDiscord = Instance.new("ImageButton")
	
		 mainDiscord.Name = "mainDiscord"
		mainDiscord.Parent = Top
		mainDiscord.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		mainDiscord.BackgroundTransparency = 1.000
		mainDiscord.Position = UDim2.new(0, 565, 0, 0)
		mainDiscord.Size = UDim2.new(0, 30, 0, 30)
		mainDiscord.Image = "rbxassetid://"..tostring(img)
		mainDiscord.ImageColor3 = Color3.fromRGB(200, 200, 200)
		
			local MainFramePage = Instance.new("ScrollingFrame")
			MainFramePage.Name = text.."_Page"
			MainFramePage.Parent = PageList
			MainFramePage.Active = true
			MainFramePage.BackgroundColor3 = Color3.fromRGB(51,255,255)
			MainFramePage.BackgroundTransparency = 1.000
			MainFramePage.BorderSizePixel = 1
			MainFramePage.Size = UDim2.new(0, 390, 0, 370)
			MainFramePage.CanvasSize = UDim2.new(0, 0, 0, 0)
			MainFramePage.ScrollBarThickness = 0
			
	
			
			local UIPadding = Instance.new("UIPadding")
			local UIListLayout = Instance.new("UIListLayout")
			
			UIPadding.Parent = MainFramePage
			UIPadding.PaddingLeft = UDim.new(0, 10)
			UIPadding.PaddingTop = UDim.new(0, 10)
	
			UIListLayout.Padding = UDim.new(0,4)
			UIListLayout.Parent = MainFramePage
			UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
			
			mainDiscord.MouseButton1Click:Connect(function()
			Sound = Instance.new("Sound", game:GetService("Workspace")) -- ตรงนี้ไม่ต้องไปสน นาจา ;0;
	Sound.Name = "Notify" -- ชื่อเสียง \;
	Sound.SoundId = "rbxassetid://3020841054" -- เลขขขขขเสียง ;/
	Sound.Looped = false -- วนลูป :>
	Sound.Playing = true -- เล่นเสียง :<
	Sound.Volume = 1 -- ระดับเสียงงงงงงง ;-;
				for i,v in next, ScrollTab:GetChildren() do
					if v:IsA("TextButton") then
						TweenService:Create(
							v,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0}
						):Play()
					end
					TweenService:Create(
						TabButton,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				for i,v in next, PageList:GetChildren() do
					currentpage2 = string.gsub(TabButton.Name,"Server","").."_Page"
					if v.Name == currentpage2 then
						UIPageLayout:JumpTo(v)
					end
				end
			end)
	
			if abc == false then
				
				for i,v in next, ScrollTab:GetChildren() do
					if v:IsA("TextButton") then
						TweenService:Create(
							v,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0}
						):Play()
					end
					TweenService:Create(
						TabButton,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				UIPageLayout:JumpToIndex(0)
				abc = true
			end
			
			game:GetService("RunService").Stepped:Connect(function()
				pcall(function()
					MainFramePage.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 20)
					ScrollTab.CanvasSize = UDim2.new(0,PLL.AbsoluteContentSize.X + 20,0,0)
				end)
			end)
	 
	 coroutine.wrap(function()
	 while wait() do
	 end
	 end)()
	 
		 
	 
	 coroutine.wrap(function()
	 while wait() do
	 end
	 end)()
		
		
		local MainFramePage2 = Instance.new("ScrollingFrame")
			MainFramePage2.Name = text.."_Page"
			MainFramePage2.Parent = PageList2
			MainFramePage2.Active = true
			MainFramePage2.BackgroundColor3 = Color3.fromRGB(51,255,255)
			MainFramePage2.BackgroundTransparency = 1.000
			MainFramePage2.BorderSizePixel = 0
			MainFramePage2.Size = UDim2.new(0, 320, 0, 370)
			MainFramePage2.CanvasSize = UDim2.new(0, 0, 0, 0)
			MainFramePage2.ScrollBarThickness = 0
			
			local UIPadding2 = Instance.new("UIPadding")
			local UIListLayout2 = Instance.new("UIListLayout")
			
			UIPadding2.Parent = MainFramePage2
			UIPadding2.PaddingLeft = UDim.new(0, 10)
			UIPadding2.PaddingTop = UDim.new(0, 10)
	
			UIListLayout2.Padding = UDim.new(0,4)
			UIListLayout2.Parent = MainFramePage2
			UIListLayout2.SortOrder = Enum.SortOrder.LayoutOrder
			
			mainDiscord.MouseButton1Click:Connect(function()
				for i,v in next, ScrollTab:GetChildren() do
					if v:IsA("TextButton") then
						TweenService:Create(
							v,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0}
						):Play()
					end
					TweenService:Create(
						TabButton,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				for i,v in next, PageList2:GetChildren() do
					currentpage2 = string.gsub(TabButton.Name,"Server","").."_Page"
					if v.Name == currentpage2 then
						UIPageLayout2:JumpTo(v)
					end
				end
			end)
	
			if abc == false then
				for i,v in next, ScrollTab:GetChildren() do
					if v:IsA("TextButton") then
						TweenService:Create(
							v,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{TextTransparency = 0}
						):Play()
					end
					TweenService:Create(
						mainDiscord,
						TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end
				UIPageLayout2:JumpToIndex(0)
				abc = true
			end
			
			game:GetService("RunService").Stepped:Connect(function()
				pcall(function()
					MainFramePage2.CanvasSize = UDim2.new(0,0,0,UIListLayout2.AbsoluteContentSize.Y + 20)
					ScrollTab.CanvasSize = UDim2.new(0,PLL.AbsoluteContentSize.X + 20,0,0)
				end)
			end)
	 
	 coroutine.wrap(function()
	 while wait() do
	 end
	 end)()
	
	 
		 
	 
	 coroutine.wrap(function()
	 while wait() do
	 end
	 end)()
		end
		
			local main = {}
			function main:AddButtonRight(text,callback)
				local Button2 = Instance.new("Frame")
				local UICorner2 = Instance.new("UICorner")
				local TextBtn2 = Instance.new("TextButton")
				local UICorner_1 = Instance.new("UICorner")
				local Black2 = Instance.new("Frame")
				local UICorner_2 = Instance.new("UICorner")
				
				Button2.Name = "Button"
				Button2.Parent = MainFramePage2
				Button2.BackgroundColor3 = _G.Color
				Button2.Size = UDim2.new(0, 280, 0, 28)
				
				UICorner2.CornerRadius = UDim.new(0, 5)
				UICorner2.Parent = Button2
				
				TextBtn2.Name = "TextBtn"
				TextBtn2.Parent = Button2
				TextBtn2.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				TextBtn2.Position = UDim2.new(0, 1, 0, 1)
				TextBtn2.Size = UDim2.new(0, 278, 0, 26)
				TextBtn2.AutoButtonColor = false
				TextBtn2.Font = Enum.Font.Code
				TextBtn2.Text = text
				TextBtn2.TextColor3 = Color3.fromRGB(225, 225, 225)
				TextBtn2.TextSize = 12.000
				
				UICorner_1.CornerRadius = UDim.new(0, 5)
				UICorner_1.Parent = TextBtn2
				
				Black2.Name = "Black"
				Black2.Parent = Button2
				Black2.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Black2.BackgroundTransparency = 1.000
				Black2.BorderSizePixel = 0
				Black2.Position = UDim2.new(0, 1, 0, 1)
				Black2.Size = UDim2.new(0, 280, 0, 26)
				
				UICorner_2.CornerRadius = UDim.new(0, 5)
				UICorner_2.Parent = Black2
	
				TextBtn2.MouseEnter:Connect(function()
					TweenService:Create(
						Black2,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundTransparency = 0.7}
					):Play()
				end)
				TextBtn2.MouseLeave:Connect(function()
					TweenService:Create(
						Black2,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundTransparency = 1}
					):Play()
				end)
				TextBtn2.MouseButton1Click:Connect(function()
					TextBtn2.TextSize = 0
					TweenService:Create(
						TextBtn2,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextSize = 12}
					):Play()
					callback()
				end)
			end
			
			function main:AddButtonLeft(text,callback)
				local Button = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local TextBtn = Instance.new("TextButton")
				local UICorner_2 = Instance.new("UICorner")
				local Black = Instance.new("Frame")
				local UICorner_3 = Instance.new("UICorner")
				
				Button.Name = "Button"
				Button.Parent = MainFramePage
				Button.BackgroundColor3 = _G.Color
				Button.Size = UDim2.new(0, 280, 0, 28)
				
				UICorner.CornerRadius = UDim.new(0, 5)
				UICorner.Parent = Button
				
				TextBtn.Name = "TextBtn"
				TextBtn.Parent = Button
				TextBtn.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				TextBtn.Position = UDim2.new(0, 1, 0, 1)
				TextBtn.Size = UDim2.new(0, 278, 0, 26)
				TextBtn.AutoButtonColor = false
				TextBtn.Font = Enum.Font.Code
				TextBtn.Text = text
				TextBtn.TextColor3 = Color3.fromRGB(225, 225, 225)
				TextBtn.TextSize = 12.000
				
				UICorner_2.CornerRadius = UDim.new(0, 5)
				UICorner_2.Parent = TextBtn
				
				Black.Name = "Black"
				Black.Parent = Button
				Black.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Black.BackgroundTransparency = 1.000
				Black.BorderSizePixel = 0
				Black.Position = UDim2.new(0, 1, 0, 1)
				Black.Size = UDim2.new(0, 280, 0, 26)
				
				UICorner_3.CornerRadius = UDim.new(0, 5)
				UICorner_3.Parent = Black
	
				TextBtn.MouseEnter:Connect(function()
					TweenService:Create(
						Black,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundTransparency = 0.7}
					):Play()
				end)
				TextBtn.MouseLeave:Connect(function()
					TweenService:Create(
						Black,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundTransparency = 1}
					):Play()
				end)
				TextBtn.MouseButton1Click:Connect(function()
					TextBtn.TextSize = 0
					TweenService:Create(
						TextBtn,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextSize = 12}
					):Play()
					callback()
				end)
			end
			function main:AddToggleLeft(text,config,callback)
				config = config or false
				local toggled = config
				local Toggle = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
			local Button = Instance.new("TextButton")
			local True = Instance.new("TextLabel")
				local UICorner_2 = Instance.new("UICorner")
				local Label = Instance.new("TextLabel")
				local ToggleImage = Instance.new("Frame")
				local UICorner_3 = Instance.new("UICorner")
				local Circle = Instance.new("ImageLabel")
				local UICorner_4 = Instance.new("UICorner")
	local ImageLabel = Instance.new("ImageLabel")
	local Space = Instance.new("TextLabel")
	
				Toggle.Name = "Toggle"
				Toggle.Parent = MainFramePage
				Toggle.BackgroundColor3 = _G.Color
				Toggle.Size = UDim2.new(0, 280, 0, 28)
	
				UICorner.CornerRadius = UDim.new(0, 5)
				UICorner.Parent = Toggle
	
				Button.Name = "Button"
				Button.Parent = Toggle
				Button.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				Button.Position = UDim2.new(0, 1, 0, 1)
				Button.Size = UDim2.new(0, 278, 0, 26)
				Button.AutoButtonColor = false
				Button.Font = Enum.Font.SourceSans
				Button.Text = ""
				Button.TextColor3 = Color3.fromRGB(0, 0, 0)
				Button.TextSize = 11.000
	
				UICorner_2.CornerRadius = UDim.new(0, 5)
				UICorner_2.Parent = Button
	
				Label.Name = "Label"
				Label.Parent = Toggle
				Label.BackgroundColor3 = Color3.fromRGB(0,255,255)
				Label.BackgroundTransparency = 1.000
				Label.Position = UDim2.new(0, 1, 0, 1)
				Label.Size = UDim2.new(0, 278, 0, 26)
				Label.Font = Enum.Font.Code
				Label.Text = text
				Label.TextColor3 = Color3.fromRGB(225, 225, 225)
				Label.TextSize = 12.000
				
	
			ToggleImage.Name = "ToggleImage"
				ToggleImage.Parent = Toggle
				ToggleImage.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				ToggleImage.Position = UDim2.new(0, 250, 0, 4)
				ToggleImage.Size = UDim2.new(0, 22, 0, 20)
	
				UICorner_3.CornerRadius = UDim.new(0, 4)
				UICorner_3.Parent = ToggleImage
	
				Circle.Name = "Circle"
				Circle.Parent = ToggleImage
				Circle.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				Circle.Position = UDim2.new(0, 2, 0, 2)
				Circle.Size = UDim2.new(0, 18, 0, 16)
				
				True.Name = "True"
				True.Parent = Circle
				True.BackgroundTransparency = 1.000
				True.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				True.Position = UDim2.new(0, 0, 0, 0)
				True.Size = UDim2.new(0, 18, 0, 16)
				True.Font = Enum.Font.SourceSans
				True.Text = ""
				True.TextColor3 = Color3.fromRGB(0, 0, 0)
				True.TextSize = 16.000
	
				UICorner_4.CornerRadius = UDim.new(0, 0)
				UICorner_4.Parent = Circle
	
				Button.MouseButton1Click:Connect(function()
					if toggled == false then
						toggled = true
						True.Text = "✔"
						Circle:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
						TweenService:Create(
							Circle,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{BackgroundColor3 = Color3.fromRGB(0, 255, 0)}
						):Play()
					else
						toggled = false
						True.Text = ""
						Circle:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
						TweenService:Create(
							Circle,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{BackgroundColor3 = Color3.fromRGB(30, 30, 30)}
						):Play()
						
					end
					pcall(callback,toggled)
				end)
	
				if config == true then
					toggled = true
					True.Text = "✔"
					Circle:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
					TweenService:Create(
						Circle,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(0, 255, 0)}
					):Play()
					pcall(callback,toggled)
				end
			end
			
	function main:AddToggleRight(text,config,callback)
				config = config or false
				local toggledd = config
				local Togglee = Instance.new("Frame")
				local UICornerr = Instance.new("UICorner")
				local Truea =Instance.new("TextLabel")
			local Buttonn = Instance.new("TextButton")
				local UICorner_22 = Instance.new("UICorner")
				local Labell = Instance.new("TextLabel")
				local ToggleImagee = Instance.new("Frame")
				local UICorner_33 = Instance.new("UICorner")
				local Circlee = Instance.new("Frame")
				local UICorner_44 = Instance.new("UICorner")
	local ImageLabell = Instance.new("ImageLabel")
	local Spacee = Instance.new("TextLabel")
	
				Togglee.Name = "Toggle"
				Togglee.Parent = MainFramePage2
				Togglee.BackgroundColor3 = _G.Color
				Togglee.Size = UDim2.new(0, 280, 0, 28)
	
				UICornerr.CornerRadius = UDim.new(0, 5)
				UICornerr.Parent = Togglee
	
				Buttonn.Name = "Button"
				Buttonn.Parent = Togglee
				Buttonn.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				Buttonn.Position = UDim2.new(0, 1, 0, 1)
				Buttonn.Size = UDim2.new(0, 278, 0, 26)
				Buttonn.AutoButtonColor = false
				Buttonn.Font = Enum.Font.SourceSans
				Buttonn.Text = ""
				Buttonn.TextColor3 = Color3.fromRGB(0, 0, 0)
				Buttonn.TextSize = 11.000
	
				UICorner_22.CornerRadius = UDim.new(0, 5)
				UICorner_22.Parent = Buttonn
	
				Labell.Name = "Label"
				Labell.Parent = Togglee
				Labell.BackgroundColor3 = Color3.fromRGB(51,255,255)
				Labell.BackgroundTransparency = 1.000
				Labell.Position = UDim2.new(0, 1, 0, 1)
				Labell.Size = UDim2.new(0, 278, 0, 26)
				Labell.Font = Enum.Font.Code
				Labell.Text = text
				Labell.TextColor3 = Color3.fromRGB(225, 225, 225)
				Labell.TextSize = 12.000
				
	
	
	
			 ToggleImagee.Name = "ToggleImage"
				ToggleImagee.Parent = Togglee
				ToggleImagee.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				ToggleImagee.Position = UDim2.new(0, 250, 0, 5)
				ToggleImagee.Size = UDim2.new(0, 22, 0, 20)
	
				UICorner_33.CornerRadius = UDim.new(0, 4)
				UICorner_33.Parent = ToggleImagee
	
				Circlee.Name = "Circle"
				Circlee.Parent = ToggleImagee
				Circlee.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				Circlee.Position = UDim2.new(0, 2, 0, 2)
				Circlee.Size = UDim2.new(0, 18, 0, 16)
	
	Truea.Name = "Truea"
				Truea.Parent = Circlee
				Truea.BackgroundTransparency = 1.000
				Truea.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Truea.Position = UDim2.new(0, 0, 0, 0)
				Truea.Size = UDim2.new(0, 18, 0, 16)
				Truea.Font = Enum.Font.SourceSans
				Truea.Text = ""
				Truea.TextColor3 = Color3.fromRGB(0, 0, 0)
				Truea.TextSize = 16.000
	
				UICorner_44.CornerRadius = UDim.new(0, 0)
				UICorner_44.Parent = Circlee
	
				Buttonn.MouseButton1Click:Connect(function()
					if toggledd == false then
						toggledd = true
						Truea.Text = "✔"
						Circlee:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
						TweenService:Create(
							Circlee,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{BackgroundColor3 = Color3.fromRGB(0, 255, 0)}
						):Play()
					else
						toggledd = false
						Truea.Text = ""
						Circlee:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
						TweenService:Create(
							Circlee,
							TweenInfo.new(0,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
							{BackgroundColor3 = Color3.fromRGB(30, 30, 30)}
						):Play()
					end
					pcall(callback,toggledd)
				end)
	
				if config == true then
					toggledd = true
					Truea.Text = "✔"
					Circlee:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0,true)
					TweenService:Create(
						Circlee,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(0, 255, 0)}
					):Play()
					pcall(callback,toggledd)
				end
			end
	
			
	
			
			function main:AddDropdownLeft(droptitle, list, config, callback)
	local config = config or ""
	local dropfunc = {}
	local list = list or {}
	local DropToggled = false
	local DropSizeFrame = Instance.new("Frame")
	local Frame = Instance.new("Frame")
	local UIStroke = Instance.new("UIStroke")
	local DropCover = Instance.new("Frame")
	local UICorner = Instance.new("UICorner")
	local UICorner2 = Instance.new("UICorner")
	local ImageLabel = Instance.new("ImageLabel")
	local Space = Instance.new("TextLabel")
	local Title = Instance.new("TextLabel")
	local ImageButton = Instance.new("ImageButton")
	local DropStrokeList = Instance.new("UIStroke")
	local DropTextList = Instance.new("TextLabel")
	
	-- Prop --
	DropSizeFrame.Name = droptitle or "DropSizeFrame"
	DropSizeFrame.Parent = MainFramePage
	DropSizeFrame.BackgroundColor3 = _G.SectionColor
	DropSizeFrame.BackgroundTransparency = 1.000
	DropSizeFrame.Size = UDim2.new(0, 280, 0, 60)
	
	Frame.Name = "Frame"
	Frame.Parent = DropSizeFrame
	Frame.BackgroundColor3 = Color3.fromRGB(30,30,30)
	Frame.BorderSizePixel = 0
	Frame.Position = UDim2.new(0, 3, 0, 0)
	Frame.Size = UDim2.new(0, 278, 0, 60)
	
	UIStroke.Name = "UIStroke"
	UIStroke.Parent = Frame
	UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	UIStroke.Color = Color3.fromRGB(255,255,255)
	UIStroke.LineJoinMode = Enum.LineJoinMode.Round
	UIStroke.Thickness = 0.7
	UIStroke.Transparency = 0
	UIStroke.Enabled = true
	UIStroke.Archivable = true
	
	UICorner.Parent = Frame
	UICorner.CornerRadius = UDim.new(0, 3)
	
	DropCover.Name = "DropCover"
	DropCover.Parent = Frame
	DropCover.BackgroundColor3 = _G.BackgroundItemColor
	DropCover.BackgroundTransparency = 1.000
	DropCover.BorderSizePixel = 0
	DropCover.Position = UDim2.new(0, 0, 0, 0)
	DropCover.Size = UDim2.new(0, 202, 0, 30)
	
	ImageLabel.Name = "ImageLabel"
	ImageLabel.Parent = DropCover
	ImageLabel.BackgroundColor3 = _G.SectionColor
	ImageLabel.BackgroundTransparency = 1.000
	ImageLabel.BorderSizePixel = 0
	ImageLabel.Position = UDim2.new(0, 5, 0, 6)
	ImageLabel.Size = UDim2.new(0, 18, 0, 18)
	ImageLabel.Image = "rbxassetid://8825010231"
	ImageLabel.ImageColor3 = Color3.fromRGB(255,255,255)
	
	Space.Name = "Space"
	Space.Parent = DropCover
	Space.BackgroundColor3 = _G.SectionColor
	Space.BackgroundTransparency = 1.000
	Space.Position = UDim2.new(0, 30, 0, 0)
	Space.Size = UDim2.new(0, 15, 0, 30)
	Space.Font = Enum.Font.Code
	Space.Text = "|"
	Space.TextSize = 13.000
	Space.TextColor3 = Color3.fromRGB(255,255,255)
	Space.TextXAlignment = Enum.TextXAlignment.Center
	
	Title.Name = "Title"
	Title.Parent = DropCover
	Title.BackgroundColor3 = _G.SectionColor
	Title.BackgroundTransparency = 1.000
	Title.Position = UDim2.new(0, 50, 0, 0)
	Title.Size = UDim2.new(0, 207, 0, 30)
	Title.Font = Enum.Font.Code
	Title.Text = tostring(droptitle) or "drop Title"
	Title.TextColor3 = Color3.fromRGB(255,255,255)
	Title.TextSize = 12.000
	Title.TextXAlignment = Enum.TextXAlignment.Left
	
	ImageButton.Name = "ImageButton"
	ImageButton.Parent = DropCover
	ImageButton.BackgroundColor3 = _G.WindowBackgroundColor
	ImageButton.BackgroundTransparency = 1.000
	ImageButton.Position = UDim2.new(0, 250, 0, 7)
	ImageButton.Size = UDim2.new(0, 23, 0, 18)
	ImageButton.Image = "rbxassetid://6583628103"
	ImageButton.ImageColor3 = Color3.fromRGB(51,255,255)
	ImageButton.Rotation = 180
	
	DropTextList.Name = "DropTextList"
	DropTextList.Parent = Frame
	DropTextList.BackgroundColor3 = _G.BackgroundItemColor
	DropTextList.BackgroundTransparency = 1.000
	DropTextList.Position = UDim2.new(0, 3, 0, 30)
	DropTextList.Size = UDim2.new(0, 278, 0, 25)
	DropTextList.Font = Enum.Font.Code
	DropTextList.Text = v or config or"Select First"
	DropTextList.TextColor3 = Color3.fromRGB(255,255,255)
	DropTextList.TextSize = 12.000
	DropTextList.TextXAlignment = Enum.TextXAlignment.Center
	
	UICorner2.Parent = DropTextList
	UICorner2.CornerRadius = UDim.new(0,0)
	
	DropStrokeList.Name = "DropStrokeList"
	DropStrokeList.Parent = DropTextList
	DropStrokeList.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	DropStrokeList.Color = Color3.fromRGB(255,255,255)
	DropStrokeList.LineJoinMode = Enum.LineJoinMode.Round
	DropStrokeList.Thickness = 0.2
	DropStrokeList.Transparency = 0
	DropStrokeList.Enabled = true
	DropStrokeList.Archivable = true
	
	-- Adden Local --
	local DropItemScroll = Instance.new("ScrollingFrame")
	local DropItemLayout = Instance.new("UIListLayout")
	local DropItemStroke = Instance.new("UIStroke")
	
	-- Adden Prop --
	DropItemScroll.Name = "DropItemScroll"
	DropItemScroll.Parent = Frame
	DropItemScroll.BackgroundColor3 = _G.SectionColor
	DropItemScroll.BackgroundTransparency = 1.000
	DropItemScroll.Position = UDim2.new(0, 3, 0, 60)
	DropItemScroll.Size = UDim2.new(0, 280, 0, 0)
	DropItemScroll.ScrollBarThickness = 0
	DropItemScroll.CanvasSize = UDim2.new(0, 0, 0, 0)
	
	DropItemLayout.Name = "DropItemLayout"
	DropItemLayout.Parent = DropItemScroll
	DropItemLayout.SortOrder = Enum.SortOrder.LayoutOrder
	DropItemLayout.Padding = UDim.new(0, 0)
	
	DropItemStroke.Name = "DropItemStroke"
	DropItemStroke.Parent = DropItemScroll
	DropItemStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	DropItemStroke.Color = Color3.fromRGB(51,255,255)
	DropItemStroke.LineJoinMode = Enum.LineJoinMode.Round
	DropItemStroke.Thickness = 0
	DropItemStroke.Transparency = 0
	DropItemStroke.Enabled = true
	DropItemStroke.Archivable = true
	
	-- Dropdown Script--
	local ItemCount = 0
	local FrameSize = 0
	
	ImageButton.MouseButton1Click:Connect(function()
	 if DropToggled then
	DropToggled = false
	DropSizeFrame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	Frame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	DropItemScroll:TweenSize(UDim2.new(0, 278, 0, 0), 'InOut', 'Linear', 0.08)
	game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{Rotation = 180}
	):Play()
	game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{ImageColor3 = Color3.fromRGB(51,255,255)}
	):Play()
	
	 else
	DropToggled = true
	DropSizeFrame:TweenSize(UDim2.new(0, 278, 0, 65 + FrameSize), 'InOut', 'Linear', 0.08)
	Frame:TweenSize(UDim2.new(0, 278, 0, 65 + FrameSize), 'InOut', 'Linear', 0.08)
	DropItemScroll:TweenSize(UDim2.new(0, 278, 0, FrameSize), 'InOut', 'Linear', 0.08)
	game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{Rotation = 0}
	):Play()
	game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{ImageColor3 = Color3.fromRGB(51,255,255)}
	):Play()
	 end
	end)
	
	for i,v in next, list do
	 ItemCount = ItemCount + 1
	 if ItemCount == 1 then
	FrameSize = 30
	 elseif ItemCount == 2 then
	FrameSize = 60
	 elseif ItemCount == 3 then
	FrameSize = 90
	 elseif ItemCount >= 3 then
	FrameSize = 120
	 end
	 
	 local ItemList = Instance.new("TextButton")
	 
	 ItemList.Name = "ItemList"
	 ItemList.Parent = DropItemScroll
	 ItemList.BackgroundColor3 = Color3.fromRGB(51,255,255)
	 ItemList.BackgroundTransparency = 1.000
	 ItemList.Size = UDim2.new(0, 278, 0, 30)
	 ItemList.AutoButtonColor = false
	 ItemList.Font = Enum.Font.Code
	 ItemList.TextColor3 = Color3.fromRGB(51,255,255)
	 ItemList.TextSize = 12.000
	 ItemList.Text = v or "None..."
	 ItemList.TextXAlignment = Enum.TextXAlignment.Center
	
	 ItemList.MouseEnter:Connect(function()
	game.TweenService:Create(ItemList, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{BackgroundTransparency = 0.8}
	):Play()
	 end)
	 ItemList.MouseLeave:Connect(function()
	game.TweenService:Create(ItemList, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{BackgroundTransparency = 1}
	):Play()
	 end)
	 
	 ItemList.MouseButton1Click:Connect(function()
	DropTextList.Text = v or "None..."
	pcall(callback, v)
	DropToggled = false
	DropSizeFrame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	Frame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	DropItemScroll:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
	game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{Rotation = 180}
	):Play()
	game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{ImageColor3 = Color3.fromRGB(51,255,255)}
	):Play()
	 end)
	 DropItemScroll.CanvasSize = UDim2.new(0, 0, 0, DropItemLayout.AbsoluteContentSize.Y)
	end
	
	function dropfunc:Clear()
						for _,v  in next, DropItemScroll:GetChildren() do
							if v:IsA("TextButton") then
								v:Destroy()
								FrameSize = 0
								ItemCount = 0
							end
						end
						DropTextList.Text = "Reset Succesfully..."
						DropToggled = false
						DropSizeFrame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
						Frame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
						DropItemScroll:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
						game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
							{Rotation = 180}
							):Play()
						game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
							{ImageColor3 = Color3.fromRGB(255,255,255)}
							):Play()
					end
	
	function dropfunc:Add(newadd)
	 newadd = newadd or {}
	 ItemCount = ItemCount + 1
	 if ItemCount == 1 then
	FrameSize = 30
	 elseif ItemCount == 2 then
	FrameSize = 60
	 elseif ItemCount == 3 then
	FrameSize = 90
	 elseif ItemCount >= 3 then
	FrameSize = 120
	 end
	 
	 local ItemList = Instance.new("TextButton")
	 ItemList.Name = "ItemList"
	 ItemList.Parent = DropItemScroll
	 ItemList.BackgroundColor3 = Color3.fromRGB(51,255,255)
	 ItemList.BackgroundTransparency = 1.000
	 ItemList.Size = UDim2.new(0, 278, 0, 30)
	 ItemList.AutoButtonColor = false
	 ItemList.Font = Enum.Font.Code
	 ItemList.TextColor3 = Color3.fromRGB(51,255,255)
	 ItemList.TextSize = 12.000
	 ItemList.Text = newadd or "None..."
	 ItemList.TextXAlignment = Enum.TextXAlignment.Center
	
	 ItemList.MouseEnter:Connect(function()
	game.TweenService:Create(ItemList, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{BackgroundTransparency = 0.8}
	):Play()
	 end)
	 ItemList.MouseLeave:Connect(function()
	game.TweenService:Create(ItemList, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{BackgroundTransparency = 1}
	):Play()
	 end)
	 
	 ItemList.MouseButton1Click:Connect(function()
	DropTextList.Text = newadd or "None..."
	pcall(callback, newadd)
	DropToggled = false
	DropSizeFrame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	Frame:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	DropItemScroll:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
	game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{Rotation = 180}
	):Play()
	game.TweenService:Create(ImageButton, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{ImageColor3 = Color3.fromRGB(51,255,255)}
	):Play()
	 end)
	 DropItemScroll.CanvasSize = UDim2.new(0, 0, 0, DropItemLayout.AbsoluteContentSize.Y)
	end
	return dropfunc
	end
	
		function main:AddDropdownRight(droptitle, list,  config, callback1)
	-- Local --
	local config = config or ""
	local dropfunc1 = {}
	local list = list or {}
	local DropToggled1 = false
	local DropSizeFrame1 = Instance.new("Frame")
	local Frame1 = Instance.new("Frame")
	local UIStroke1 = Instance.new("UIStroke")
	local DropCover1 = Instance.new("Frame")
	local UICorner1 = Instance.new("UICorner")
	local UICorner21 = Instance.new("UICorner")
	local ImageLabel1 = Instance.new("ImageLabel")
	local Space1 = Instance.new("TextLabel")
	local Title1 = Instance.new("TextLabel")
	local ImageButton1 = Instance.new("ImageButton")
	local DropStrokeList1 = Instance.new("UIStroke")
	local DropTextList1 = Instance.new("TextLabel")
	
	-- Prop --
	DropSizeFrame1.Name = droptitle or "DropSizeFrame"
	DropSizeFrame1.Parent = MainFramePage2
	DropSizeFrame1.BackgroundColor3 = _G.SectionColor
	DropSizeFrame1.BackgroundTransparency = 1.000
	DropSizeFrame1.Size = UDim2.new(0, 280, 0, 60)
	
	Frame1.Name = "Frame"
	Frame1.Parent = DropSizeFrame1
	Frame1.BackgroundColor3 = Color3.fromRGB(30,30,30)
	Frame1.BorderSizePixel = 0
	Frame1.Position = UDim2.new(0, 3, 0, 0)
	Frame1.Size = UDim2.new(0, 278, 0, 60)
	
	UIStroke1.Name = "UIStroke"
	UIStroke1.Parent = Frame1
	UIStroke1.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	UIStroke1.Color = Color3.fromRGB(255,255,255)
	UIStroke1.LineJoinMode = Enum.LineJoinMode.Round
	UIStroke1.Thickness = 0.7
	UIStroke1.Transparency = 0
	UIStroke1.Enabled = true
	UIStroke1.Archivable = true
	
	UICorner1.Parent = Frame1
	UICorner1.CornerRadius = UDim.new(0, 3)
	
	DropCover1.Name = "DropCover"
	DropCover1.Parent = Frame1
	DropCover1.BackgroundColor3 = _G.BackgroundItemColor
	DropCover1.BackgroundTransparency = 1.000
	DropCover1.BorderSizePixel = 0
	DropCover1.Position = UDim2.new(0, 0, 0, 0)
	DropCover1.Size = UDim2.new(0, 204, 0, 30)
	
	ImageLabel1.Name = "ImageLabel"
	ImageLabel1.Parent = DropCover1
	ImageLabel1.BackgroundColor3 = _G.SectionColor
	ImageLabel1.BackgroundTransparency = 1.000
	ImageLabel1.BorderSizePixel = 0
	ImageLabel1.Position = UDim2.new(0, 5, 0, 6)
	ImageLabel1.Size = UDim2.new(0, 18, 0, 18)
	ImageLabel1.Image = "rbxassetid://8825010231"
	ImageLabel1.ImageColor3 = Color3.fromRGB(255,255,255)
	
	Space1.Name = "Space"
	Space1.Parent = DropCover1
	Space1.BackgroundColor3 = _G.SectionColor
	Space1.BackgroundTransparency = 1.000
	Space1.Position = UDim2.new(0, 30, 0, 0)
	Space1.Size = UDim2.new(0, 15, 0, 30)
	Space1.Font = Enum.Font.Code
	Space1.Text = "|"
	Space1.TextSize = 13.000
	Space1.TextColor3 = Color3.fromRGB(255,255,255)
	Space1.TextXAlignment = Enum.TextXAlignment.Center
	
	Title1.Name = "Title"
	Title1.Parent = DropCover1
	Title1.BackgroundColor3 = _G.SectionColor
	Title1.BackgroundTransparency = 1.000
	Title1.Position = UDim2.new(0, 50, 0, 0)
	Title1.Size = UDim2.new(0, 278, 0, 30)
	Title1.Font = Enum.Font.Code
	Title1.Text = tostring(droptitle) or "drop Title"
	Title1.TextColor3 = Color3.fromRGB(255,255,255)
	Title1.TextSize = 12.000
	Title1.TextXAlignment = Enum.TextXAlignment.Left
	
	ImageButton1.Name = "ImageButton"
	ImageButton1.Parent = DropCover1
	ImageButton1.BackgroundColor3 = _G.WindowBackgroundColor
	ImageButton1.BackgroundTransparency = 1.000
	ImageButton1.Position = UDim2.new(0, 250, 0, 7)
	ImageButton1.Size = UDim2.new(0, 23, 0, 18)
	ImageButton1.Image = "rbxassetid://6583628103"
	ImageButton1.ImageColor3 = Color3.fromRGB(51,255,255)
	ImageButton1.Rotation = 180
	
	DropTextList1.Name = "DropTextList"
	DropTextList1.Parent = Frame1
	DropTextList1.BackgroundColor3 = _G.BackgroundItemColor
	DropTextList1.BackgroundTransparency = 1.000
	DropTextList1.Position = UDim2.new(0, 3, 0, 30)
	DropTextList1.Size = UDim2.new(0, 278, 0, 25)
	DropTextList1.Font = Enum.Font.Code
	DropTextList1.Text = v or config or "Select First"
	DropTextList1.TextColor3 = Color3.fromRGB(255,255,255)
	DropTextList1.TextSize = 12.000
	DropTextList1.TextXAlignment = Enum.TextXAlignment.Center
	
	UICorner21.Parent = DropTextList1
	UICorner21.CornerRadius = UDim.new(0,0)
	
	DropStrokeList1.Name = "DropStrokeList"
	DropStrokeList1.Parent = DropTextList1
	DropStrokeList1.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	DropStrokeList1.Color = Color3.fromRGB(255,255,255)
	DropStrokeList1.LineJoinMode = Enum.LineJoinMode.Round
	DropStrokeList1.Thickness = 0.2
	DropStrokeList1.Transparency = 0
	DropStrokeList1.Enabled = true
	DropStrokeList1.Archivable = true
	
	-- Adden Local --
	local DropItemScroll1 = Instance.new("ScrollingFrame")
	local DropItemLayout1 = Instance.new("UIListLayout")
	local DropItemStroke1 = Instance.new("UIStroke")
	
	-- Adden Prop --
	DropItemScroll1.Name = "DropItemScroll"
	DropItemScroll1.Parent = Frame1
	DropItemScroll1.BackgroundColor3 = _G.SectionColor
	DropItemScroll1.BackgroundTransparency = 1.000
	DropItemScroll1.Position = UDim2.new(0, 3, 0, 60)
	DropItemScroll1.Size = UDim2.new(0, 278, 0, 0)
	DropItemScroll1.ScrollBarThickness = 0
	DropItemScroll1.CanvasSize = UDim2.new(0, 0, 0, 0)
	
	DropItemLayout1.Name = "DropItemLayout"
	DropItemLayout1.Parent = DropItemScroll1
	DropItemLayout1.SortOrder = Enum.SortOrder.LayoutOrder
	DropItemLayout1.Padding = UDim.new(0, 0)
	
	DropItemStroke1.Name = "DropItemStroke"
	DropItemStroke1.Parent = DropItemScroll1
	DropItemStroke1.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	DropItemStroke1.Color = Color3.fromRGB(51,255,255)
	DropItemStroke1.LineJoinMode = Enum.LineJoinMode.Round
	DropItemStroke1.Thickness = 0
	DropItemStroke1.Transparency = 0
	DropItemStroke1.Enabled = true
	DropItemStroke1.Archivable = true
	
	-- Dropdown Script--
	local ItemCount1 = 0
	local FrameSize1 = 0
	
	ImageButton1.MouseButton1Click:Connect(function()
	 if DropToggled1 then
	DropToggled1 = false
	DropSizeFrame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	Frame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	DropItemScroll1:TweenSize(UDim2.new(0, 278, 0, 0), 'InOut', 'Linear', 0.08)
	game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{Rotation = 180}
	):Play()
	game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{ImageColor3 = Color3.fromRGB(51,255,255)}
	):Play()
	
	 else
	DropToggled1 = true
	DropSizeFrame1:TweenSize(UDim2.new(0, 278, 0, 65 + FrameSize1), 'InOut', 'Linear', 0.08)
	Frame1:TweenSize(UDim2.new(0, 278, 0, 65 + FrameSize1), 'InOut', 'Linear', 0.08)
	DropItemScroll1:TweenSize(UDim2.new(0, 278, 0, FrameSize1), 'InOut', 'Linear', 0.08)
	game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{Rotation = 0}
	):Play()
	game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{ImageColor3 = Color3.fromRGB(51,255,255)}
	):Play()
	 end
	end)
	
	for i,v in next, list do
	 ItemCount1 = ItemCount1 + 1
	 if ItemCount1 == 1 then
	FrameSize1 = 30
	 elseif ItemCount1 == 2 then
	FrameSize1 = 60
	 elseif ItemCount1 == 3 then
	FrameSize1 = 90
	 elseif ItemCount1 >= 3 then
	FrameSize1 = 120
	 end
	 
	 local ItemList1 = Instance.new("TextButton")
	 
	 ItemList1.Name = "ItemList"
	 ItemList1.Parent = DropItemScroll1
	 ItemList1.BackgroundColor3 = Color3.fromRGB(51,255,255)
	 ItemList1.BackgroundTransparency = 1.000
	 ItemList1.Size = UDim2.new(0, 278, 0, 30)
	 ItemList1.AutoButtonColor = false
	 ItemList1.Font = Enum.Font.Code
	 ItemList1.TextColor3 = Color3.fromRGB(51,255,255)
	 ItemList1.TextSize = 12.000
	 ItemList1.Text = v or "None..."
	 ItemList1.TextXAlignment = Enum.TextXAlignment.Center
	
	 ItemList1.MouseEnter:Connect(function()
	game.TweenService:Create(ItemList1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{BackgroundTransparency = 0.8}
	):Play()
	 end)
	 ItemList1.MouseLeave:Connect(function()
	game.TweenService:Create(ItemList1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{BackgroundTransparency = 1}
	):Play()
	 end)
	 
	 ItemList1.MouseButton1Click:Connect(function()
	DropTextList1.Text = v or "None..."
	pcall(callback1, v)
	DropToggled1 = false
	DropSizeFrame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	Frame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	DropItemScroll1:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
	game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{Rotation = 180}
	):Play()
	game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{ImageColor3 = Color3.fromRGB(51,255,255)}
	):Play()
	 end)
	 DropItemScroll1.CanvasSize = UDim2.new(0, 0, 0, DropItemLayout1.AbsoluteContentSize.Y)
	end
	
				   function dropfunc1:Clear()
						for _,v  in next, DropItemScroll1:GetChildren() do
							if v:IsA("TextButton") then
								v:Destroy()
							end
						end
						DropTextList1.Text = "Reset Succesfully"
						DropToggled1 = false
						DropSizeFrame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
						Frame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
						DropItemScroll1:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
						game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
							{Rotation = 180}
							):Play()
						game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
							{ImageColor3 = Color3.fromRGB(255,255,255)}
							):Play()
					end
	
	function dropfunc1:Add(newadd)
	 newadd = newadd or {}
	 ItemCount1 = ItemCount1 + 1
	 if ItemCount1 == 1 then
	FrameSize1= 30
	 elseif ItemCount1 == 2 then
	FrameSize1 = 60
	 elseif ItemCount1 == 3 then
	FrameSize1 = 90
	 elseif ItemCount1 >= 3 then
	FrameSize1 = 120
	 end
	 
	 local ItemList1 = Instance.new("TextButton")
	 ItemList1.Name = "ItemList"
	 ItemList1.Parent = DropItemScroll1
	 ItemList1.BackgroundColor3 = Color3.fromRGB(255,255,255)
	 ItemList1.BackgroundTransparency = 1.000
	 ItemList1.Size = UDim2.new(0, 278, 0, 30)
	 ItemList1.AutoButtonColor = false
	 ItemList1.Font = Enum.Font.Code
	 ItemList1.TextColor3 = Color3.fromRGB(51,255,255)
	 ItemList1.TextSize = 12.000
	 ItemList1.Text = newadd or "None..."
	 ItemList1.TextXAlignment = Enum.TextXAlignment.Center
	
	 ItemList1.MouseEnter:Connect(function()
	game.TweenService:Create(ItemList1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{BackgroundTransparency = 0.8}
	):Play()
	 end)
	 ItemList1.MouseLeave:Connect(function()
	game.TweenService:Create(ItemList1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{BackgroundTransparency = 1}
	):Play()
	 end)
	 
	 ItemList1.MouseButton1Click:Connect(function()
	DropTextList1.Text = newadd or "None..."
	pcall(callback1, newadd)
	DropToggled1 = false
	DropSizeFrame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	Frame1:TweenSize(UDim2.new(0, 278, 0, 60), 'InOut', 'Linear', 0.08)
	DropItemScroll1:TweenSize(UDim2.new(0, 278, 0), 'InOut', 'Linear', 0.08)
	game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{Rotation = 180}
	):Play()
	game.TweenService:Create(ImageButton1, TweenInfo.new(0.08, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut),
	{ImageColor3 = Color3.fromRGB(51,255,255)}
	):Play()
	 end)
	 DropItemScroll1.CanvasSize = UDim2.new(0, 0, 0, DropItemLayout1.AbsoluteContentSize.Y)
	end
	return dropfunc1
	end
	
	
	function main:AddSliderLeft(text,min,max,set,callback)
					local Slider = Instance.new("Frame")
					local slidercorner = Instance.new("UICorner")
					local sliderr = Instance.new("Frame")
					local sliderrcorner = Instance.new("UICorner")
					local SliderLabel = Instance.new("TextLabel")
					local HAHA = Instance.new("Frame")
					local AHEHE = Instance.new("TextButton")
					local bar = Instance.new("Frame")
					local bar1 = Instance.new("Frame")
					local bar1corner = Instance.new("UICorner")
					local barcorner = Instance.new("UICorner")
					local circlebar = Instance.new("Frame")
					local UICorner = Instance.new("UICorner")
					local slidervalue = Instance.new("Frame")
					local valuecorner = Instance.new("UICorner")
					local TextBox = Instance.new("TextBox")
					local UICorner_2 = Instance.new("UICorner")
		
					Slider.Name = "Slider"
					Slider.Parent = MainFramePage
					Slider.BackgroundColor3 = _G.Color
					Slider.BackgroundTransparency = 0
					Slider.Size = UDim2.new(0, 280, 0, 51)
		
					slidercorner.CornerRadius = UDim.new(0, 5)
					slidercorner.Name = "slidercorner"
					slidercorner.Parent = Slider
		
					sliderr.Name = "sliderr"
					sliderr.Parent = Slider
					sliderr.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
					sliderr.Position = UDim2.new(0, 1, 0, 1)
					sliderr.Size = UDim2.new(0, 278, 0, 49)
		
					sliderrcorner.CornerRadius = UDim.new(0, 5)
					sliderrcorner.Name = "sliderrcorner"
					sliderrcorner.Parent = sliderr
		
					SliderLabel.Name = "SliderLabel"
					SliderLabel.Parent = sliderr
					SliderLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					SliderLabel.BackgroundTransparency = 1.000
					SliderLabel.Position = UDim2.new(0, 15, 0, 0)
					SliderLabel.Size = UDim2.new(0, 100, 0, 26)
					SliderLabel.Font = Enum.Font.Code
					SliderLabel.Text = text
					SliderLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
					SliderLabel.TextSize = 16.000
					SliderLabel.TextTransparency = 0
					SliderLabel.TextXAlignment = Enum.TextXAlignment.Left
		
					HAHA.Name = "HAHA"
					HAHA.Parent = sliderr
					HAHA.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					HAHA.BackgroundTransparency = 1.000
					HAHA.Size = UDim2.new(0, 468, 0, 29)
		
					AHEHE.Name = "AHEHE"
					AHEHE.Parent = sliderr
					AHEHE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					AHEHE.BackgroundTransparency = 1.000
					AHEHE.Position = UDim2.new(0, 10, 0, 35)
					AHEHE.Size = UDim2.new(0, 260, 0, 5)
					AHEHE.Font = Enum.Font.Code
					AHEHE.Text = ""
					AHEHE.TextColor3 = Color3.fromRGB(0, 0, 0)
					AHEHE.TextSize = 14.000
		
					bar.Name = "bar"
					bar.Parent = AHEHE
					bar.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
					bar.Size = UDim2.new(0, 260, 0, 5)
		
					bar1.Name = "bar1"
					bar1.Parent = bar
					bar1.BackgroundColor3 = _G.Color
					bar1.BackgroundTransparency = 0
					bar1.Size = UDim2.new(set/max, 0, 0, 5)
		
					bar1corner.CornerRadius = UDim.new(0, 5)
					bar1corner.Name = "bar1corner"
					bar1corner.Parent = bar1
		
					barcorner.CornerRadius = UDim.new(0, 5)
					barcorner.Name = "barcorner"
					barcorner.Parent = bar
		
					circlebar.Name = "circlebar"
					circlebar.Parent = bar1
					circlebar.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
					circlebar.Position = UDim2.new(1, -2, 0, -3)
					circlebar.Size = UDim2.new(0, 10, 0, 10)
		
					UICorner.CornerRadius = UDim.new(0, 100)
					UICorner.Parent = circlebar
		
					slidervalue.Name = "slidervalue"
					slidervalue.Parent = sliderr
					slidervalue.BackgroundColor3 = _G.Color
					slidervalue.BackgroundTransparency = 0
					slidervalue.Position = UDim2.new(0, 220, 0, 5)
					slidervalue.Size = UDim2.new(0, 50, 0, 15)
		
					valuecorner.CornerRadius = UDim.new(0, 5)
					valuecorner.Name = "valuecorner"
					valuecorner.Parent = slidervalue
		
					TextBox.Parent = slidervalue
					TextBox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
					TextBox.Position = UDim2.new(0, 1, 0, 1)
					TextBox.Size = UDim2.new(0, 48, 0, 13)
					TextBox.Font = Enum.Font.Code
					TextBox.TextColor3 = Color3.fromRGB(225, 225, 225)
					TextBox.TextSize = 9.000
					TextBox.Text = set
					TextBox.TextTransparency = 0
		
					UICorner_2.CornerRadius = UDim.new(0, 5)
					UICorner_2.Parent = TextBox
		
					local mouse = game.Players.LocalPlayer:GetMouse()
					local uis = game:GetService("UserInputService")
		
					if Value == nil then
						Value = set
						pcall(function()
							callback(Value)
						end)
					end
					
					AHEHE.MouseButton1Down:Connect(function()
						Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min)) or 0
						pcall(function()
							callback(Value)
						end)
						TweenService:Create(
							bar1,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
						TweenService:Create(
							circlebar,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
						moveconnection = mouse.Move:Connect(function()
							TextBox.Text = Value
							Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
							pcall(function()
								callback(Value)
							end)
							TweenService:Create(
								bar1,
								TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
							TweenService:Create(
								circlebar,
								TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
						end)
						releaseconnection = uis.InputEnded:Connect(function(Mouse)
							if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
								Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
								pcall(function()
									callback(Value)
								end)
								TweenService:Create(
									bar1,
									TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
									{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
								):Play()
								--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
								TweenService:Create(
									circlebar,
									TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
									{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
								):Play()
								--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
								moveconnection:Disconnect()
								releaseconnection:Disconnect()
							end
						end)
					end)
					releaseconnection = uis.InputEnded:Connect(function(Mouse)
						if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
							Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
							TextBox.Text = Value
						end
					end)
		
					TextBox.FocusLost:Connect(function()
						if tonumber(TextBox.Text) > max then
							TextBox.Text  = max
						end
						bar1.Size = UDim2.new((TextBox.Text or 0) / max, 0, 0, 5)
						circlebar.Position = UDim2.new(1, -2, 0, -3)
						TextBox.Text = tostring(TextBox.Text and math.floor( (TextBox.Text / max) * (max - min) + min) )
						pcall(callback, TextBox.Text)
					end)
				end
	
	function main:AddSliderRight(text,min,max,set,callback)
					local Slider = Instance.new("Frame")
					local slidercorner = Instance.new("UICorner")
					local sliderr = Instance.new("Frame")
					local sliderrcorner = Instance.new("UICorner")
					local SliderLabel = Instance.new("TextLabel")
					local HAHA = Instance.new("Frame")
					local AHEHE = Instance.new("TextButton")
					local bar = Instance.new("Frame")
					local bar1 = Instance.new("Frame")
					local bar1corner = Instance.new("UICorner")
					local barcorner = Instance.new("UICorner")
					local circlebar = Instance.new("Frame")
					local UICorner = Instance.new("UICorner")
					local slidervalue = Instance.new("Frame")
					local valuecorner = Instance.new("UICorner")
					local TextBox = Instance.new("TextBox")
					local UICorner_2 = Instance.new("UICorner")
		
					Slider.Name = "Slider"
					Slider.Parent = MainFramePage2
					Slider.BackgroundColor3 = _G.Color
					Slider.BackgroundTransparency = 0
					Slider.Size = UDim2.new(0, 280, 0, 51)
		
					slidercorner.CornerRadius = UDim.new(0, 5)
					slidercorner.Name = "slidercorner"
					slidercorner.Parent = Slider
		
					sliderr.Name = "sliderr"
					sliderr.Parent = Slider
					sliderr.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
					sliderr.Position = UDim2.new(0, 1, 0, 1)
					sliderr.Size = UDim2.new(0, 278, 0, 49)
		
					sliderrcorner.CornerRadius = UDim.new(0, 5)
					sliderrcorner.Name = "sliderrcorner"
					sliderrcorner.Parent = sliderr
		
					SliderLabel.Name = "SliderLabel"
					SliderLabel.Parent = sliderr
					SliderLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					SliderLabel.BackgroundTransparency = 1.000
					SliderLabel.Position = UDim2.new(0, 15, 0, 0)
					SliderLabel.Size = UDim2.new(0, 100, 0, 26)
					SliderLabel.Font = Enum.Font.Code
					SliderLabel.Text = text
					SliderLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
					SliderLabel.TextSize = 16.000
					SliderLabel.TextTransparency = 0
					SliderLabel.TextXAlignment = Enum.TextXAlignment.Left
		
					HAHA.Name = "HAHA"
					HAHA.Parent = sliderr
					HAHA.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					HAHA.BackgroundTransparency = 1.000
					HAHA.Size = UDim2.new(0, 468, 0, 29)
		
					AHEHE.Name = "AHEHE"
					AHEHE.Parent = sliderr
					AHEHE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					AHEHE.BackgroundTransparency = 1.000
					AHEHE.Position = UDim2.new(0, 10, 0, 35)
					AHEHE.Size = UDim2.new(0, 260, 0, 5)
					AHEHE.Font = Enum.Font.Code
					AHEHE.Text = ""
					AHEHE.TextColor3 = Color3.fromRGB(0, 0, 0)
					AHEHE.TextSize = 14.000
		
					bar.Name = "bar"
					bar.Parent = AHEHE
					bar.BackgroundColor3 = Color3.fromRGB(45,45,45)
					bar.Size = UDim2.new(0, 260, 0, 5)
		
					bar1.Name = "bar1"
					bar1.Parent = bar
					bar1.BackgroundColor3 = _G.Color
					bar1.BackgroundTransparency = 0
					bar1.Size = UDim2.new(set/max, 0, 0, 5)
		
					bar1corner.CornerRadius = UDim.new(0, 5)
					bar1corner.Name = "bar1corner"
					bar1corner.Parent = bar1
		
					barcorner.CornerRadius = UDim.new(0, 5)
					barcorner.Name = "barcorner"
					barcorner.Parent = bar
		
					circlebar.Name = "circlebar"
					circlebar.Parent = bar1
					circlebar.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
					circlebar.Position = UDim2.new(1, -2, 0, -3)
					circlebar.Size = UDim2.new(0, 10, 0, 10)
		
					UICorner.CornerRadius = UDim.new(0, 100)
					UICorner.Parent = circlebar
		
					slidervalue.Name = "slidervalue"
					slidervalue.Parent = sliderr
					slidervalue.BackgroundColor3 = _G.Color
					slidervalue.BackgroundTransparency = 0
					slidervalue.Position = UDim2.new(0, 220, 0, 5)
					slidervalue.Size = UDim2.new(0, 50, 0, 15)
		
					valuecorner.CornerRadius = UDim.new(0, 5)
					valuecorner.Name = "valuecorner"
					valuecorner.Parent = slidervalue
		
					TextBox.Parent = slidervalue
					TextBox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
					TextBox.Position = UDim2.new(0, 1, 0, 1)
					TextBox.Size = UDim2.new(0, 48, 0, 13)
					TextBox.Font = Enum.Font.Code
					TextBox.TextColor3 = Color3.fromRGB(225, 225, 225)
					TextBox.TextSize = 9.000
					TextBox.Text = set
					TextBox.TextTransparency = 0
		
					UICorner_2.CornerRadius = UDim.new(0, 5)
					UICorner_2.Parent = TextBox
		
					local mouse = game.Players.LocalPlayer:GetMouse()
					local uis = game:GetService("UserInputService")
		
					if Value == nil then
						Value = set
						pcall(function()
							callback(Value)
						end)
					end
					
					AHEHE.MouseButton1Down:Connect(function()
						Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min)) or 0
						pcall(function()
							callback(Value)
						end)
						TweenService:Create(
							bar1,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
						TweenService:Create(
							circlebar,
							TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
						moveconnection = mouse.Move:Connect(function()
							TextBox.Text = Value
							Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
							pcall(function()
								callback(Value)
							end)
							TweenService:Create(
								bar1,
								TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
							TweenService:Create(
								circlebar,
								TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
								{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
							):Play()
							--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
						end)
						releaseconnection = uis.InputEnded:Connect(function(Mouse)
							if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
								Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
								pcall(function()
									callback(Value)
								end)
								TweenService:Create(
									bar1,
									TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
									{Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 260), 0, 5)} -- UDim2.new(0, 128, 0, 25)
								):Play()
								--bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
								TweenService:Create(
									circlebar,
									TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
									{Position =  UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 260), 0, -3)} -- UDim2.new(0, 128, 0, 25)
								):Play()
								--circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
								moveconnection:Disconnect()
								releaseconnection:Disconnect()
							end
						end)
					end)
					releaseconnection = uis.InputEnded:Connect(function(Mouse)
						if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
							Value = math.floor((((tonumber(max) - tonumber(min)) / 260) * bar1.AbsoluteSize.X) + tonumber(min))
							TextBox.Text = Value
						end
					end)
		
					TextBox.FocusLost:Connect(function()
						if tonumber(TextBox.Text) > max then
							TextBox.Text  = max
						end
						bar1.Size = UDim2.new((TextBox.Text or 0) / max, 0, 0, 5)
						circlebar.Position = UDim2.new(1, -2, 0, -3)
						TextBox.Text = tostring(TextBox.Text and math.floor( (TextBox.Text / max) * (max - min) + min) )
						pcall(callback, TextBox.Text)
					end)
				end
	
	
	
			function main:AddTextboxLeft(text,texts,disappear,callback)
				local Textbox = Instance.new("Frame")
				local TextboxCorner = Instance.new("UICorner")
				local Textboxx = Instance.new("Frame")
				local TextboxxCorner = Instance.new("UICorner")
				local TextboxLabel = Instance.new("TextLabel")
				local txtbtn = Instance.new("TextButton")
				local RealTextbox = Instance.new("TextBox")
				local UICorner = Instance.new("UICorner")
	
			 
				Textbox.Name = "Textbox"
				Textbox.Parent = MainFramePage
				Textbox.BackgroundColor3 = _G.Color
				Textbox.BackgroundTransparency = 0
				Textbox.Size = UDim2.new(0, 280, 0, 57)
	
				TextboxCorner.CornerRadius = UDim.new(0, 5)
				TextboxCorner.Name = "TextboxCorner"
				TextboxCorner.Parent = Textbox
	
				Textboxx.Name = "Textboxx"
				Textboxx.Parent = Textbox
				Textboxx.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				Textboxx.Position = UDim2.new(0, 1, 0, 1)
				Textboxx.Size = UDim2.new(0, 278, 0, 55)
	
				TextboxxCorner.CornerRadius = UDim.new(0, 5)
				TextboxxCorner.Name = "TextboxxCorner"
				TextboxxCorner.Parent = Textboxx
	
			
				txtbtn.Name = "txtbtn"
				txtbtn.Parent = Textbox
				txtbtn.BackgroundColor3 = Color3.fromRGB(51,255,255)
				txtbtn.BackgroundTransparency = 1.000
				txtbtn.Position = UDim2.new(0, 1, 0, 1)
				txtbtn.Size = UDim2.new(0, 278, 0, 45)
				txtbtn.Font = Enum.Font.SourceSans
				txtbtn.Text = ""
				txtbtn.TextColor3 = Color3.fromRGB(0, 0, 0)
				txtbtn.TextSize = 14.000
	
	TextboxLabel.Name = "TextboxLabel"
				TextboxLabel.Parent = Textbox
				TextboxLabel.BackgroundColor3 = Color3.fromRGB(51,255,255)
				TextboxLabel.BackgroundTransparency = 1.000
				TextboxLabel.Position = UDim2.new(0, 15, 0, 8)
				TextboxLabel.Text = text
				TextboxLabel.Size = UDim2.new(0, 220, 0, 12)
				TextboxLabel.Font = Enum.Font.Code
				TextboxLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
				TextboxLabel.TextSize = 12.000
				TextboxLabel.TextTransparency = 0
				TextboxLabel.TextXAlignment = Enum.TextXAlignment.Left
	
				Textbox.Name = "Textbox"
				Textbox.Parent = MainFramePage
				Textbox.BackgroundColor3 = _G.Color
				Textbox.BackgroundTransparency = 0
				Textbox.Size = UDim2.new(0, 280, 0, 57)
	
				RealTextbox.Name = "RealTextbox"
				RealTextbox.Parent = Textbox
				RealTextbox.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				RealTextbox.BackgroundTransparency = 0
				RealTextbox.Position = UDim2.new(0, 3, 0, 30)
				RealTextbox.Size = UDim2.new(0, 276, 0, 24)
				RealTextbox.Font = Enum.Font.Code
				RealTextbox.Text = texts
				RealTextbox.TextColor3 = Color3.fromRGB(255, 225, 225)
				RealTextbox.TextSize = 11.000
				RealTextbox.TextTransparency = 0
	
				RealTextbox.FocusLost:Connect(function()
					callback(RealTextbox.Text)
					if disappear then
						RealTextbox.Text = ""
					end
				end)
	
				UICorner.CornerRadius = UDim.new(0, 5)
				UICorner.Parent = RealTextbox
			end
			
			function main:AddTextboxRight(text,texts,disappear,callback)
				local Textboxx = Instance.new("Frame")
				local TextboxCornerr = Instance.new("UICorner")
				local Textboxxx = Instance.new("Frame")
				local TextboxxCornerr = Instance.new("UICorner")
				local TextboxLabell = Instance.new("TextLabel")
				local txtbtnn = Instance.new("TextButton")
				local RealTextboxx = Instance.new("TextBox")
				local UICornerr = Instance.new("UICorner")
	
				Textboxx.Name = "Textbox"
				Textboxx.Parent = MainFramePage2
				Textboxx.BackgroundColor3 = _G.Color
				Textboxx.BackgroundTransparency = 0
				Textboxx.Size = UDim2.new(0, 280, 0, 57)
	
				TextboxCornerr.CornerRadius = UDim.new(0, 5)
				TextboxCornerr.Name = "TextboxCorner"
				TextboxCornerr.Parent = Textboxx
	
				Textboxxx.Name = "Textboxx"
				Textboxxx.Parent = Textboxx
				Textboxxx.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
				Textboxxx.Position = UDim2.new(0, 1, 0, 1)
				Textboxxx.Size = UDim2.new(0, 278, 0, 55)
	
				TextboxxCornerr.CornerRadius = UDim.new(0, 5)
				TextboxxCornerr.Name = "TextboxxCorner"
				TextboxxCornerr.Parent = Textboxxx
	
			
				txtbtnn.Name = "txtbtn"
				txtbtnn.Parent = Textboxx
				txtbtnn.BackgroundColor3 = Color3.fromRGB(51,255,255)
				txtbtnn.BackgroundTransparency = 1.000
				txtbtnn.Position = UDim2.new(0, 1, 0, 1)
				txtbtnn.Size = UDim2.new(0, 278, 0, 45)
				txtbtnn.Font = Enum.Font.SourceSans
				txtbtnn.Text = ""
				txtbtnn.TextColor3 = Color3.fromRGB(0, 0, 0)
				txtbtnn.TextSize = 14.000
	
	TextboxLabell.Name = "TextboxLabel"
				TextboxLabell.Parent = Textboxx
				TextboxLabell.BackgroundColor3 = Color3.fromRGB(51,255,255)
				TextboxLabell.BackgroundTransparency = 1.000
				TextboxLabell.Position = UDim2.new(0, 15, 0, 8)
				TextboxLabell.Text = text
				TextboxLabell.Size = UDim2.new(0, 278, 0, 12)
				TextboxLabell.Font = Enum.Font.Code
				TextboxLabell.TextColor3 = Color3.fromRGB(225, 225, 225)
				TextboxLabell.TextSize = 12.000
				TextboxLabell.TextTransparency = 0
				TextboxLabell.TextXAlignment = Enum.TextXAlignment.Left
	
				RealTextboxx.Name = "RealTextbox"
				RealTextboxx.Parent = Textboxx
				RealTextboxx.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				RealTextboxx.BackgroundTransparency = 0
				RealTextboxx.Position = UDim2.new(0, 3, 0, 30)
				RealTextboxx.Size = UDim2.new(0, 276, 0, 24)
				RealTextboxx.Font = Enum.Font.Code
				RealTextboxx.Text = texts
				RealTextboxx.TextColor3 = Color3.fromRGB(255, 225, 225)
				RealTextboxx.TextSize = 11.000
				RealTextboxx.TextTransparency = 0
	
				RealTextboxx.FocusLost:Connect(function()
					callback(RealTextboxx.Text)
					if disappear then
						RealTextboxx.Text = ""
					end
				end)
	
				UICornerr.CornerRadius = UDim.new(0, 5)
				UICornerr.Parent = RealTextboxx
			end
			
			function main:AddLabelLeft(text)
				local Label = Instance.new("TextLabel")
				local PaddingLabel = Instance.new("UIPadding")
				local labelfunc = {}
		
				Label.Name = "Label"
				Label.Parent = MainFramePage
				Label.BackgroundColor3 = Color3.fromRGB(51,255,255)
				Label.BackgroundTransparency = 1.000
				Label.Size = UDim2.new(0, 360, 0, 20)
				Label.Font = Enum.Font.Code
				Label.TextColor3 = Color3.fromRGB(225, 225, 225)
				Label.TextSize = 14.000
				Label.Text = text
				Label.TextXAlignment = Enum.TextXAlignment.Left
	
				PaddingLabel.PaddingLeft = UDim.new(0,15)
				PaddingLabel.Parent = Label
				PaddingLabel.Name = "PaddingLabel"
		
				function labelfunc:Set(newtext)
				Label.Text = newtext
			end
			return labelfunc
			end
	
			function main:AddLabelRight(text)
				local Labell = Instance.new("TextLabel")
				local PaddingLabell = Instance.new("UIPadding")
				local labelfunc = {}
		
				Labell.Name = "Label"
				Labell.Parent = MainFramePage2
				Labell.BackgroundColor3 = Color3.fromRGB(51,255,255)
				Labell.BackgroundTransparency = 1.000
				Labell.Size = UDim2.new(0, 360, 0, 20)
				Labell.Font = Enum.Font.Code
				Labell.TextColor3 = Color3.fromRGB(225, 225, 225)
				Labell.TextSize = 14.000
				Labell.Text = text
				Labell.TextXAlignment = Enum.TextXAlignment.Left
	
				PaddingLabell.PaddingLeft = UDim.new(0,15)
				PaddingLabell.Parent = Labell
				PaddingLabell.Name = "PaddingLabel"
		
				function labelfunc:Set(newtext)
				Labell.Text = newtext
			end
			return labelfunc
			end
	
	
	function main:Label1(text)
				local Label1 = Instance.new("TextLabel")
				local PaddingLabel1 = Instance.new("UIPadding")
				local Label1func = {}
		
				Label1.Name = "Label1"
				Label1.Parent = MainFramePage
				Label1.BackgroundColor3 = Color3.fromRGB(51,255,255)
				Label1.BackgroundTransparency = 1.000
				Label1.Size = UDim2.new(0, 360, 0, 20)
				Label1.Font = Enum.Font.Code
				Label1.TextColor3 = Color3.fromRGB(225, 225, 225)
				Label1.TextSize = 15.000
				Label1.Text = text
				Label1.TextXAlignment = Enum.TextXAlignment.Left
	
				PaddingLabel1.PaddingLeft = UDim.new(0,15)
				PaddingLabel1.Parent = Label1
				PaddingLabel1.Name = "PaddingLabel1"
	function Label1func:Refresh(tochange)
	 Label1.Text = tochange
	end
	
	return Label1func
	end
	
			function main:AddSeperatorLeft(text)
				local Seperator = Instance.new("Frame")
				local Sep1 = Instance.new("Frame")
				local Sep2 = Instance.new("TextLabel")
				local Sep3 = Instance.new("Frame")
				
				Seperator.Name = "Seperator"
				Seperator.Parent = MainFramePage
				Seperator.BackgroundColor3 = Color3.fromRGB(51,255,255)
				Seperator.BackgroundTransparency = 1.000
				Seperator.Size = UDim2.new(0, 280, 0, 20)
				
				Sep1.Name = "Sep1"
				Sep1.Parent = Seperator
				Sep1.BackgroundColor3 = _G.Color
				Sep1.BorderSizePixel = 0
				Sep1.Position = UDim2.new(0, 0, 0, 10)
				Sep1.Size = UDim2.new(0, 20, 0, 1)
				
				Sep2.Name = "Sep2"
				Sep2.Parent = Seperator
				Sep2.BackgroundColor3 = Color3.fromRGB(51,255,255)
				Sep2.BackgroundTransparency = 1.000
				Sep2.Position = UDim2.new(0, 0.01, 0, 0)
				Sep2.Size = UDim2.new(0, 280, 0, 20)
				Sep2.Font = Enum.Font.Code
				Sep2.Text = text
				Sep2.TextColor3 = Color3.fromRGB(51,255,255)
				Sep2.TextSize = 20.000
				
				Sep3.Name = "Sep3"
				Sep3.Parent = Seperator
				Sep3.BackgroundColor3 = _G.Color
				Sep3.BorderSizePixel = 0
				Sep3.Position = UDim2.new(0, 260, 0, 10)
				Sep3.Size = UDim2.new(0, 20, 0, 1)
			end
	
			function main:AddSeperatorRight(text)
				local Seperator2 = Instance.new("Frame")
				local Sep4 = Instance.new("Frame")
				local Sep5 = Instance.new("TextLabel")
				local Sep6 = Instance.new("Frame")
				
				Seperator2.Name = "Seperator"
				Seperator2.Parent = MainFramePage2
				Seperator2.BackgroundColor3 = Color3.fromRGB(51,255,255)
				Seperator2.BackgroundTransparency = 1.000
				Seperator2.Size = UDim2.new(0, 280, 0, 20)
				
				Sep4.Name = "Sep1"
				Sep4.Parent = Seperator2
				Sep4.BackgroundColor3 = _G.Color
				Sep4.BorderSizePixel = 0
				Sep4.Position = UDim2.new(0, 0, 0, 10)
				Sep4.Size = UDim2.new(0, 20, 0, 1)
				
				Sep5.Name = "Sep2"
				Sep5.Parent = Seperator2
				Sep5.BackgroundColor3 = Color3.fromRGB(51,255,255)
				Sep5.BackgroundTransparency = 1.000
				Sep5.Position = UDim2.new(0, 0.01, 0, 0)
				Sep5.Size = UDim2.new(0, 280, 0, 20)
				Sep5.Font = Enum.Font.Code
				Sep5.Text = text
				Sep5.TextColor3 = Color3.fromRGB(51,255,255)
				Sep5.TextSize = 20.000
				
				Sep6.Name = "Sep3"
				Sep6.Parent = Seperator2
				Sep6.BackgroundColor3 = _G.Color
				Sep6.BorderSizePixel = 0
				Sep6.Position = UDim2.new(0, 260, 0, 10)
				Sep6.Size = UDim2.new(0, 20, 0, 1)
			end
	
	
			function main:AddLineLeft()
				local Linee = Instance.new("Frame")
				local Line = Instance.new("Frame")
				
				Linee.Name = "Linee"
				Linee.Parent = MainFramePage
				Linee.BackgroundColor3 = Color3.fromRGB(255,0,0)
				Linee.BackgroundTransparency = 1.000
				Linee.Position = UDim2.new(0, 0, 0.119999997, 0)
				Linee.Size = UDim2.new(0, 280, 0, 20)
				
				Line.Name = "Line"
				Line.Parent = Linee
				Line.BackgroundColor3 = _G.Color
				Line.BorderSizePixel = 0
				Line.Position = UDim2.new(0, 0, 0, 10)
				Line.Size = UDim2.new(0, 280, 0, 1)
			end
			
			function main:AddLineRight()
				local Lineee = Instance.new("Frame")
				local Line1 = Instance.new("Frame")
				
				Lineee.Name = "Linee"
				Lineee.Parent = MainFramePage2
				Lineee.BackgroundColor3 = Color3.fromRGB(255,0,0)
				Lineee.BackgroundTransparency = 1.000
				Lineee.Position = UDim2.new(0, 0, 0.119999997, 0)
				Lineee.Size = UDim2.new(0, 280, 0, 20)
				
				Line1.Name = "Line"
				Line1.Parent = Lineee
				Line1.BackgroundColor3 = _G.Color
				Line1.BorderSizePixel = 0
				Line1.Position = UDim2.new(0, 0, 0, 10)
				Line1.Size = UDim2.new(0, 280, 0, 1)
			end
			
			return main
		end
		return uitab
	end
	
--------------------------------------------- Function ----------------------------------------------

spawn(function()
    while true do
        pcall(function()
            if Auto_Click or Auto_Ghost_Ship or Auto_Hydra or Auto_Sea_King then         
                game:GetService("ReplicatedStorage").Chest.Remotes.Functions.SkillAction:InvokeServer("SW_"..WeaPon_Select.."_M1")
                game:GetService("ReplicatedStorage").Chest.Remotes.Functions.SkillAction:InvokeServer("FS_"..WeaPon_Select.."_M1")
            end
        end)
        wait(0) -- ปรับค่าเวลาที่รอเป็น 0.1 วินาที (หรือค่าที่ต้องการ)
    end
end)
 

 
function AutoHaki()
	pcall(function()
		local NamePlayer = game.Players.LocalPlayer.Name
		if game:GetService("Workspace").PlayerCharacters.NamePlayer.Services.Haki.Value == 0  then
			game:GetService("ReplicatedStorage").Chest.Remotes.Events.Armament:FireServer()
			wait(6)
		end
	end)
end

function AutoKen()
	pcall(function()
		local NamePlayer = game.Players.LocalPlayer.Name
		if workspace.PlayerCharacters.NamePlayer.Services.KenOpen.Value == 0  then
			game:GetService("ReplicatedStorage").Chest.Remotes.Functions.KenEvent:InvokeServer()
			wait(6)
		end
	end)
end

spawn(function()
    pcall(function()
        while wait() do -- รอเวลาระหว่างแต่ละรอบ
            if Auto_Ghost_Ship or Auto_Hydra or Auto_Sea_King then
                local player = game:GetService("Players").LocalPlayer
                local character = player.Character
                local humanoidRootPart = character and character:FindFirstChild("HumanoidRootPart")
                local humanoid = character and character:FindFirstChild("Humanoid")
                
                if humanoidRootPart and humanoid then
                    -- ใช้ v แทน character
                    local v = character

                    -- ตรวจสอบว่าไม่มี BodyClip อยู่แล้ว
                    local noclip = humanoidRootPart:FindFirstChild("BodyClip")
                    if not noclip then
                        local Noclip = Instance.new("BodyVelocity")
                        Noclip.Name = "BodyClip"
                        Noclip.Parent = humanoidRootPart
                        Noclip.MaxForce = Vector3.new(1000000, 1000000, 1000000)
                        Noclip.Velocity = Vector3.new(0, 0, 0)

                        -- เปลี่ยนสถานะของ Humanoid เป็น Physics
                        v.Humanoid:ChangeState(14) -- ใช้ v.Humanoid ตามที่ต้องการ
                    end
                end
            else
                -- หากปิด Auto_Ghost_Ship, Auto_Hydra หรือ Auto_Sea_King จะทำลาย BodyClip
                local player = game:GetService("Players").LocalPlayer
                local humanoidRootPart = player.Character and player.Character:FindFirstChild("HumanoidRootPart")
                local noclip = humanoidRootPart and humanoidRootPart:FindFirstChild("BodyClip")
                if noclip then
                    noclip:Destroy()
                end
            end
        end
    end)
end)


spawn(function()
	while wait() do
		if Auto_Ghost_Ship or Auto_Hydra or Auto_Sea_King then
			pcall(function()
				if game:GetService("Workspace").PlayerCharacters.NamePlayer.Services.KenOpen.Value == false then
					game:GetService("ReplicatedStorage"):WaitForChild("Chest"):WaitForChild("Remotes"):WaitForChild("Functions"):WaitForChild("KenEvent"):InvokeServer()
				end
			end) 
		end
	end
end)

spawn(function()
	pcall(function()
		game:GetService("RunService").Stepped:Connect(function()
			if Auto_Ghost_Ship or Auto_Hydra or Auto_Sea_King then
				for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
					if v:IsA("BasePart") then
						v.CanCollide = false    
					end
				end
			else
				for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
					if v:IsA("BasePart") then
						v.CanCollide = true    
					end
				end
			end
		end)
	end)
end)



function EquipWeapon(ToolSe)
	if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
		getgenv().tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
		wait()
		game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
	end
end

function Hop()
	local PlaceID = game.PlaceId
	local AllIDs = {}
	local foundAnything = ""
	local actualHour = os.date("!*t").hour
	local Deleted = false
	function TPReturner()
		local Site;
		if foundAnything == "" then
			Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
		else
			Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
		end
		local ID = ""
		if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
			foundAnything = Site.nextPageCursor
		end
		local num = 0;
		for i,v in pairs(Site.data) do
			local Possible = true
			ID = tostring(v.id)
			if tonumber(v.maxPlayers) > tonumber(v.playing) then
				for _,Existing in pairs(AllIDs) do
					if num ~= 0 then
						if ID == tostring(Existing) then
							Possible = false
						end
					else
						if tonumber(actualHour) ~= tonumber(Existing) then
							local delFile = pcall(function()
								AllIDs = {}
								table.insert(AllIDs, actualHour)
							end)
						end
					end
					num = num + 1
				end
				if Possible == true then
					table.insert(AllIDs, ID)
					wait()
					pcall(function()
						wait()
						game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
					end)
					wait(4)
				end
			end
		end
	end
	function Teleport() 
		while wait() do
			pcall(function()
				TPReturner()
				if foundAnything ~= "" then
					TPReturner()
				end
			end)
		end
	end
	Teleport()
end

function UseSkill(skill)
	Tool = game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool")
	local args = {
		[1] = tostring(TypeWeapon) .. "_" .. tostring(WeaPon_Select) .. "_" .. tostring(skill), -- ใส่ค่าตัวแปรเข้าไปใน string โดยตรง
		[2] = {
			["MouseHit"] = CFrame.new(v.HumanoidRootPart.CFrame), -- ไม่จำเป็นต้องใส่ CFrame.new เนื่องจากเรากำหนดค่าให้แล้ว
			["Type"] = "Down"
		}
	}
	
	game:GetService("ReplicatedStorage"):WaitForChild("Chest"):WaitForChild("Remotes"):WaitForChild("Functions"):WaitForChild("SkillAction"):InvokeServer(unpack(args))
		task.wait()
		local args = {
			[1] = tostring(TypeWeapon) .. "_" .. tostring(WeaPon_Select) .. "_" .. tostring(skill), -- ใส่ค่าตัวแปรเข้าไปใน string โดยตรง
			[2] = {
				["MouseHit"] = CFrame.new(v.HumanoidRootPart.CFrame), -- ไม่จำเป็นต้องใส่ CFrame.new เนื่องจากเรากำหนดค่าให้แล้ว
				["Type"] = "Up"
			}
		}
		
		game:GetService("ReplicatedStorage"):WaitForChild("Chest"):WaitForChild("Remotes"):WaitForChild("Functions"):WaitForChild("SkillAction"):InvokeServer(unpack(args))
		end


------------------------------------------------- Ui ----------------------------------------------------------
if game.PlaceId == 6381829480 then
	WorldCheck = 2
	MapPlaceId = "6381829480"
end

local RenUi = Update:AddWindow("RebornXer Hub","10039618734",Enum.KeyCode.RightControl)
local Main = RenUi:AddTab("Farm","6026568198")
    local Player = RenUi:AddTab("Player - TP","7044226690")
    local Misc = RenUi:AddTab("Misc","6034900727")
    local Setting = RenUi:AddTab("","")
    
    local S = RenUi:AddTabH("Top","14134158045")
   
    Main:AddSeperatorRight("Settings")
    
Setting:AddButtonLeft("Copy CFrame",function()
setclipboard(tostring(game.Players.LocalPlayer.Character.HumanoidRootPart.Position))
end)

 Main:AddSeperatorLeft("Info")
    Main:AddLabelLeft("Wecome To RebornXer Hub Script")
    Main:AddLabelLeft("Map : King Legazy")
    Date = os.date("%d".." ".."%B".." ".."%Y")
    Main:AddLabelLeft("Day : "..Date)
    Main:AddSeperatorLeft("Job ID")

	Main:AddTextboxLeft("job id ","...",true,function(s)
		Jobid = s
		end)
		
		Main:AddButtonLeft("Copy Job id",function()
		setclipboard(tostring(game.JobId))
		end)
					
			 Main:AddButtonLeft("Join Job",function(s)
			game:GetService("TeleportService"):TeleportToPlaceInstance(MapPlaceId, Jobid)
			end)
Main:AddToggleLeft("Spam Join Job",Spam_Join_Job,function(a)
	Spam_Join_Job = a
			end)

			spawn(function()
				while wait() do
					pcall(function()
						if Spam_Join_Job then
							game:GetService("TeleportService"):TeleportToPlaceInstance(MapPlaceId, Jobid)
						end
					end)
				end
			end)
				
 Main:AddSeperatorLeft("Main")

Main:AddToggleLeft("Auto Farm",Auto_Farm,function(a)
Auto_Farm = a
end)

function CheckQuest()
	local MyLevel = game.Players.LocalPlayer.PlayerStats.lvl.Value
      if MyLevel == 0 or MyLevel <= 80 then
	MonQuest = "Kill 4 Soldiers"
	PahtNPC = game:GetService("Workspace").AllNPC["Starter Island Quest"].CFrame
	  end
	end


 

	spawn(function()
		while wait() do
			pcall(function()
				if Auto_Farm then
					CheckQuest()
					local questBoard = game.Players.LocalPlayer.PlayerGui.Quest.QuestBoard
					if not questBoard.Visible == false then
						TP(PahtNPC)
						game:GetService("ReplicatedStorage").Chest.Remotes.Functions.Quest:InvokeServer("take", MonQuest)
					else
						local questText = questBoard.QuestCount.Text
						local Ms = string.sub(questText, 5, #questText)
						local monsters = game:GetService("Workspace").Monster
						if monsters.Mon:FindFirstChild(Ms) or monsters.Boss:FindFirstChild(Ms) then
							for _, v in pairs(monsters:GetDescendants()) do
								if v.Name == Ms and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat
										wait()
										AutoHaki()
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * MethodFarm
										EquipWeapon(_G.SelectWeapon)
										v.Humanoid.WalkSpeed = 0
										if _G.AutoSkill then
											UseSkill("Z")
											UseSkill("X")
											UseSkill("C")
											UseSkill("V")
										end
									until not v.Parent or v.Humanoid.Health <= 0 or not _G.AutoFarm or not questBoard.Visible == false
								end
							end
						end
					end
				end
			end)
		end
	end)
	
function TP(Pos)
	local NamePlayer = game.Players.LocalPlayer.Name
     local MainPlayer = game.workspace.PlayerCharacters:FindFirstChild(NamePlayer)
	 MainPlayer.HumanoidRootPart.CFrame = Pos
end

Main:AddSeperatorLeft("World Quest")

Main:AddToggleLeft("Auto Sea Two",Auto_Sea_Two,function(a)
    Auto_Sea_Two = a
end)

spawn(function()
    while wait() do
        pcall(function()
            if Auto_Sea_Two then
                
            end
    end)
end
end)

Main:AddToggleLeft("Auto Sea thi")

Main:AddSeperatorLeft("Sea Event")

Main:AddToggleLeft("Hop Mix",Hop_Mix,function(a)
	Hop_Mix = a
		_G.SaveSettings.Hop_Mix = Hop_Mix
	SaveSetting()
end)

spawn(function()
    while wait() do
        if Hop_Mix and Auto_Hydra and Auto_Sea_King and Auto_Ghost_Ship then
            pcall(function()
                if not game:GetService("Workspace").Island:FindFirstChild("Sea King Thunder") and not game:GetService("Workspace").Island:FindFirstChild("Sea King Lava") and not game:GetService("Workspace").Island:FindFirstChild("Sea King Water") and  not game:GetService("Workspace").Island:FindFirstChild("Legacy Island1") and not game:GetService("Workspace").Island:FindFirstChild("Legacy Island2") and not game:GetService("Workspace").Island:FindFirstChild("Legacy Island3") and not game:GetService("Workspace").Island:FindFirstChild("Legacy Island4") and not game:GetService("Workspace").GhostMonster:FindFirstChild("Ghost Ship") then
                    wait(8)
                    Hop()
                end
            end)
        end
    end
end)


Hydra = Main:AddLabelLeft("")
  

             function HydraSent()
				if game:GetService("Workspace").Island:FindFirstChild("Sea King Thunder") or game:GetService("Workspace").Island:FindFirstChild("Sea King Lava") or game:GetService("Workspace").Island:FindFirstChild("Sea King Water") then
              Hydra:Set("Hydra : ✔")   
                else
                    Hydra:Set("Hydra : ✖")    
                end
                end

         spawn(function()
        while task.wait() do
            pcall(function()
                HydraSent()
            end)
        end
         end)


Main:AddToggleLeft("Auto Hydra",Auto_Hydra,function(a)
    Auto_Hydra = a
	_G.SaveSettings.Auto_Hydra = Auto_Hydra
	SaveSetting()
end)

spawn(function()
    while wait(1) do
        if Auto_Hydra then
            pcall(function()
                -- ตรวจสอบ Hydra ว่าเกิดขึ้นหรือไม่
                local hydra = game:GetService("Workspace").SeaMonster:FindFirstChild("HydraSeaKing")
                if hydra then
                    -- ถ้า Hydra เกิดแล้ว ทำการเทเลพอร์ตไปที่ Hydra
                    repeat
                        wait(0.1) -- เพิ่มการหน่วงเวลาให้เหมาะสม
                        AutoHaki()
						AutoKen()
                        EquipWeapon(WeaPon_Select)
                        TP(hydra.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(90), 0, 0) * CFrame.new(0, 75, 0))
                        if Auto_Skill then
                            UseSkill("Z")
                            UseSkill("X")
                            UseSkill("C")
                            UseSkill("V")
                        end
                    until hydra.Humanoid.Health <= 0 or not Auto_Hydra or not game:GetService("Workspace").SeaMonster:FindFirstChild("HydraSeaKing")
                    
                    -- หาก Hydra ตายแล้ว, เทเลพอร์ตไปที่กล่อง
                    if hydra.Humanoid.Health <= 0 then
                        local lootBox = game:GetService("Workspace").SeaMonster:FindFirstChild("LootBox") -- สมมติว่าชื่อกล่องคือ LootBox
                        if lootBox then
                            TP(lootBox.CFrame)
                        end
                    end
                else
                    -- ถ้า Hydra ไม่เกิด แต่มีเกาะ Hydra, เทเลพอร์ตไปที่เกาะ
                    local seaKingTypes = {"Sea King Thunder", "Sea King Lava", "Sea King Water"}
                    for _, seaKingType in ipairs(seaKingTypes) do
                        local seaKing = game:GetService("Workspace").Island:FindFirstChild(seaKingType)
                        if seaKing then
                            TP(seaKing.HydraStand.CFrame)
                            break
                        end
                    end
                end
            end)
        end
    end
end)


Main:AddToggleLeft("Auto Hydra Hop",Auto_Hydra_Hop,function(a)
    Auto_Hydra_Hop = a
	_G.SaveSettings.Auto_Hydra_Hop = Auto_Hydra_Hop
	SaveSetting()
end)

spawn(function()
    while wait() do
        if Auto_Hydra and Auto_Hydra_Hop then
            pcall(function()
                if not game:GetService("Workspace").Island:FindFirstChild("Sea King Thunder") and not game:GetService("Workspace").Island:FindFirstChild("Sea King Lava") and not game:GetService("Workspace").Island:FindFirstChild("Sea King Water") then
                    wait(3)
                    Hop()
                end
            end)
        end
    end
end)

Seaking = Main:AddLabelLeft("")
  

function SeaKingSent()
if  game:GetService("Workspace").Island:FindFirstChild("Legacy Island1") or game:GetService("Workspace").Island:FindFirstChild("Legacy Island2") or game:GetService("Workspace").Island:FindFirstChild("Legacy Island3") or game:GetService("Workspace").Island:FindFirstChild("Legacy Island4") then
 Seaking:Set("Seaking : ✔")   
   else
       Seaking:Set("Seaking : ✖")    
   end
   end

spawn(function()
while task.wait() do
pcall(function()
    SeaKingSent()
end)
end
end)

Main:AddToggleLeft("Auto Sea King",Auto_Sea_King,function(a)
    Auto_Sea_King = a
	_G.SaveSettings.Auto_Sea_King = Auto_Sea_King
	SaveSetting()
end)

spawn(function()
    while wait(1) do
        if Auto_Sea_King then
            pcall(function()
                -- ตรวจสอบการเกิดของ SeaKing
                local seaMonster = workspace.SeaMonster
                local seaKing = seaMonster and seaMonster:FindFirstChild("SeaKing")
                
                if seaKing and seaKing.Humanoid.Health > 0 then
                    -- ถ้า SeaKing เกิดแล้ว
                    repeat
                        wait(0.1) -- รอระหว่างการดำเนินการ
                        AutoHaki()
						AutoKen()
                        EquipWeapon(WeaPon_Select)
                        TP(seaKing.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(90), 0, 0) - Vector3.new(0, 25, 0))
                        if Auto_Skill then
                            UseSkill("Z")
                            UseSkill("X")
                            UseSkill("C")
                            UseSkill("V")
                        end
                    until seaKing.Humanoid.Health <= 0 or not Auto_Sea_King or not seaMonster:FindFirstChild("SeaKing")

                    -- ถ้า SeaKing ตายแล้ว, ทำการเทเลพอร์ตไปที่กล่อง
                    if seaKing.Humanoid.Health <= 0 then
						local islandNames = {"Legacy Island1", "Legacy Island2", "Legacy Island3", "Legacy Island4"}
						for _, islandName in ipairs(islandNames) do
							local island = game:GetService("Workspace").Island:FindFirstChild(islandName)
							if island then
								TP(island.ChestSpawner.CFrame * CFrame.new(0, 0, 2))
                        end
                    end
                else
                    -- ถ้า SeaKing ยังไม่เกิด, ให้ไปที่เกาะ
                    local islandNames = {"Legacy Island1", "Legacy Island2", "Legacy Island3", "Legacy Island4"}
                    for _, islandName in ipairs(islandNames) do
                        local island = game:GetService("Workspace").Island:FindFirstChild(islandName)
                        if island then
                            TP(island.ChestSpawner.CFrame * CFrame.new(0, 0, 2))
                            break
                        end
                    end
                end
            end)
        end
    end
end)


Main:AddToggleLeft("Auto Sea King Hop",Auto_Sea_King_Hop,function(a)
    Auto_Sea_King_Hop = a
	_G.SaveSettings.Auto_Sea_King_Hop = Auto_Sea_King_Hop
	SaveSetting()
end)

 
spawn(function()
    while wait() do
        if Auto_Sea_King and Auto_Sea_King_Hop then
            pcall(function()
                if not game:GetService("Workspace").Island:FindFirstChild("Legacy Island1") or not game:GetService("Workspace").Island:FindFirstChild("Legacy Island2") or not game:GetService("Workspace").Island:FindFirstChild("Legacy Island3") or not game:GetService("Workspace").Island:FindFirstChild("Legacy Island4") then
                    wait(3)
                    Hop()
                end
            end)
        end
    end
end)

GhostShip = Main:AddLabelLeft("")
  

             function GhostShipSent()
    		if game:GetService("Workspace").GhostMonster:FindFirstChild("Ghost Ship") then
              GhostShip:Set("Ghost Ship : ✔")   
                else
                    GhostShip:Set("Ghost Ship : ✖")    
                end
                end

         spawn(function()
        while task.wait() do
            pcall(function()
                GhostShipSent()
            end)
        end
         end)

Main:AddToggleLeft("Auto Ghost Ship",Auto_Ghost_Ship,function(a)
    Auto_Ghost_Ship = a
	_G.SaveSettings.Hop_Mix = Hop_Mix
	SaveSetting()
end)
spawn(function()
    while wait() do
        pcall(function()
            if Auto_Ghost_Ship then
                local ghostShip = game:GetService("Workspace").GhostMonster:FindFirstChild("Ghost Ship")
                if ghostShip then
                    for i,v in pairs(game:GetService("Workspace").GhostMonster:GetChildren()) do
                        if v == ghostShip and v.Humanoid.Health > 0 then
                            repeat
                                wait()
                                AutoHaki()
                                EquipWeapon(WeaPon_Select)
                                TP(v.HumanoidRootPart.CFrame * CFrame.new(0,10,0))
                                if Auto_Skill then 
                                    UseSkill("Z")
                                    UseSkill("X")
                                    UseSkill("C")
                                    UseSkill("V")
                                end
                            until v.Humanoid.Health <= 0 or not Auto_Ghost_Ship or not game:GetService("Workspace").GhostMonster:FindFirstChild("Ghost Ship") or game:GetService("Workspace"):FindFirstChild("Chest1")
                        end
                    end
                elseif game:GetService("Workspace"):FindFirstChild("Chest1") then
                    for _, chest in pairs(game.Workspace:GetChildren()) do 
                        if chest.Name:find("Chest") then 
                            TP(chest.PrimaryPart.CFrame)
                            wait(0.3)
                        end
                    end
                end
            end
        end)
    end
end)

Main:AddToggleLeft("Auto Ghost Ship Hop",Auto_Ghost_Ship_Hop,function(a)
    Auto_Ghost_Ship_Hop = a
	_G.SaveSettings.Hop_Mix = Hop_Mix
	SaveSetting()
end)

 

    spawn(function()
        while wait() do
            if Auto_Ghost_Ship and Auto_Ghost_Ship_Hop then
                pcall(function()
                    if not game:GetService("Workspace").GhostMonster:FindFirstChild("Ghost Ship") then
                        wait(3)
                        Hop()
                    end
                end)
            end
        end
    end)

------------------------------------------------------------------ Right ------------------------------------------------------------------

Main:AddDropdownRight("Select Weapon", {"Melee","Sword","Fruit"},_G.SaveSettings.elect_Weapon, function(value)
    Select_Weapon = value
	_G.SaveSettings.elect_Weapon = Select_Weapon
	SaveSetting()
end)


spawn(function()
	while true do
		pcall(function()
		local playerStats = game:GetService("Players").LocalPlayer.PlayerStats
		if Select_Weapon == "Melee" then
			WeaPon_Select = playerStats.FightingStyle.Value
			TypeWeapon = "FS"
		elseif Select_Weapon == "Sword" then
			WeaPon_Select = playerStats.SwordName.Value
			TypeWeapon = "SW"
		elseif Select_Weapon == "Fruit" then
			WeaPon_Select = playerStats.DFName.Value 
			TypeWeapon = "DF"
		end
		wait() -- หยุดสักครู่ก่อนที่จะวน loop ต่อ
	end)
end
end)

Main:AddDropdownRight("Select Method",{"Behind","Below","Upper"},_G.SaveSettings.Select_Method,function(value)
    Select_Method = value
	_G.SaveSettings.Select_Method = Select_Method
	SaveSetting()
end)

spawn(function()
	while wait(1) do 
		pcall(function()
			if Select_Method == "Behind" then
				MethodFarm = CFrame.new(0,0,DistanceMob)
			elseif Select_Method == "Below" then
				MethodFarm = CFrame.new(0,-DistanceMob,0) * CFrame.Angles(math.rad(90),0,0)
			elseif Select_Method == "Upper" then
				MethodFarm = CFrame.new(0,DistanceMob,0)  * CFrame.Angles(math.rad(-90),0,0)
			else
				MethodFarm = CFrame.new(0,DistanceMob,0)  * CFrame.Angles(math.rad(-90),0,0)
			end
		end)
	end
end)

Main:AddSliderRight("Distance",1,100,_G.SaveSettings.DistanceMob,function(value)
	DistanceMob = value
	_G.SaveSettings.DistanceMob = DistanceMob
	SaveSetting()
end)

Main:AddToggleRight("Auto Skill",Auto_Skill,function(a)
	Auto_Skill = a
end)

local player = game:GetService("Players").LocalPlayer

local blackscreen = function(enable)
    local playerGui = player:WaitForChild("PlayerGui")
    if not enable then
        local sUi = playerGui:FindFirstChild("Blackscreen")
        if sUi then sUi:Destroy() end
        return
    elseif playerGui:FindFirstChild("Blackscreen") then
        return
    end
    local sUi = Instance.new("ScreenGui", playerGui)
    sUi.Name = "Blackscreen"
    sUi.DisplayOrder = -727

    local uiFrame = Instance.new("Frame", sUi)
    uiFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    uiFrame.Size = UDim2.new(0, 72727, 0, 72727)
    uiFrame.Position = UDim2.new(0, 0, -5, 0)
end


Main:AddToggleRight("Black Screen",Black_Screen,function(a)
	Black_Screen = a
	if Black_Screen == true then
		game:GetService("RunService"):Set3dRenderingEnabled(false)
		wait()
		blackscreen(true)
	elseif Black_Screen == false then
		game:GetService("RunService"):Set3dRenderingEnabled(true)
		blackscreen(false)
	end
end)


Main:AddSeperatorRight("Auto Stats")
    
Main:AddToggleRight("Auto Defense",Auto_Defense,function(value)
	Auto_Defense = value
end)

spawn(function()
	while wait() do
		if Auto_Defense then
			if game:GetService("Players")["LocalPlayer"].PlayerStats.Points.Value ~= 0 then
				pcall(function()
					game:GetService("Players").LocalPlayer.PlayerGui.Stats.Button.StatsFrame.RemoteEvent:FireServer("Defense",PointStats)
				end)
			end
		end
	end
end)

Main:AddToggleRight("Auto Melee",Auto_Melee,function(value)
	Auto_Melee = value
end)

spawn(function()
	while wait() do
		if Auto_Melee then
			if game:GetService("Players")["LocalPlayer"].PlayerStats.Points.Value ~= 0 then
				pcall(function()
					game:GetService("Players").LocalPlayer.PlayerGui.Stats.Button.StatsFrame.RemoteEvent:FireServer("Melee",PointStats)
				end)
			end
		end
	end
end)

Main:AddToggleRight("Auto Sword",Auto_Sword,function(value)
	Auto_Sword = value
end)

spawn(function()
	while wait() do
		if Auto_Sword then
			if game:GetService("Players")["LocalPlayer"].PlayerStats.Points.Value ~= 0 then
				pcall(function()
					game:GetService("Players").LocalPlayer.PlayerGui.Stats.Button.StatsFrame.RemoteEvent:FireServer("Sword",PointStats)
				end)
			end
		end
	end
end)

Main:AddToggleRight("Auto Devil Fruit",Auto_Devil_Fruit,function(value)
	Auto_Devil_Fruit = value
end)

spawn(function()
	while wait() do
		if Auto_Devil_Fruit then
			if game:GetService("Players")["LocalPlayer"].PlayerStats.Points.Value ~= 0 then
				pcall(function()
					game:GetService("Players").LocalPlayer.PlayerGui.Stats.Button.StatsFrame.RemoteEvent:FireServer("Devil Fruit",PointStats)
				end)
			end
		end
	end
end)


Misc:AddToggleLeft("Walk on Water",_G.Walk_On_Water,function(a)
_G.Walk_On_Water = a
if _G.Walk_On_Water then
 game:GetService("Workspace").watermove.Sea.CanCollide = true
else
 game:GetService("Workspace").watermove.Sea.CanCollide = false
end
end)

Misc:AddToggleLeft("Auto Click",Auto_Click,function(a)
	Auto_Click = a
end)

Player:AddSeperatorLeft("Players")
PlayerList = {}
    
for i,v in pairs(workspace.PlayerCharacters:GetChildren()) do  
		table.insert(PlayerList ,v.Name)
end

Player_Select = Player:AddDropdownLeft("Select Player",PlayerList,Select_Player,function(value)
	Select_Player = value
end)

Player:AddButtonLeft("Reset Player",function()
	Player_Select:Clear()
	for i,v in pairs(workspace.PlayerCharacters:GetChildren()) do  
		Player_Select:Add(v.Name)
	end
end)

Player:AddButtonLeft("Teleport Player",function()
	TP(workspace.PlayerCharacters:FindFirstChild(Select_Player).HumanoidRootPart.CFrame)
end)

Misc:AddButtonRight("Rejoin Server",function()
	game:GetService("TeleportService"):Teleport(game.PlaceId, game.Jobid)
end)

Misc:AddButtonRight("Server Hop",function()
	Hop()
end)

Misc:AddButtonRight("Hop To Lower Player",function()
	getgenv().AutoTeleport = true
	getgenv().DontTeleportTheSameNumber = true 
	getgenv().CopytoClipboard = false
	if not game:IsLoaded() then
		print("Game is loading waiting...")
	end
	local maxplayers = math.huge
	local serversmaxplayer;
	local goodserver;
	local gamelink = "https://games.roblox.com/v1/games/" .. game.PlaceId .. "/servers/Public?sortOrder=Asc&limit=100" 
	function serversearch()
		for _, v in pairs(game:GetService("HttpService"):JSONDecode(game:HttpGetAsync(gamelink)).data) do
			if type(v) == "table" and v.playing ~= nil and maxplayers > v.playing then
				serversmaxplayer = v.maxPlayers
				maxplayers = v.playing
				goodserver = v.id
			end
		end       
	end
	function getservers()
		serversearch()
		for i,v in pairs(game:GetService("HttpService"):JSONDecode(game:HttpGetAsync(gamelink))) do
			if i == "nextPageCursor" then
				if gamelink:find("&cursor=") then
					local a = gamelink:find("&cursor=")
					local b = gamelink:sub(a)
					gamelink = gamelink:gsub(b, "")
				end
				gamelink = gamelink .. "&cursor=" ..v
				getservers()
			end
		end
	end 
	getservers()
	if AutoTeleport then
		if DontTeleportTheSameNumber then 
			if #game:GetService("Players"):GetPlayers() - 4  == maxplayers then
				return warn("It has same number of players (except you)")
			elseif goodserver == game.JobId then
				return warn("Your current server is the most empty server atm") 
			end
		end
		game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, goodserver)
	end
end)
