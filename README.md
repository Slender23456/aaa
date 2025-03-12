--Punch
--Key
local KeySystem = loadstring(game:HttpGet("https://raw.githubusercontent.com/OopssSorry/LuaU-Free-Key-System-UI/main/source.lua"))()
local KeyValid = false
local response = KeySystem:Init({
    Debug=false,
    Title="Slender Hub | Key System",
    Description=nil,
    Link="https://fir3.net/UF854v",
    Discord="https://discord.gg/UFdqC6Nz", -- Link do Discord adicionado
    SaveKey=false,
    Verify=function(key)
        if key=="A9X3B7Z5Q2L8M4C6" then
            KeyValid=true
            return true
        else
            return false
        end
    end,
    GuiParent = game.CoreGui,
})

if not response or not KeyValid then return end
--Id
if game.PlaceId == 14236123211 then

    --Load
    local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/jensonhirst/Orion/main/source')))()
    
    --Main
    local Window = OrionLib:MakeWindow({Name = "Slender HUB", HidePremium = false, SaveConfig = true, ConfigFolder = "Slender", IntroEnabled = false})
    
    --Valor
    _G.Autoclick = true
    _G.autoHatch = true
    _G.selectEgg = "1"
    _G.autoCraft = true
    _G.selectCraft = "ShortSwords"
    _G.autoWishingWell = true
    _G.selectWishingWell = "Small"
    _G.autoWin = true
    _G.autoSpin = true
    _G.autoPower1 = true
    _G.autoHack = true
    _G.autoPower2 = true

    
    --Função
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
   
function autoPower1()
   while _G.autoPower1 == true do
      game:GetService("ReplicatedStorage").Events.PowerCore:InvokeServer(_G.autoPower1)
      wait(0.1)
   end
end

function autoHack()
   while _G.autoHack == true do
      game:GetService("ReplicatedStorage").Events.HackEvent:InvokeServer(_G.autoHack)
      wait(1)
   end
end
function autoPower2()
   while _G.autoPower2 == true do
      game:GetService("ReplicatedStorage").Events.PowerCoreV2:InvokeServer(_G.autoPower2)
      wait(5)
   end
end


   
 
    --Local
    local AutoTab = Window:MakeTab({
       Name = "Auto",
       Icon = "rbxassetid://4483345998",
       PremiumOnly = false
    })
    local Section = AutoTab:AddSection({
       Name = "AutoFarm"
    })
 
    local EggTab = Window:MakeTab({
       Name = "Eggs",
       Icon = "rbxassetid://4483345998",
       PremiumOnly = false
    })
 
    local MiscTab = Window:MakeTab({
       Name = "Misc",
       Icon = "rbxassetid://4483345998",
       PremiumOnly = false
    })
    
    
    
    --Toggle
    AutoTab:AddToggle({
       Name = "AutoDamage",
       Default = false,
       Callback = function(Value)
          _G.Autoclick = Value
          Autoclick()
       end    
    })

    AutoTab:AddToggle({
      Name = "AutoWin",
      Default = false,
      Callback = function(Value)
         _G.autoWin = Value
         autoWin()
      end    
   })
 
    AutoTab:AddToggle({
       Name = "AutoCraft",
       Default = false,
       Callback = function(Value)
          _G.autoCraft = Value
          autoCraft()
       end    
    })
 
    EggTab:AddToggle({
       Name = "AutoHatch",
       Default = false,
       Callback = function(Value)
          _G.autoHatch = Value
          autoHatch()
       end    
    })
    
    MiscTab:AddToggle({
      Name = "AutoSpin",
      Default = false,
      Callback = function(Value)
         _G.autoSpin = Value
         autoSpin()
      end    
   })

     MiscTab:AddToggle({
      Name = "AutoHack",
      Default = false,
      Callback = function(Value)
         _G.autoHack = Value
         autoHack()
      end    
   })

   MiscTab:AddToggle({
      Name = "Auto PowerCore 1",
      Default = false,
      Callback = function(Value)
         _G.autoPower1 = Value
         autoPower1()
      end    
   })

   MiscTab:AddToggle({
      Name = "Auto PowerCore 2",
      Default = false,
      Callback = function(Value)
         _G.autoPower2 = Value
         autoPower2()
      end    
   })

    MiscTab:AddToggle({
       Name = "AutoWishingWell",
       Default = false,
       Callback = function(Value)
          _G.autoWishingWell = Value
          autoWishingWell()
       end    
    })
   
  
    --Dropdown 
    AutoTab:AddDropdown({
       Name = "Select Craft",
       Default = "ShortSwords",
       Options = {"ShortSwords", "Clover", "HealthKit", "BootsofSwiftness", "LuckyDie", "Magnet", "Dagger", "LuckyTooth", "JetFuel", "LuckyGem", "Heart", "HeavyHammer", "HorseShoe", "HandfulOfCoins", "HealthGem", "DualHammers", "GoldenClover", "GemStack", "GoldenHealthGem", "RocketJet", "QuadHammers"},
       Callback = function(Value)
          _G.selectCraft = Value
          print(_G.selectCraft)
       end    
    })
    
    
    
    EggTab:AddDropdown({
       Name = "Select Egg",
       Default = "1",
       Options = {"1", "2", "3", "4", "5", "6", "7", "8", "9", "10", "11", "12", "13", "14", "15", "16", "17", "18", "19", "20", "21", "22", "23", "24", "25", "26", "27"},
       Callback = function(Value)
          _G.selectEgg = Value
          print(_G.selectEgg)
       end    
    })
    
 
    MiscTab:AddDropdown({
       Name = "Select Wishing Well",
       Default = "Small",
       Options = {"Small", "Medium", "Mega"},
       Callback = function(Value)
          _G.selectWishingWell = Value
          print(_G.selectWishingWell)
       end    
    })
    
  
 
    
    end
