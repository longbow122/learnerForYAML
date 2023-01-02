---
hide:
  - footer
title: "Minecraft-specific YAML Examples"
---

*This page is currently a stub. I would like to add more to this page, but I'm not sure what else to add! If you have any ideas, please [contact me.](https://github.com/longbow122/learnerForYAML/wiki#suggestions-and-improvements)*

# Minecraft-specific Examples
So, after all that reading, it's time you finally saw how this can be applied to your server.

## Example One
Most servers owners don't like large configuration files, as they'll normally be the ones that take the longest to configure and thus, mean more work. It's actually quite the opposite. The more configuration options you have, the more control over the plugin you get! Take a look at [ChatManager's configuration file.](https://github.com/H1DD3NxN1NJA/ChatManager/blob/master/Files/config.yml) I'll be referencing examples from this to show how large configuration files with good YAML practice can help.

Take a look at the first section of the configuration file:
```yaml
Chat:

  #Block advertising in chat.
  Enable: true

  #Should the anti advertising checker be more sensitive? This may cause false positives.
  Increase_Sensitivity: false

  #Should staff get notified when a player advertises in chat?
  Notify_Staff: true

  #Should a command be executed to the player that advertises?
  Execute_Command: false

  #The command that is executed when a player advertises.
  #Set this section to Executed_Command: '' to disable
  Executed_Command: 'kick {player} Please do not advertise in chat'

  #Every time a player advertises in chat, their message will be logged in the Advertisements.txt file.
  Log_Advertisers: true
```
The developer of this plugin has followed excellent YAML practice when writing this configuration file and has even made it nice and easy to read! Let's break this file down, to see what he's doing to help you:

- Clear, concise section and key naming. This will help you a ton due to the fact that with this simple key and section naming, you may not even need the comments to know what each option does.
- Short, informative comments. These explain what each key does in easy to read sentences. Very useful, makes choices of what to change much easier.
- Whitespacing/newlines. These simply keep everything separated. While it does mean more scrolling, it can also mean certain keys are easier to find, and comments and keys are much easier to read. Makes configuration much easier in the long run.

When it comes to configuration files, this is a prime example of one that is easy to edit, and to read. Perfect for server owners and admins!

## Example Two
As said before, when it comes to most server owners/admins, long configuration files are the bane of their existence. Some people even quit purely because it's long and confusing. Fortunately, for SOME plugins, this is not the case. Most GUI, Command, Crate, Shop and Quest plugins will be very customisable, and as such, will have a very structured way of configuring their plugins to allow maximum customisation. Take [Crazy Crates](https://www.spigotmc.org/resources/crazy-crates.17599/) for example. When customising a crate through this plugin, you should notice that they have many options you can use. Note that word specifically, **options, meaning, optional**. You don't have to use ALL of them! A plugin with a similar configuration structure like CrazyCrates, will also be similar in the sense that these sections and keys can simply be removed for peace of mind. This, in turn, will make your config file so much smaller and easier to read, since there are fewer comments and sections to read and flick through. Take a look at the example below:

```yaml
1:
  #Name of the item shown by the crate.
  DisplayName: '&7&lBasic Grass'
  #Item that is shown by the crate.
  DisplayItem: 'GRASS'
  #The amount that is displayed.
  DisplayAmount: 1
  #Lore will be shown in rewards GUI.
  Lore:
    - '&7Win some grass for your fields.'
    - '&6&lChance: &c&l40%'
  #Adds enchantments to the display item.
  DisplayEnchantments:
    - 'PROTECTION_ENVIRONMENTAL:1'
    - 'OXYGEN:1'
  #The max range that the chance will go though.
  MaxRange: 100
  #Chance of that item getting picked. It would be 40/100 chance because MaxRange is 100.
  Chance: 40
  #Firework when it is won.
  Firework: false
  #Toggle if the item has a glowing effect but doesn't have an enchantment on it.
  Glowing: false
  #Set the item to 397:3 and then add the players name for this to take effect.
  Player: ''
  #Adds the unbreaking NBT tag to the display item to allow it to have custom textures.
  Unbreakable: false
  #When set to true, tags like Armor, Unbreakable and other tags are hidden and not visible to the user.
  HideItemFlags: false
  # Items that the player wins if this prize is picked. (If you wish not to give an Item in the prize just delete the Items Section)
  # Items: Options
  # Item:<ID:MD> - You can choose the item with its id and meta data.
  # Amount:<Number> - Choose how many of the item you get.
  # Name:<Name> - The display name that goes on the item.
  # Lore:<Line 1>,<Line 2>,<Line 3>,<Line 4> - The lore that will go under the enchantments. Split lines with a ','
  # Unbreakable-Item:<True/False> - Will add the Unbreaking NBT tag to the item to allow custom textured items to be gained through the envoys.
  # <Enchantment>:<Level> - Choose the enchantment you want to add to the item. You can use the in-game names of the enchantment if you want. Replace the spaces in the name with "_".
  Items:
    - 'Item:GRASS, Amount:32, Name:&7&lBasic Grass'
  #Commands are the commands that are run when this prize is won. (If you wish not to use a CMD in the prize just delete the Commands Section)
  #You can use %Player% to get the player that won the prize.
  Commands:
    - 'broadcast &6&l%Player% &7has just won some Basic Grass.'
  #Messages: option allows you to send players messages and not have to pm them with commands.
  #If you do not wish to have players get messaged that they won this prize then just remove the Messages: option.
  Messages:
    - '&7You just won a &7&lBasic Grass&7.'
  #This allows for one time winnable prizes. If a player has one of the permissions then they will not be able to win it.
  BlackListed-Permissions: []
  #This allows users who have won the same prize before to get alternative prizes. They must of a BlackListed-Permission to get a alternative prize.
  Alternative-Prize:
    #Toggle if the prize will use alternative prizes for the blacklisted permission.
    Toggle: false
    Messages: []
    Commands: []
    Items: []
```
Way too much information, right? The comments, as helpful as they are, aren't actually needed, since, through one quick read-over of them and maybe a short read of the [plugin wiki](https://github.com/badbones69/Crazy-Crates/wiki), you shouldn't need to use them much. So, we're going to remove those, as well as the sections and keys we don't use to condense this crate prize. This will allow us to add more prizes with less trouble due to the decreased amount of scrolling and reading. Messy file, messy server! Take a look down below for the more barebones version of this:
```yaml
1:
  DisplayName: '&7&lBasic Grass'
  DisplayItem: 'GRASS'
  DisplayAmount: 1
  Lore:
    - '&7Win some grass for your fields.'
    - '&6&lChance: &c&l40%'
  DisplayEnchantments:
    - 'PROTECTION_ENVIRONMENTAL:1'
    - 'OXYGEN:1'
  MaxRange: 100
  Chance: 40
  Items:
    - 'Item:GRASS, Amount:32, Name:&7&lBasic Grass'
  Commands:
    - 'broadcast &6&l%Player% &7has just won some Basic Grass.'
  Messages:
    - '&7You just won a &7&lBasic Grass&7.'
```
See how much smaller, and easier to read this is? When coming across a plugin like this, it's always best that you remove sections and keys (maybe even comments) that you don't need. This will make your configuration files much easier to read and easier to work on. A more condensed form of prize-making such as this will allow for less scrolling and reading.

!!! info ""

    *Please note that some information may be wrong in this wiki, and I have done my best to ensure whatever has been written is correct. This was written in British English (with the odd oxford comma). If you believe there is a spelling, grammatical, or technical error, please contact me immediately through Discord:* ***longbow122#1576***