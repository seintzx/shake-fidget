# Shake and Fidget

> NOTE: In the config file the password is in plaintext so remember to obfuscate
> it if you want to share the config file

This is my guide on how to use and setup the bot, it's config and general tips
on the game

## BOT

[Source Here](https://www.mfbot.de/forum/viewtopic.php?f=20&t=1391)
> NOTE: I suppose you already have `Raspbian` installed

### Download

Download the bot [here](https://www.mfbot.de/en/downloads/), select the one
according to your architecture

Raspberry Pi3: `ARM processors  (ARM standard Hard Float, tested with Debian 7)`
Odroid C2: `ARM64 processors  (ARM 64-bit, tested with Debian 7)`

### Raspbian Dependencies

```
sudo apt update -y && sudo apt install -y \
    screen vim wget \
    apt-transport-https dirmngr gnupg ca-certificates \
    mono-devel referenceassemblies-pcl ca-certificates-mono \
    libcurl4-openssl-dev libssl-dev \
    tightvncserver gsfonts-x11 xfonts-75dpi xfonts-100dpi
```

### Archlinux Dependencies

```
sudo pacman -S referenceassemblies-pcl mono screen gnupg ca-certificates cronie
```

### Set up

First you have to run the bot on windows in order to create some files (and the
language pack if you want, default is German)

I suggest to set the settings on windows since it's easier and more intuitive at
the beginning

Now copy the created file into you folder on the Raspi and run the bot

### Config file explanation

The file `Acc.ini` is the config file, it is splitted into `two + X` sections:
- `[COMMON]`: Global settings
- `[GUI]`: GUI stuff, mainly for the graphical version
- `[NAME@SERVER]`: config for each server
    - you can have as many as you want (I think, never tested with more than
      one)

> NOTE: Do not touch the first two unless you know what you are doing

In the repo you will find the `[NAME@SERVER]` config for the "_free to play_"
style and one for the "_big spender_" style

For the "_free to play_" style you can leave it like that, maybe play a bit with
it to understand how the bot works

Meanwhile for the "_big spender_" style you need to change some config
accordingly to the level, opponents and your play style (if you play this kind
of style, I'm sure you know what to do)

There's also an `Acc.ini` that it's the combination of both

## Crawler

[Here](https://www.mfbot.de/forum/viewtopic.php?t=1314) you can find an awesome
tool that will help you with the `Scrapbook`

### Suggested settings
- Hall of Fame page: 100
- Start Page: 2
- Max Player Level: 400

### Usage

1. Click on `Crawl` under `Scrapbook`
    - This will store the item you already have and haven't in order to find
      what you need
2. Click on `Crawl` under `Hall of Fame`
    - This will search player's item that you don't have
3. Click on `Analyze`
    - This will show you some information, what you need to look at is **Needed
      Items**. Click on it
4. You will see a table, check `Remove doubled Items` and you will have the list
of players you need to **beat** in arena to discover their items

## Useful information

### Feature Unlock Level

- Level 1: a new hero is born!
- Level 10: Daily Missions, Scrapbook (Magic Shop), Dungeon 1 (Quests) & sending
  private messages unlocked
- Level 20: Dungeon 2 unlocked (Quests)
- Level 25: Fortress unlocked
- Level 30: Dungeon 3 unlocked (Quests)
- Level 40: Dungeon 4 unlocked (Quests)
- Level 50: Magic Mirror (Quests) & Dungeon 5 unlocked (Quests)
- Level 66: Witch unlocked
- Level 70: Dungeon 6 unlocked (Quests, Magic Shop)
- Level 75: Pets unlocked (Quests)
- Level 80: Dungeon 7 unlocked (Quests)
- Level 90: Blacksmith unlocked (also needs Pets)
- Level 95: Dungeon 8 (Quests) & Wheel of Fortune 2.0 (Quests) unlocked
- Level 99: Demon's Portal unlocked
- Level 100: Arcane Toilet unlocked
- Level 105: Arena Manager
- Level 110: Dungeon 9 (Quests, Weapon Shop) unlocked
- Level 125: Shadow World unlocked (also needs access to Tower)
- Level 125: Twister unlocked (also needs access to Tower)
- Level 200: Dungeon 15 unlocked
- Level 350: Shadow Dungeon 15 unlocked

- Tower: clear Dungeons 1-9
- Underworld: Gem Mine (Fortress) Level 10+, access to Tower
- Key to Dungeon 10: after clearing Dungeons 1-9
- Key to Dungeon 11: after clearing Dungeon 10 or clearing the first 10 Twister
  floors
- Key to Dungeon 12: after clearing Dungeon 11
- Key to Dungeon 13: after clearing Dungeon 12
- Key to Dungeon 14: in the Gem Mine of the Fortress is Dungeon 12 is already
  open
- Key to Dungeon 16: in the Gem Mine of the Fortress is Dungeon 12 is already
  open
- Keys to Shadow Dungeons 2-14: after clearing 5+ Floors of the previous Shadow
  Dungeon (Gem Mine)
- Key to Shadow Dungeons 16: after clearing 5+ Floors of Shadow Dungeon 12 (Gem
  Mine)

## Guide

### Character

Skill Balance: 35 main stat, 10 other, 30 cos, 15 luck

Gem Balance: 5 main/4 cos, main on weapon always

### Fortress

- Upgrade Order Suggestion: Fortress, Worker, Stoner, Wooder
- Keep Gem Mine at level 1 until fortress is at 10, then rush the mine
- Hall of Knight at the same level as the fortress
- Avoid building defenses until really needed
- Academy and Treasury as you prefer
- Attack as much as you can everyday

### Witch

Everyday she will ask for a different item, if you throw it in the cauldron you
will get **double** gold and you will also increase a global percentage

Every time this percentage reach 100% the world will unlock an enchant scroll
that you can buy with gold (no mushrooms)

**Remember to enchant an item if you change it!**

#### Available Enchant

- Headgear: 10 XP bonus per quest
- Chest armor: +50% chance to find mushrooms
- Gloves: +1 reaction boost (higher strikes first)
- Footwear: 30 seconds less travel duration
- Weapon: 5% more damage on a critical hit
- Amulet: +10% chance to find items
- Belt: Can drink 1 more beer per day 
- Ring: 10 gold bonus per quest
- Talisman: Up to 20% more gold in arena fights

### Pet

You can find them on missions, **level up only the third pet untill he reaches
level 100**

To level up a pet you need `pet-food` that can be found in the pet arena (once
per day for each habitat) or in the pet dungeon (shares CD with other dungeons)

#### Pet toLevel

- Water: 3,13,16
- Light: 3,13,18
- Earth: 3,13,18
- Shadow: 3,13,17/18
- Fire: 3,13,16

#### Pet Bonus

For each pet you own in every habitat one of your stat will be increased of 1%
- Water -> Str
- Light -> Dex
- Earth -> Int
- Shadow -> Cos
- Fire -> Luck

### Blacksmith

You can do 5 things here:
- Add a socket
- Extract a gem
- Disassemble an item
- Improve items
- Change look at epics

#### Add a socket

You can add a gem slot to an item
**Never spend materials for it, use only mushrooms and only if you can afford
it**

#### Extract a gem

You can retrieve a gem from an item, the item will be destroyed

**Never spend materials for it, use only mushrooms and only if you can afford
it**

#### Disassemble items

Each day you can disassemble up to 5 items to gain materials

After you have gained some material it's good to start upgrading an item of one
or two level before disassembling it to increase the pink dust outcome

If you destroy or sell (even the cauldron) an upgraded item you will be refunded
with the materials you spent on the upgrade

#### Upgrade an item

This will increase the stats an item gives, each item can be upgraded a maximum
of 20 times

### Toilet

You can throw an item into it and you will be given another item in return

You can do it as many times as you want (once per item) but only the first item
will increase your tank

Once the tank is full you can flush it and you will be given an item

Normal item increase the tank by 25, epics by 50, gems by 30 and potions by 10

### Companion

Companion will be unlocked when you unlock the tower. You have 3 of them, one
for each base class

The only way to upgrade them is with gold, their max level is your level

You can equip them with your gear (the one that has you same class) and the
other you will need to use the `Toilet`

### Underworld

- Suggested upgrade order: Heart of Darkness, Gate, Keeper, Soul Extractor,
  Gladiator, Torture Chamber
- Gold Pit and Time Machine as you wish
- Never build the Troll and keep goblin at level 1

My strategy is to keep everything equal, except for trolls and goblins

### Arena Manager

It's similar to any IDLE money game, you upgrade stuff, they give you money to
upgrade more stuff, here it's same with the little difference that every a
certain amount of money you also gain `rune` (still have to find out the rate),
and for every rune you have you will gain 5% more money from every perk

Every time you sacrifice you restart from scratch but you will gain some
`runes`, they can't be spent but after you store 1000+ of them you will get a
chance to have bonus enhancement on equip you find, the more rune you have the
higher the chance and quality of that enhancement

Every 20H a merchant will appear, for only 2H, where you can buy upgrades to the
perks for mushrooms (obviously) that will boosts them permanently (even after
sacrifice)

This is a new feature, I still have to find the best combination of when to
reset, what to buy from the merchant, so I'll keep you posted

List of possible enhancement:

