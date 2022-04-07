# Lumio Personal Pets
## Info
This is a custom script that allows you to buy, own and care animals / pets! It's fully configurable and easy to use. It is used on a server for a month as a testing phase and so far no complaints.

You can manage your pet by doing the configured slash command and there you will get a lot of options of what you can do. You'll not be able to open the menu if you have no pets! The script also has a build-in pet store where you can buy pets, food and extras.

## Features
- QBCore supported
- Custom QBCore rename supported in config
- Fully configurable
- Default english, dutch supported, you can easily add others
- Completely custom and optimised

## How to install
### **Choose core**
- Go to `config.lua` and search for this:
```
Config.Core = {
    core = 'QBCore', --change to your core
    name = 'qb-core' --change to your core name
}
```

### **Choose menu, input and other core stuff**
- Go to `config.lua` and search for this:
```
Config.MenuExports = 'qb-menu'
Config.InputExports = 'qb-input'

Config.Notify = 'QBCore:Notify' --change QBCore to your core if needed
Config.CoreAddItem = 'QBCore:Server:AddItem' --change QBCore to your core if needed
Config.CoreRemoveItem = 'QBCore:Server:RemoveItem' --change QBCore to your core if needed
Config.CoreLoaded = 'QBCore:Client:OnPlayerLoaded' --change QBCore to your core if needed
```

### **Language select**
Go to the `fxmanifest.lua` and look for `shared_scripts`. Once you found that there will be something like this:
```
shared_scripts {
    'config.lua',
    'translations/en.lua'
}
```
The `en.lua` stands for the English translation file found in translations/en.lua. If you prefer another language like French for example just add a file named `fr.lua` and copy paste the contents of `en.lua`, then you can change the translations to french (not the ones between `[' ']`). Don't forget to change the `en.lua` in `fxmanifest.lua` to `fr.lua` then!

### **Configuration**
- Go the `config.lua` file
- Configure pet store:
- ([Here](https://docs.fivem.net/docs/game-references/blips/) you can find blips / colors)
```
Config.Store = {
    storelocation = vector3(562.27, 2751.56, 42.88), --Location where you can buy pets
    blipcoords = vector3(562.37, 2751.36, 42.88), -- Location on the map for the blip
    blipsprite = 273, --Blip icon
    blipcolor = 24,
    blipscale = 0.6,
    bliplabel = "Pet store",
    blipshortrange = true, --If false then it will be visible on minimap when not near it (should stay on true)
}
```
- Configure time of eating:
```
Config.EatTime = 10 -- Time in seconds for how long eating takes
```
- Configure time which stats should update:
```
Config.FoodTimer = 30 --Time in minutes update stats (health, food)
```
- Default pet name when buying one:
```
Config.DefaultPetName = 'My pet'
```
- Changing pets in store
- You can add pets to Config.BuyPetMenu like this:
```
Config.BuyPetMenu = {
    [index number] = { 
        header = 'Header on menu',
        txt = 'Sub text',
        spawnname = 'Pet spawn name', --https://wiki.altv.mp/wiki/GTA:Ped_Models
        price = 500,
        type = 'dog', --dog, cat or chicken
    },
```

### **Items**
- Add the following to your items list in your core:
```
['dogfood'] = {
    ['name'] = 'dogfood',
    ['label'] = 'Dogfood',
    ['weight'] = 1000,
    ['type'] = 'item',
    ['image'] = 'dogfood.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'Food for your dog'
},

['catfood'] = {
    ['name'] = 'catfood',
    ['label'] = 'Catfood',
    ['weight'] = 1000,
    ['type'] = 'item',
    ['image'] = 'catfood.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'Food for your cat'
},
```
- Add these items to your `qb-inventory > html > images`, images found in images folder

![dogfood](https://cdn.discordapp.com/attachments/928287293742149716/961757865608114187/dogfood.png)
![catfood](https://cdn.discordapp.com/attachments/928287293742149716/961757865410973707/catfood.png)

### **Database**
- Insert the pets.sql file in your database
- ⚠️ DO NOT CHANGE ANYTHING IN SQL FILE OR IT WON'T WORK ⚠️

## Dependencies not include
- [Petstore MLO](https://nl.gta5-mods.com/maps/mlo-pet-shop)

## Support
For issues join our [Discord](https://discord.gg/eS6KGq8bRb), and we will help you asap!
