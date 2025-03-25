--Punch

--Id
if game.PlaceId == 14236123211 then

    -- Função para copiar o link da key ao iniciar
    local function CopyKeyLink()
        if setclipboard then
            setclipboard("https://fir3.net/UF854v")
            print("Link da key copiado automaticamente!")
        end
    end

    -- Chama a função de cópia logo no início
    CopyKeyLink()

    --Rayfield Library
    local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

    --Window
    local Window = Rayfield:CreateWindow({
        Name = "Slender Hub",
        Icon = 0,
        LoadingTitle = "Slender Hub",
        LoadingSubtitle = "by Slender",
        Theme = "Default",
     
        DisableRayfieldPrompts = false,
        DisableBuildWarnings = false,
     
        ConfigurationSaving = {
           Enabled = true,
           FolderName = nil,
           FileName = "Big Hub"
        },
     
        Discord = {
           Enabled = true,
           Invite = "zFQMEvT6",
           RememberJoins = true
        },
     
        KeySystem = true,
        KeySettings = {
           Title = "Slender Hub",
           Subtitle = "Sistema de Chave",
           Note = "The link to get the key was copied automatically", 
           FileName = "SlenderHubKey", 
           SaveKey = true,
           GrabKeyFromSite = true,
           Key = {"https://pastebin.com/raw/azs17Tmb"} -- Link direto para o Pastebin
        }
     })
    

     --Variaveis
     _G.Autoclick = true
     _G.autoHatch = true
     _G.selectEgg = "1"
     _G.autoCraft = true
     _G.selectCraft = "ShortSwords"
     _G.autoWishingWell = true
     _G.selectWishingWell = "Small"
     _G.autoWin = true
     _G.autoSpin = true
    


     --Funcoes 
     function Autoclick()
        while _G.Autoclick == true do  
           local Event = game:GetService("ReplicatedStorage").Events.DamageIncreaseOnClickEvent
           Event:FireServer()
           wait(0)
        end
     end
        
    function autoHatch()
        while _G.autoHatch == true do 
           game:GetService("ReplicatedStorage").Events.PlayerPressedKeyOnEgg:FireServer(_G.selectEgg,1)
           wait(0)
        end
     end
  
     function autoCraft()
        while _G.autoCraft == true do
           game:GetService("ReplicatedStorage").Events.CraftingEvent:FireServer(_G.selectCraft)
           wait(0,1)
        end
     end
  
     function autoWishingWell()
        while _G.autoWishingWell == true do
           game:GetService("ReplicatedStorage").Events.WishingWell:FireServer(_G.selectWishingWell)
           wait(1)
        end
     end      
 
     function autoWin()
       while _G.autoWin == true do
          game:GetService("ReplicatedStorage").Events.PushEvent:FireServer(true)
          wait(0.1)
       end
    end
 
    function autoSpin()
       while _G.autoSpin == true do
          game:GetService("ReplicatedStorage").Events.SpinWheelEvent:FireServer(_G.autoSpin)
          wait(0.1)
       end
    end
    


     --Tabs
     local AutoTab = Window:CreateTab("Auto", 4483362458) -- Title, Image

     local EggTab = Window:CreateTab("Eggs", 4483362458) -- Title, Image

     local MiscTab = Window:CreateTab("Misc", 4483362458) -- Title, Image

     --Toogles
     local Toggle = AutoTab:CreateToggle({
        Name = "Auto Damage",
        CurrentValue = false,
        Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
        Callback = function(Value)
            _G.Autoclick = Value  
            Autoclick()
        end,
     })

     local Toggle = AutoTab:CreateToggle({
        Name = "Auto Win",
        CurrentValue = false,
        Flag = "Toggle2", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
        Callback = function(Value)
            _G.autoWin = Value
            autoWin()
        end,
     })

     local Toggle = AutoTab:CreateToggle({
        Name = "Auto Craft",
        CurrentValue = false,
        Flag = "Toggle3", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
        Callback = function(Value)
            _G.autoCraft = Value
            autoCraft()
        end,
     })

     local Toggle = EggTab:CreateToggle({
        Name = "Auto Hatch",
        CurrentValue = false,
        Flag = "Toggle4", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
        Callback = function(Value)
            _G.autoHatch = Value
            autoHatch()
        end,
     })

     local Toggle = MiscTab:CreateToggle({
        Name = "Auto Spin",
        CurrentValue = false,
        Flag = "Toggle5", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
        Callback = function(Value)
            _G.autoSpin = Value
            autoSpin()
        end,
     })

     local Toggle = MiscTab:CreateToggle({
        Name = "Auto WishingWell",
        CurrentValue = false,
        Flag = "Toggle6", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
        Callback = function(Value)
            _G.autoWishingWell = Value
          autoWishingWell()
        end,
     })
     --Dropdown
     local Dropdown = AutoTab:CreateDropdown({
        Name = "Select Craft",
        Options = {"ShortSwords", "Clover", "HealthKit", "BootsofSwiftness", "LuckyDie", "Magnet", "Dagger", "LuckyTooth", "JetFuel", "LuckyGem", "Heart", "HeavyHammer", "HorseShoe", "HandfulOfCoins", "HealthGem", "DualHammers", "GoldenClover", "GemStack", "GoldenHealthGem", "RocketJet", "QuadHammers"},
        CurrentOption = {"ShortSwords"},
        MultipleOptions = false,
        Flag = "Dropdown1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
        Callback = function(Options)
            _G.selectCraft = Value
            print(_G.selectCraft)
        end,
     })

     local Dropdown = EggTab:CreateDropdown({
        Name = "Select Egg",
        Options = {"1", "2", "3", "4", "5", "6", "7", "8", "9", "10", "11", "12", "13", "14", "15", "16", "17", "18", "19", "20", "21", "22", "23", "24", "25", "26", "27"},
        CurrentOption = {"1"},
        MultipleOptions = false,
        Flag = "Dropdown2", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
        Callback = function(Options)
            _G.selectEgg = Value
          print(_G.selectEgg)
        end,
     })

     local Dropdown = MiscTab:CreateDropdown({
        Name = "Select Wishing Well",
        Options ={"Small", "Medium", "Mega"},
        CurrentOption = {"Small"},
        MultipleOptions = false,
        Flag = "Dropdown3", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
        Callback = function(Options)
            _G.selectWishingWell = Value
          print(_G.selectWishingWell)
        end,
     })
     
    end
