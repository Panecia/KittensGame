# ScriptKitties
A script to automate playing the addicting [Kittens Game](https://kittensgame.com/web/).

Note: This was a fork from the script MaPaul1977 originally made with some modifications by araemo, and others by Tsolron.

Note: This is a _total_ overhaul of the above.

Note: Personal branch to try fixing small issues run into during later game play. Not intended for general use, I only test on personal game state.

## How do I use the script?

If you want to use this, you need to load it into the browser. The easiest way is to create a bookmarklet like the following, and run it after loading the game. However, Github doesn't like people using it as a hosting solution, so they've deliberately broken the ability to use it for that. However, [jsDelivr](https://www.jsdelivr.com/), offers a free CDN solution for GitHub repos, so you can use the follow.

    javascript:(function(){var d=document,s=d.createElement('script');s.src='https://cdn.jsdelivr.net/gh/Panecia/KittensGame@main/ScriptKitties.js';d.body.appendChild(s);})();

Alternatively, you can paste the contents of the script into the developer console. If you use TamperMonkey, or similar, you can use [autoload.user.js](autoload.user.js).

Once loaded, the button to get to the ScriptKitties option menu is in the bottom right "footer" links. It's very small, people often don't notice it at first.

## What does it do?

Currently this script can be set to automate the following:

**BUILD:** ScriptKitties will automatically build any of the buildings on the Bonfire tab, and it lets you choose exactly which ones you want! If you want to turn on or off an entire group of buildings, just click the header. For space buildings, click the small "space" link in the upper corner. Religion and Time building are both grouped together under "time".

**ASSIGN:** Lazy kittens not doing anything? Give a specified role to all those "free" kittens! There is now a "Smart" option, which will try to balance kittens between various jobs.

**CRAFT:** ScriptKitties keeps your resources from capping out! You can be sure to keep a healthy supply of crafted resources coming! The "secondary craft" ratio helps control how much to craft. If the amount of product drops below the "minimum", it will craft some before you hit the capacity, useful when storage gets large. Conversely, the "maximum" controls the ratio for input resources that have unlimited storage.

**HUNT:** Don't let your catpower go to waste! Automatically send your kittens on hunting expeditions to get your furs, ivory, and unicorns!

**TRADE:** Automagically trade with Zebras and the Elders! Keep your titanium stores full and never miss a visit from the Elders! Elder trade can be disabled in the minor options.

**PRAISE:** Want a praise bonus that will make a difference? Turn on Auto Praise and see your faith based productivity skyrocket by praising the sun every tick!

**PARTY:** If you have the resources, ScriptKitties will keep the festival going!

**EMBASSIES:** Do you like trading? Embassies help trading. How about automatically building the cheapest one every time culture maxes out?

**EXPLORE:** Automatically sends out explorers whenever a new civilization can be reached.

**CYCLES:** Master time itself! Always enjoy the benefits of your favourite cycle!

**SHATTERSTORM:** Is there some strange reason you'd like to shatter as often as heat allows? Well, then this is the option for you. If Auto Cycle is also set, you'll always end the shatterstorm in your chosen cycle.

**SCIENCE:** Don't let your kitten kingdom stagnate! As soon as you have the requirements, ScriptKitties will make sure to research new technologies for you.

**UPGRADE:** Want to upgrade your buildings and abilities, but don't want to just sit there waiting? Let the script make upgrades whenever you are able!

**RELIGION:** Want all those amazing temple upgrades? Want no more!

**UNICORNS:** Never sure which one is most cost-effective? Stop wondering and let ScriptKitties build those wonders for you!

**ENERGY:** Don't worry about having negative energy or wasted potential! Turn on Energy Control, and you will stay between 0 and 3 Watts of surplus power!

**TEMPUS FUGIT:** Time doesn't fly when you don't have this set! Will try to use flux as often as possible, but keeps a reserve for getting Chronosurge next run.

You can use this script as much or as little as you like, but if you turn on all the options, it will basically run the Kittens Game from reset to reset.

Enjoy!

## Minor Options
These are a set of smaller options that do not warrant space in the main UI. Most are fairly obvious, primarily due to the longer names allowed by the menu.

Praise After Religion: If Auto Religion determines that all options are limited by capacity, it will turn on Auto Praise. Note that it will not turn it back off when storage increases.

Conserve Exotic Resources: Prevents Auto Science and Auto Upgrade from using relics, void, antimatter, blackcoin, flux, and similar.

Unicorn Ivory Optimization: By default, Auto Unicorn optimizes for Tears, later on, Ivory becomes the limiting factor, and this option tells it to switch to that.

## What does Auto Play do?
Auto Play is a series of scripts for fully automating parts of mid, late, and endgame. They are customized to my game state at the point I needed them. If they do not seem to work, check the console. They are likely to have more bugs than the rest of the code. Most of them are intended to run reset-to-reset, and if you permit Auto Play to reset, they can run unattended for hours or weeks.

Fast Paragon: rapidly resets (~40 minutes) with near max housing, five chronospheres, and flux condensator.

DF ChronoExpo: build 67+ chronospheres by shattering until Dark Future. Goal is to exponentiate relic/void/antimatter storage. Will spend some antimatter on AI Cores to optimize.

Short ChronoExpo: as above, but without waiting for Dark Future. This option bleeds time crystals.

Hoglagame - {Hunt,Mint,Trade}: very rapid resets for the post 100-CS era. The suffix is how to manage catpower.

CryEngine: cry some more. (note: does not usefully manage HG)

## Tsolron's notable modifications:
* Can autocraft resources without also auto-crafting furs to Parchment (or others in that line)
* If Blueprints are selected, will only craft Compendiums if there are not enough to make Blueprints
* Will auto-build buildings even if you haven't unlocked some of them
* Fixed building selection pop-up so all buildings appear on-screen

## Jonathan's notable modifications:
* Building list is dynamically populated from game data
* Crafting from Science and Culture tries to maintain a large stockpile for the user
* Better handling of crafting that takes multiple inputs (steel, alloy, ...)
* Eliminate tab-switching to improve usability while script is running
* AutoEmbassy(), AutoExplore(), AutoCycle(), AutoShatter(), AutoReligion(), AutoUnicorn(), ...
* Numerous bugfixes, most of which are for bugs he introduced.

## Important Considerations
* Some scripts can starve other scripts of resources. Most obvious is that "Auto Religion" will never do anything if "Auto Praise" is on. More subtly, since "Auto Craft" only uses capped resources, it won't generate Steel or Alloy until "Auto Build" is done with them. 
* "Auto Cycle" won't stop just because the fabric of spacetime is melting due to chronoheat. Build some Furnaces.
* Try to keep Coal generation less than Iron generation so that Plates get crafted.
* Early game, the script will make poor choices, because it does what is cheapest.

## Any special thanks?

A huge thanks to the authors of both AutoKittens and KittenScientists for some of the ideas I integrated into this script!

Thanks also go out to each of these reddit users for their help!

- Patashu
- Saucistophe
- Trezzie
- DamianDavis
- curiouscorncob
- hughperman
- dbsps
- kbob
