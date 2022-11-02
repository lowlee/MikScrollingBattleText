Mik's Scrolling Battle Text Readme body { font-size: 10pt; font-family: verdana, arial, helvetica, sans-serif; } h1 { font-weight: bold; color: #004080; } a:link { color: #000060; text-decoration: none; } a:visited { color: #000060; text-decoration: none; } a:hover { text-decoration: underline; } div#HeaderBlock { background-color: #e0e0e0; border: 1px solid #000060; padding: 1ex; margin: 2em 0em 4em 0em; } div.TOCTitle { font-weight: bold; font-size: 14pt; color: #004080; border-bottom: 1px solid #000060; } div.TOC { margin: 2ex 1ex 4em 2ex; } div.TOCSection { margin-bottom: 2ex; } div.SectionTitle { margin-top: 6ex; font-weight: bold; font-size: 14pt; color: #004080; border-bottom: 1px solid #000060; } div.SectionBody { margin: 2ex 0ex 2ex 2ex; } div.SectionBody ul { margin-top: 1ex; } div.SectionBody a:link { color: #002080; } div.SectionBody a:visited { color: #002080; } div.SectionBody a:hover { text-decoration: underline; } div.SubsectionTitle { margin-top: 4ex; margin-bottom: 2ex; font-weight: bold; font-size: 110%; color: #004080; } div.SubsectionBody { margin: 2ex 0ex 2ex 2ex; } div.TriggerParameter { margin-left: 2ex; } td.ParameterName { font-size: 10pt; background-color: #e0e0e0; vertical-align: top; } td.ParameterDesc { font-size: 10pt; background-color: #e0e0e0; text-align: left; } li.FAQListItem { margin-bottom: 6ex; }

Mik's Scrolling Battle Text
===========================

Version: 5.7.148  
Author: Mikord  
Updated: February 5, 2018  
Official Site: [https://wow.curseforge.com/projects/mik-scrolling-battle-text](https://wow.curseforge.com/projects/mik-scrolling-battle-text)  
  
[See Credits](#Credits)

Table of Contents:

*   [What's new?](#WhatsNew)
*   [Installation Instructions](#Install)
*   [Description](#Description)
*   [Commands](#Commands)
*   [Trigger Guide](#TriggerGuide)
    
    *   [Basic Concepts](#TriggerBasicConcepts)
    *   [Trigger Mechanics](#TriggerMechanics)
    *   [Advanced Concepts](#TriggerAdvancedConcepts)
    *   [Example Triggers](#ExampleTriggers)
    
*   [Trigger Reference](#TriggerReference)
    
    *   [Trigger Main Events](#MainEvents)
    *   [Main Event Conditions](#MainEventConditions)
    *   [Trigger Exceptions](#TriggerExceptions)
    
*   [Search Pattern Reference](#SearchPatternReference)
*   [Frequently Asked Questions](#FAQ)

*   [I don't like any of the fonts supplied with MSBT. How do I use my own fonts?](#FAQFonts)
*   [How do I increase the font size to something larger than 38?](#FAQFontSize)
*   [How do I add my own custom sounds?](#FAQSounds)
*   [How do I create a new trigger?](#FAQNewTrigger)
*   [Is it possible to prevent Mutilate from being merged?](#FAQMutilate)
*   [Is is possible to disable the default Blizzard XP Text?](#FAQXP)
*   [How do I suppress Vampiric Embrace?](#FAQVE)
*   [I want to see skill names even when there is an icon. Is that possible?](#FAQExclusiveIcons)
*   [Is there a way to show the damage above the target's heads like the default damage text?](#FAQGameDamage)
*   [Is MSBT efficient?](#FAQEfficiency)

*   [Version History](#VersionHistory)
*   [Credits](#Credits)

Installation Instructions

[Return to TOC](#TOC)  
  

Unzip the contents into the AddOns directory of your WoW game directory.  
  
This is typically C:\\Program Files\\World of Warcraft\\Interface\\AddOns.  
  
**If you are upgrading the mod from a previous version, make sure to delete the old version prior to installing the new version.**

Description

[Return to TOC](#TOC)  
  

MSBT is designed to be an extremely lightweight, efficient, and highly configurable mod that makes it easier to see combat information by scrolling the information on the screen in separate, dynamically creatable scroll areas. It is a replacement for Blizzard's Floating Combat Text and Damage output.  
  

Features:

*   Lightweight and efficient design.
*   Scroll incoming damage/heals, outgoing damage/heals, and notifications in separate configurable scroll areas on the playing field.
*   Display cooldown completion alerts.
*   Display loot alerts with a total of how many are now in inventory.
*   Add triggers that will allow you to show notifications based on a variety of conditions.
*   Assign a sound file to play for events/triggers.
*   Dynamically create new scroll areas and assign any event/trigger to them.
*   Customize the position, size, animation style, enabled state, font style, font size, font outline, and opacity for each of the scroll areas.
*   Customize each individual event's color, font style, font size, font outline, opacity, output message, enabled state, and scroll area.
*   Set "Master Font" settings that will be inherited by all of the scroll areas and the events in them unless they are overridden at the scroll area or event level.
*   Merge AoE data into one event with cumulative damage/healing done with number of normal and crits specified.
*   Show overhealing amounts against yourself or party/raid members.
*   Color unit names according to their class (including CUSTOM\_CLASS\_COLORS support).
*   Color damage amounts according to damage type.
*   Show partial effects (resists, absorbs, vulnerabilities, etc) colored according to type.
*   Filter output information with a full suite of spam controls.
*   Load on demand options.
*   For mod developers:
    *   Output your own scrolling messages with the MikSBT.DisplayMessage function instead of having to create your own frame and animation code. You can also use your own font by first registering it with MSBT via the MikSBT.RegisterFont function.
    *   Create custom animation styles.
    *   See the included API.html file for reference information.

Supported Events:

*   Incoming:

*   Melee Damage, Misses, Dodges, Parries, Blocks, Deflects, Absorbs, and Immunes
*   Skill Damage, Damage Over Time (DoTs), Misses, Dodges, Parries, Blocks, Deflects, Absorbs, Immunes, Reflects, and Interrupts
*   Spell Resists
*   Heals and Heals Over Time (HoTs)
*   Pet Melee Damage, Misses, Dodges, Parries, Blocks, Deflects, Absorbs, and Immunes
*   Pet Skill Damage, Damage Over Time (DoTs), Misses, Dodges, Parries, Blocks, Deflects, Absorbs, and Immunes
*   Pet Spell Resists
*   Pet Heals and Heals Over Time (HoTs)
*   Environmental Damage

  
*   Outgoing:

*   Melee Damage, Misses, Dodges, Parries, Blocks, Deflects, Absorbs, Immunes, Evades
*   Skill Damage, Damage Over Time (DoTs), Misses, Dodges, Parries, Blocks, Deflects, Absorbs, Immunes, Reflects, Interrupts, and Evades
*   Spell Resists and Buff Dispels
*   Heals and Heals Over Time (HoTs)
*   Pet Melee Damage, Misses, Dodges, Parries, Blocks, Deflects, Absorbs, Immunes, and Evades
*   Pet Skill Damage, Damage Over Time (DoTs), Misses, Dodges, Parries, Blocks, Deflects, Absorbs, Immunes, and Evades
*   Pet Spell Resists and Buff Dispels
*   Pet Heals and Heals Over Time (HoTs)

  
*   Notification:

*   Buffs / Buff Stacks / Buff Fades
*   Debuffs / Debuff Stacks / Debuff Fades
*   Item Buffs / Item Buff Fades
*   Enter/Leave Combat
*   Power Gains and Losses
*   Alternate Power Gains and Losses
*   Chi Gains and Chi Full
*   Combo Point Gains and Combo Points Full
*   Holy Power Changes and Holy Power Full
*   Honor Gains
*   Reputation Gains and Losses
*   Skill Gains
*   Experience Gains
*   Killing Blows (Player and NPC)
*   Extra Attacks
*   Soul Shard Creation
*   Enemy Buff Gains
*   Monster Emotes
*   Player, Pet, and Item Cooldown Completions

  
*   Loot:

*   Looted Items
*   Money Gains

  
*   Default Triggers:

*   All Relevant Classes - Low Health, Low Mana, Low Pet Health
*   Death Knight - Killing Machine, Rime, Shadow Infusion x5
*   Druid - Berserk, Clearcasting, Predator's Swiftness, Shooting Stars
*   Hunter - Kill Shot, Lock and Load
*   Mage - Brain Freeze, Clearcasting, Fingers of Frost, Missile Barrage
*   Monk- Elusive Brew x5, x10, x15, Mana Tea x20, Vital Mists x5
*   Paladin - Hammer of Wrath, The Art of War
*   Priest - Clearcasting
*   Rogue - Blindside
*   Shaman - Clearcasting, Lava Surge, Maelstrom Weapon x5, Tidal Waves
*   Warlock - Decimation, Molten Core, Nightfall
*   Warrior - Bloodsurge, Execute, Revenge, Sudden Death, Taste for Blood, Victory Rush

Commands

[Return to TOC](#TOC)  
  

/msbt

Shows the options interface.

/msbt reset

Resets the current profile to the default settings.

/msbt disable

Disables the mod.

/msbt enable

Enables the mod.

/msbt version

Shows the current version.

/msbt help

Shows the command usage.

Trigger Guide

[Return to TOC](#TOC)  
  

The trigger system is a powerful and flexible system that allows you to specify custom events to be displayed based on specific game events that are not already handled by default. There are several mechanisms in place to ensure triggers are efficient as possible so they are not needlessly wasting CPU cycles checking conditions that aren't relevant. Due to this optimization, several common triggers are included by default.

Basic Concepts:

Every time almost anything happens in the game, a combat log entry is generated for it. While it is not readily visible, each of these combat log entries is categorized by Blizzard according to specific event types. It is these event types that drive triggers. Triggers are really just definitions of a specific set of circumstances that must occur before they will fire.  
  
Aside from being categorized into an event type, each event that occurs in game has several other pieces of information associated with it such as who the source of the event was, how much the event hit or healed for, and whether or not the event was a crit. Obviously this additional information varies according to the type of event it is since, for example, an aura application can't crit.  
  
The trigger system refers to these event types as [main events](#MainEvents) and the additional pieces of information as [conditions](#MainEventConditions), since ultimately it is these additional pieces of information that define the specific circumstances of interest.  
  
Let's consider an example event to better understand how the pieces fit together. Assume that you were just hit by a fireball. The damage caused to you by the fireball generated an event of type "Skill Damage". The event also has many of other pieces of information associated with it like the name of the unit who cast the fireball, how much the fireball hit you for, whether or not it crit, whether the unit who cast the fireball is a player or an NPC, etc.  
  
Putting the above fireball example in terms of the trigger system, the fireball hitting you was a [main event](#MainEvents) of type "Skill Damage", and the [conditions](#MainEventConditions) were the name of the unit who cast the fireball, how much it hit you for, and so on.  
  
While the [main events](#MainEvents) and their [conditions](#MainEventConditions) offer a wealth the information, there is other non-event related "state" information available such as the current zone your character is in, whether or not certain buffs are active, and whether or not certain skills are available. This "state" information forms the basis for what the trigger system refers to as [exceptions](#TriggerExceptions). An [exception](#TriggerExceptions) will prevent a trigger from being displayed when it applies.

Trigger Mechanics:

Now that it is clear what [main events](#MainEvents), [conditions](#MainEventConditions), and [exceptions](#TriggerExceptions) are, we can explore how triggers make use of them and consequently how they are defined.  
  
The following list summarizes the stages a trigger follows to determine whether or not it fires:

1.  One of the [main events](#MainEvents) that a trigger has defined occurs.
2.  The specific [conditions](#MainEventConditions) defined for the [main event](#MainEvents) for the trigger are tested. If any of the conditions do not apply, the trigger will not fire and all processing for the trigger stops.
3.  The [exceptions](#TriggerExceptions) defined for the trigger are tested. If any of the exceptions apply, the trigger will not fire and all processing for the trigger stops.
4.  The trigger fires thus displaying the specified output message and event settings.

  
As mentioned in the "[Basic Concepts](#TriggerBasicConcepts)" section above, triggers are driven by [main events](#MainEvents). Each trigger can be based on one or more of these [main events](#MainEvents) each with unique [conditions](#MainEventConditions). These [main events](#MainEvents) are treated as an "or" relationship meaning that when **ANY** one of them occurs, the trigger will move to the next stage of testing the [conditions](#MainEventConditions).  
  
The [conditions](#MainEventConditions) defined for a given [main event](#MainEvents) are treated as an "and" relationship meaning that **ALL** of them must be true for the trigger to move to the next stage of testing [exceptions](#TriggerExceptions).  
  
During the final stage, the [exceptions](#TriggerExceptions) defined for a trigger are treated as an "or" relationship meaning that when **ANY** one of them is true, the trigger will not fire.

Advanced Concepts:

Most common triggers won't need to delve into any of the concepts presented in this section, but using some of the more advanced capabilities can lead to triggers for highly complex events or single triggers capable of handling multiple events.  
  
Here is an overview of the main points that will be covered:

*   Each [main event](#MainEvents) can be used multiple times for a single trigger
*   Each [condition](#MainEventConditions) can be used multiple times for a given [main event](#MainEvents).
*   Triggers will try to choose an appropriate icon based on the [main event](#MainEvents) that fired it.
*   Substitution codes for skill names are available.
*   Skill IDs can be used to discern which rank of a skill was used.

  
Recall from the "[Trigger Mechanics](#TriggerMechanics)" section that each trigger can have multiple [main events](#MainEvents) treated as an "or" relationship, and that each [main event](#MainEvents) can have its own unique [conditions](#MainEventConditions). Combining that with the capability to use a [main event](#MainEvents) multiple times for a single trigger means you can effectively cover a set of common scenarios all with a single trigger. For example, imagine you want to see when both Mace Stun and Improved Hamstring proc. Both cases are an aura application, but they have different skill names. By adding the same [main event](#MainEvents) twice, but specifying a different skill name [condition](#MainEventConditions) for each one, you are effectively saying when Mace Stun or Improved Hamstring proc this trigger should fire. Naturally the other [conditions](#MainEventConditions) such as affiliation and reaction would need to also be set for each event.  
  
The astute reader will say "Wait a second! How will I be able to tell which one procced if the output message is the same?". This problem is solved with substitution codes. Depending on which event actually caused the trigger to fire, %s will be replaced the appropriate skill name. Also, the correct icon would be displayed since triggers attempt to choose an appropriate icon based on the [main event](#MainEvents) that fired them.  
  
The capability of using the same condition multiple times for a given [main event](#MainEvents) with different relationships means that things such as ranges and complex pattern matching can be implemented. For example, imagine you are trying to create a trigger that will fire when an amount is between two values. The first [condition](#MainEventConditions) could be "Amount - Is Greater Than - X" and the second could be "Amount - Is Less Than - Y".  
  
Another advanced capability is using skill IDs to detect when specific ranks, such as rank 1, are being used. Most online databases can be used to ascertain what the skill ID is for the ranks of each skill. By adding [conditions](#MainEventConditions) that specify these specific skill IDs, it is possible to only trigger on specific skill ranks.

Example Triggers:

Since the point of the trigger system is to allow for custom events that are not already available, there is no way to cover all of the possibilities. However, most commonly requested triggers fall within the following categories. An example trigger or two for each category is provided and can be used as a guide to creating your desired trigger.  
  
Please note these examples don't make use of advanced capabilities in order to keep the examples easy to understand.  
  

CC Breaks:

A common request for triggers is to be notified when crowd control skills like sheep, sap, and blind break from your focus target while in the arena. Nearly all of these effects involve removing an aura and therefore the [main event](#MainEvents) type will usually be "Aura Removal".  
  
The most common [conditions](#MainEventConditions) used for this category of triggers are "Skill Name", "Recipient Unit Affiliation", and "Recipient Unit Reaction".  
  
**Polymorph Broke**  
  
Output Message: Poly Broke - %r!  
Main Events:

Aura Removal

Skill Name - Is Equal To - Polymorph  
Recipient Unit Affiliation - Is Equal To - Focus  
Recipient Unit Reaction - Is Equal To - Hostile  

  
Exceptions:

Zone Type - Is Not Equal To - Arena  

Procs:

Another common request for triggers is to be notified when certain procs such as Mace Stun, Improved Wing Clip, or item-based haste effects occur. Nearly all of the effects apply an aura of some sort and as such the [main event](#MainEvents) type will usually be "Aura Application".  
  
The most common [conditions](#MainEventConditions) used for this category of triggers are "Skill Name", "Recipient Unit Affiliation", and "Recipient Unit Reaction".  
  
**Mace Stun**  
  
Output Message: Mace Stun!  
Main Events:

Aura Application

Skill Name - Is Equal To - Mace Stun Effect  
Recipient Unit Affiliation - Is Equal To - Target  
Recipient Unit Reaction - Is Equal To - Hostile  

  
Exceptions:

None

  
  
**Focus** (from Mystical Skyfire Diamond)  
  
Output Message: Focus!  
Main Events:

Aura Application

Skill Name - Is Equal To - Focus  
Recipient Unit Affiliation - Is Equal To - You  

  
Exceptions:

None

Key Skill Usage:

Many players find it useful to create a trigger for when certain key abilities such as Hand of Freedom or Hand of Protection are used while in the arena. Most of these effects involve successfully casting a spell and so the [main event](#MainEvents) type will usually be "Cast Success".  
  
The most common [conditions](#MainEventConditions) used for this category of triggers are "Skill Name" and "Source Unit Reaction".  
  
**Hand of Protection Used**  
  
Output Message: Melee Bubble!  
Main Events:

Cast Success

Skill Name - Is Equal To - Hand of Protection  
Source Unit Reaction - Is Equal To - Hostile  

  
Exceptions:

Zone Type - Is Not Equal To - Arena  

  
  
**Priest Fear Used**  
  
Output Message: Priest Fear Down!  
Main Events:

Cast Success

Skill Name - Is Equal To - Psychic Scream  
Source Unit Reaction - Is Equal To - Hostile  

  
Exceptions:

Zone Type - Is Not Equal To - Arena  

Trigger Reference

[Return to TOC](#TOC)  
  

This section provides a reference for each of the [main events](#MainEvents), [conditions](#MainEventConditions), and [exceptions](#TriggerExceptions) that triggers may utilize.  
  
The following is a description of the fields unique to the trigger system interface:  
  

Output Message:

This is the message that will be displayed when the trigger fires.  
  
Most [main events](#MainEvents) allow the following substitution codes:  

*   %n - The name of the source of the event.
*   %r - The name of the recipient of the event.
*   %a - The amount associated with the event.
*   %s - The skill name associated with the event.

  
In addition, certain [main events](#MainEvents) that involve two different skill names like dispels (the name of skill performing the dispel and the name of the skill being dispelled) allow the following substitution code:

*   %e - The extra skill name associated with the event.

Trigger Classes:

This allows you to set the classes that you want the trigger to apply to. **NOTE: THIS IS YOUR CLASS NOT THE TARGET CLASS.** You may look at the Execute trigger for an example. Since Warrior is selected, the trigger will only apply when you are playing on a warrior.

[Main Events](#MainEvents):

This allows you to define which [main events](#MainEvents) should begin the process of testing the trigger. When **ANY** (or relationship) of these main events occur and their [conditions](#MainEventconditions) are true, the trigger will then make sure none of the [exceptions](#TriggerExceptions) are true before firing.  
  
The [main events](#MainEvents) reference table details the purpose of each event.

[Trigger Exceptions](#TriggerExceptions):

This allows you define [exceptions](#TriggerExceptions) to prevent the trigger from firing.  
  
They are only checked if one of the [main events](#MainEvents) has occurred and all its [conditions](#MainEventConditions) are true.  
  
The [trigger exceptions](#TriggerExceptions) reference table below details the purpose of each exception.

Trigger Main Events:

Aura Application:

Fired when an aura is applied to a unit.

Aura Broken:

Fired when an aura is broken by a skill.

Aura Dispel:

Fired when an aura is dispelled from a unit.

Aura Removal:

Fired when an aura is removed from a unit.

Aura Refresh:

Fired when an aura is refreshed on a unit.

Aura Stolen:

Fired when an aura is stolen from a unit.

Cast Failure:

Fired when a cast fails.

Cast Start:

Fired when a cast begins.

Cast Success:

Fired when a cast successfully completes.

Create:

Fired when items are created. This is typically for conjured items.

Damage Shield Damage:

Fired when damage is done from a damage shield like thorns.

Damage Shield Miss:

Fired when damage from a damage shield like thorns is resisted, absorbed, etc.

Dispel Failed:

Fired when a dispel attempt fails.

Enchant Application:

Fired when an enchant is applied to an item.

Environmental Damage:

Fired when damage is done as the result of an environmental effect like falling and drowning.

Extra Attacks:

Fired when extra attacks occur from abilities like Windfury.

Heal:

Fired when a unit is healed.

Health Change:

Fired when a health value changes for one of the supported units.

Item Cooldown Complete:

Fired when an item cooldown completes.

Killing Blow:

Fired when a unit gets a killing blow.

Periodic Skill Damage (DoT):

Fired when damage from a periodic source is done.

Periodic Skill Miss:

Fired when damage from a periodic source is resisted, absorbed, etc.

Periodic Heal (HoT):

Fired when a unit is healed by a periodic source.

Periodic Power Drain:

Fired when power is drained as the result of a periodic source.

Periodic Power Gain:

Fired when power is gained from a periodic source.

Periodic Power Leech:

Fired when power is leeched as the result of a periodic source.

Pet Cooldown Complete:

Fired when a pet skill cooldown completes.

Player Cooldown Complete:

Fired when a player skill cooldown completes.

Power Change:

Fired when a power value changes for one of the supported units.

Power Drain:

Fired when power is drained from a unit.

Power Gain:

Fired when power is gained by a unit.

Power Leech:

Fired when power is leeched from a unit.

Range Damage:

Fired when damage from a ranged source like wands/bows is done.

Range Miss:

Fired when damage from a ranged source like wands/bows is dodged, absorbed, etc.

Skill Damage:

Fired when damage from a skill was done to a unit.

Skill Interrupt:

Fired when a skill is interrupted (not pushed back).

Skill Miss:

Fired when damage from a skill is resisted, absorbed, etc.

Split Damage:

Fired when damage is being split between the source and recipient units.

Swing Damage:

Fired when damage from normal melee swings is done to a unit.

Swing/Range/Skill Damage:

Fired when any form of non-periodic damage is done to a unit.

Swing Miss:

Fired when damage from normal melee swings is dodged, absorbed, etc.

Swing/Range/Skill Miss:

Fired when any form of non-periodic damage is dodged, resisted, absorbed, etc.

Summon:

Fired when a creature is summoned.

Unit Death:

Fired when a unit dies.

Unit Destroy:

Fired when a mechanical unit is destroyed.

Main Event Conditions:

Absorb Amount:

The amount of damage absorbed.

Amount:

The amount of damage, health, power, etc generated by the event.

Aura Type:

The type of aura (buff, debuff) generated by the event.

Block Amount:

The amount of damage blocked.

Crit:

Whether or not the event is a critical event.

Crushing Blow:

Whether or not the hit was a crushing blow.

Damage Type:

The type of damage (arcane, fire, holy, etc) associated with the event.

Extra Amount:

Secondary amount used for events that have more than one amount value.

Extra Skill ID:

The ID of the secondary skill associated with the event.

Extra Skill Name:

The name of the secondary skill associated with the event.

Extra Skill School:

The school (arcane, fire, holy, etc) of the secondary skill associated with the event.

Glancing Hit:

Whether or not the hit was a glancing hit.

Hazard Type:

The type of hazard (falling, drowning, etc) that caused environmental damage.

Miss Type:

The type of miss (block, dodge, parry, resist, etc) that occurred.

Power Type:

The type of power (energy, mana, rage, etc) that was affected.

Recipient Unit Affiliation:

The affiliation (mine, target, focus, you, party member, etc) of the unit that was the recipient of the event.

Recipient Unit Control:

The controlling mechanism (server, human) of the unit that was the recipient of the event.

Recipient Unit Name:

The name of the unit that was the recipient of the event.

Recipient Unit Reaction:

The reaction (hostile, friendly, neutral) of the unit that was the recipient of the event.

Recipient Unit Type:

The type of the unit (player, pet, NPC, etc) that was the recipient of the event.

Resist Amount:

The amount of damage resisted.

Skill ID:

The ID of the skill associated with the event.

Skill Name:

The name of the skill associated with the event.

Skill School:

The school (arcane, fire, holy etc) of the skill associated with the event.

Source Unit Affiliation:

The affiliation (mine, target, focus, you, party member, etc) of the unit that was the source of the event.

Source Unit Control:

The controlling mechanism (server, human) of the unit that was the source of the event.

Source Unit Name:

The name of the unit that was the source of the event.

Source Unit Reaction:

The reaction (hostile, friendly, neutral) of the unit that was the source of the event.

Source Unit Type:

The type of the unit (player, pet, NPC, etc) that was the source of the event.

Threshold:

Percentage value that must be crossed when dealing with changes in energy, health, mana, etc.

Unit ID:

The ID of the unit affected. Use this condition to test specific units for changes in energy, health, mana, etc.

Unit Reaction:

The reaction of the unit affected by changes in energy, health, mana, etc.

Trigger Exceptions:

Active Talents:

Examines if the specified talent group is currently active.

Buff Active:

Examines if the specified buff is currently active on you.

Current Combo Points:

The current number of combo points you have.

Current Power:

The current amount of power you have.

Trigger Recently Fired:

The number of seconds since the last time the trigger fired.

Trivial Target:

Examines if the current target is trivial (grey).

Unavailable Skill:

Examines if the specified skill is unknown or on cooldown. It does not cover other facets such as necessary reagents, appropriate range, etc.

Warrior Stance:

The current stance your warrior is in. Only works correctly if you are playing a warrior.

Zone Name:

The zone you are currently in.

Zone Type:

The type of zone you are currently in.

Search Pattern Reference

[Return to TOC](#TOC)  
  

Here is the official lua reference for patterns:

Character Class:

A _character class_ is used to represent a set of characters. The following combinations are allowed in describing a character class:

*   x: (where x is not one of the magic characters ^$()%.\[\]\*+-?) represents the character x itself.
*   .: (a dot) represents all characters.
*   %a: represents all letters.
*   %c: represents all control characters.
*   %d: represents all digits.
*   %l: represents all lowercase letters.
*   %p: represents all punctuation characters.
*   %s: represents all space characters.
*   %u: represents all uppercase letters.
*   %w: represents all alphanumeric characters.
*   %x: represents all hexadecimal digits.
*   %z: represents the character with representation 0.
*   %x: (where x is any non-alphanumeric character) represents the character x. This is the standard way to escape the magic characters. Any punctuation character (even the non magic) can be preceded by a '%' when used to represent itself in a pattern.
*   \[set\]: represents the class which is the union of all characters in set. A range of characters may be specified by separating the end characters of the range with a '-'. All classes %x described above may also be used as components in set. All other characters in set represent themselves. For example, \[%w\_\] (or \[\_%w\]) represents all alphanumeric characters plus the underscore, \[0-7\] represents the octal digits, and \[0-7%l%-\] represents the octal digits plus the lowercase letters plus the '-' character.  
      
    The interaction between ranges and classes is not defined. Therefore, patterns like \[%a-z\] or \[a-%%\] have no meaning.
  
*   \[^set\]: represents the complement of set, where set is interpreted as above.

For all classes represented by single letters (%a, %c, etc.), the corresponding uppercase letter represents the complement of the class. For instance, %S represents all non-space characters.  
  
The definitions of letter, space, and other character groups depend on the current locale. In particular, the class \[a-z\] may not be equivalent to %l.

Pattern Item:

A pattern item may be:

*   a single character class, which matches any single character in the class;
*   a single character class followed by '\*', which matches 0 or more repetitions of characters in the class. These repetition items will always match the longest possible sequence;
*   a single character class followed by '+', which matches 1 or more repetitions of characters in the class. These repetition items will always match the longest possible sequence;
*   a single character class followed by '-', which also matches 0 or more repetitions of characters in the class. Unlike '\*', these repetition items will always match the shortest possible sequence;
*   a single character class followed by '?', which matches 0 or 1 occurrence of a character in the class;
*   %n, for n between 1 and 9; such item matches a substring equal to the n-th captured string (see below);
*   %bxy, where x and y are two distinct characters; such item matches strings that start with x, end with y, and where the x and y are balanced. This means that, if one reads the string from left to right, counting +1 for an x and -1 for a y, the ending y is the first y where the count reaches 0. For instance, the item %b() matches expressions with balanced parentheses.

Pattern:

A _pattern_ is a sequence of pattern items. A '^' at the beginning of a pattern anchors the match at the beginning of the subject string. A '$' at the end of a pattern anchors the match at the end of the subject string. At other positions, '^' and '$' have no special meaning and represent themselves.

Captures:

A pattern may contain sub-patterns enclosed in parentheses; they describe captures. When a match succeeds, the substrings of the subject string that match captures are stored (captured) for future use. Captures are numbered according to their left parentheses. For instance, in the pattern "(a\*(.)%w(%s\*))", the part of the string matching "a\*(.)%w(%s\*)" is stored as the first capture (and therefore has number 1); the character matching "." is captured with number 2, and the part matching "%s\*" has number 3.  
  
As a special case, the empty capture () captures the current string position (a number). For instance, if we apply the pattern "()aa()" on the string "flaaap", there will be two captures: 3 and 5.

Frequently Asked Questions

[Return to TOC](#TOC)  
  

1.  **I don't like any of the fonts supplied with MSBT. How do I use my own fonts?**  
      
    
    WARNING: FONT FILES MUST EXIST IN THE TARGET LOCATION **BEFORE** WORLD OF WARCRAFT IS STARTED.  
    IT IS HIGHLY RECOMMENDED THAT YOU PLACE YOUR CUSTOM FONT FILES IN THE MikScrollingBattleText\\Fonts DIRECTORY TO AVOID ISSUES.
    
      
      
    NOTE: Keep in mind that if you use your own font files that you need to make sure the font supports the characters that will be displayed. For example the typical way to display buff gains is \[BuffName\]. If the font you use does not have a character glyph for the \[ or \] characters you will not be able to see the unsupported characters. This is especially important with non-English clients since a lot of characters aren't supported by English fonts.  
      
    There are a couple of ways to use custom fonts:  
      
    *   The first, and preferred method, is to use MSBT's new in-game media editor available under the custom media tab. If you follow the recommended guideline of placing your custom font files in the MikScrollingBattleText\\Fonts directory, all you need to enter for the font path in the in-game media editor is the name of the font file.  
          
        For example, assume you have a truetype font file "MyUberFont.ttf" you want to use.  
          
        1.  Copy the "MyUberFont.ttf" font file into the MikScrollingBattleText\\Fonts directory before you start the game.
        2.  Load the game and access MSBT's custom media tab.
        3.  Click the Add Font button.
        4.  Enter the name you want the font to be called in game such as "My Custom Font" without the quotes.
        5.  Enter "MyUberFont.ttf" without the quotes for the font path.
        6.  Click the Okay button and the new font will be available.
      
      
    *   The second method is aimed more at mod developers that want to display information using MSBT. You can call the MikSBT.RegisterFont function to register a custom font that you may then specify in your call to MikSBT.DisplayMessage. See the included API.html file for reference information.
2.  **How do I increase the font size to something larger than 38?**  
      
    It is not currently possible due to a limitation within the game. Blizzard has stated that allowing larger font sizes is something they would like to implement at some point, but has not provided a time frame.
3.  **How do I add my own custom sounds?**  
      
    
    WARNING: SOUND FILES MUST EXIST IN THE TARGET LOCATION **BEFORE** WORLD OF WARCRAFT IS STARTED.  
    IT IS HIGHLY RECOMMENDED THAT YOU PLACE YOUR CUSTOM SOUND FILES IN THE MikScrollingBattleText\\Sounds DIRECTORY TO AVOID ISSUES.
    
      
      
    There are a couple of methods that can be used to add custom sounds.
    *   The first, and preferred method, is to use MSBT's new in-game media editor available under the custom media tab. If you follow the recommended guideline of placing your custom sound files in the MikScrollingBattleText\\Sounds directory, all you need to enter for the sound path in the in-game media editor is the name of the sound file. The acceptable sound file types are .mp3 and .ogg.  
          
        For example, assume you have an mp3 sound file "MyUberSound.mp3" you want to use.  
          
        1.  Copy the "MyUberSound.mp3" sound file into the MikScrollingBattleText\\Sounds directory before you start the game.
        2.  Load the game and access MSBT's custom media tab.
        3.  Click the Add Sound button.
        4.  Enter the name you want the sound to be called in game such as "My Custom Sound" without the quotes.
        5.  Enter "MyUberSound.mp3" without the quotes for the sound path.
        6.  Click the Okay button and the new sound will be available.
      
      
    *   The second method is aimed more at mod developers. You can call the MikSBT.RegisterSound function to register a custom sound. See the included API.html file for reference information.
4.  **How do I create a new trigger?**  
      
    The first step is to **read** the [Trigger Guide](#TriggerGuide) and [Trigger Reference](#TriggerReference) sections above.  
      
    Among other things, the guide explains how triggers work, what the various components of the trigger system are, and provides example triggers for common categories. The reference section provides specific information about the various components such as the available substitution codes, main events, conditions, and exceptions.  
      
    Once you've read those sections, we can continue on to the process for creating triggers.  
      
    We will be creating a trigger that notifies us when Polymorph breaks from a hostile unit when we are playing on a mage in the arena.  
      
    
    1.  Since a new trigger is being created, click the Add New Trigger button, enter "Poly Broke - %r!" for the output message, and click Okay.
    2.  The trigger conditions configuration dialog for the new trigger will automatically be shown. You can click the trigger conditions icon button (the gear) next to a trigger to access these settings manually at a later time.
    3.  Click the edit Trigger Classes icon button and uncheck "All" classes. Check Mage for the class the trigger will apply to. It is better to select the specific classes the trigger applies to instead of selecting all classes since by specifying classes, the mod can completely ignore the trigger and save resources for the classes to which it does not apply.
    4.  Click the Add Event button next to the Main Events label to add a new main event.
    5.  Select Aura Removal for the Main Event.
    6.  Modify the first condition to "Recipient Unit Reaction - Is Equal To - Hostile" because we don't want to see when poly fades from our teammates.
    7.  Modify the second condition to "Skill Name - Is Equal To - Polymorph". It is case-sensitive, so make sure you use a capital P.
    8.  Click the Save button to save the new main event and its conditions.
    9.  Click the Add Exception button next to the Trigger Exceptions label to add a new exception.
    10.  Select "Zone Type - Is Not Equal To - Arena" for the Exception. This makes it so the trigger will not fire when we aren't in the arena.
    11.  Click the Save button to save the new exception.
    12.  Click the Save button on the trigger frame to save the trigger's new conditions.
    
      
      
    The %r used in step a is a substitution code for the name of the unit that the debuff (polymorph in this case) faded from. You already knew that though because you read the [Trigger Guide](#TriggerGuide) and [Trigger Reference](#TriggerReference)!  
      
    The color, font settings, sticky state, sound, and output scroll area for the trigger can be set like any other event.
5.  **Is it possible to prevent Mutilate from being merged?**  
      
    Yes. Add it to the merge exclusions list under the Spam Controls tab in the options interface.
6.  **Is is possible to disable the default Blizzard XP Text?**  
      
    No. Unfortunately that text is not a part of the UI and Blizzard has not provided the means necessary to disable it. I have requested a CVar to control it several times over the years, but they have yet to add one.
7.  **How do I suppress Vampiric Embrace?**  
      
    This can be accomplished a couple of different ways.  
      
    *   The preferred method is to add it to the skill suppressions list under the Spam Controls tab.
      
      
    *   Another way is to use the heal threshold slider under the Spam Controls tab.  
        The drawback to this approach is that all heals under the specified value will be suppressed and not specifically Vampiric Embrace, which may or may not be your desired behavior.
8.  **I want to see skill names even when there is an icon. Is that possible?**  
      
    Yes. Uncheck "Exclusive Skill Names" under the Skill Icons tab.
9.  **Is there a way to show the damage above the target's heads like the default damage text?**  
      
    The only way this is possible is using the built-in game damage. It can be enabled through the game's interface options, but keep in mind you will lose all customization capabilities for outgoing damage if you choose to use the game's built-in damage. WoW's API does not provide a method to get the position of 3D game objects such as players and mobs. This is intentional on their part and will likely never change.  
      
    I do not recommend using the built-in game damage option. If you take the time to get used to having the damage in a consolidated area, you will likely find it superior in many ways. Aside from the obvious visual customization capabilities of using MSBT's damage display, there are many other benefits such as being able to see the damage and healing being done to targets that are not in your viewport, merging of AoE with cumulative amounts, throttling of DoT spam, damage thresholds, per skill suppressions for things you don't care about, icons annotating which skill caused the damage or healing, and more.
10.  **Is MSBT efficient?**  
      
    Absolutely. MSBT 5.0 was completely re-designed from the ground up using Blizzard's new mod statistics API tools with the #1 priority of optimization for reduced memory usage and CPU efficiency. As a result, it is both lightweight (low memory usage) and efficient (low CPU usage), which, sadly, is frequently ignored in performance discussions. Performance entails both memory usage and CPU usage. Unless you don't have enough RAM available, CPU usage is almost always more of a factor on your FPS than raw memory usage is.  
      
    Please don't just take my word for it though. Test it out for yourself. Blizzard has made it simple to see statistics about mod usage with the GetAddOnMemoryUsage and GetAddOnCPUUsage API calls. Testing a mod will give you a true picture of its performance.  
      
    One thing to keep in mind during your testing is that MSBT is written to be completely dynamic. It will only create exactly what objects it needs when it needs them and then reuse them from that point forward. This means during the first few combat cycles you will see a slightly higher increasing rate than you might expect as the first set of objects is created. The rate will quickly stabilize to typically less than 1 KiB/s as the objects begin to be reused. The main benefits to this approach are less overall memory usage and very little memory churn.  
      
    Also, don't forget to look at CPU utilization. As I said above, it is frequently ignored, but it is also important. Would you rather have your CPU spending extra time on the game engine, or wasting cycles on an inefficient mod?

Version History

[Return to TOC](#TOC)  
  

Latest

*   Moved the new font loader logic into its own frame to prevent issues with UIs such as RealUI that play with opacity on objects they don't own.
*   Fixed unit reaction condition that was preventing many triggers like Kill Shot and Hammer of Wrath from working.
*   Fixed taint issues cause by the \_ global variable.
*   Updated options dialogs to remove reference to support for mp3s which the game no longer supports.

5.7.137

*   Corrected an error that occurs on startup with deleted default triggers.

5.7.136

*   Reworked the font handling to preload fonts during initial load to resolve the issue where the fonts would reset to the default on initial game load.

5.7.135

*   Fixed the ability to add custom fonts via the custom media tab.

5.7.134

*   Fixed an issue where the font previews were not updating properly.
*   Updated parser to support the new parameters introduced by patch 6.0.2.

5.7.132

*   Updated for Patch 6.0.2 / Warlords of Draenor
    *   Modified global constants for item quality to their new values.
    *   Removed Berserker Stance from available trigger conditions.
    *   Removed Backlash default trigger.
    *   Removed Owlkin Frenzy default trigger.
    *   Removed Overpower default trigger.
    *   Removed Power Guard default trigger.
    *   Removed Rune Strike default trigger.
    *   Removed Solar and Lunar Eclipse default triggers.
    *   Modified several skill IDs to reflect their new values.
    *   Updated TOC for Patch 6.0.2.

5.7.131

*   Fixed issue introduced with Patch 5.4 where the fonts could not be changed.

5.7.130

*   Updated TOC for Patch 5.4

5.7.129

*   Fixed issue introduced with Patch 5.3 where dispels were showing the skill performing the dispel rather than the one being dispelled.
*   Increased damage and healing maximum spam thresholds to 100,000.
*   Added default trigger for Ultimatum.
*   Updated TOC for Patch 5.3

5.7.128

*   Updated parser to support the new amount parameter on applied and removed auras. Thanks to pelf for the patch.

5.7.127

*   Fixed issue introduced with Patch 5.2 where dispels were showing the skill performing the dispel rather than the one being dispelled.

5.7.126

*   Modified skill ID for Taste For Blood to reflect the new value.
*   Updated TOC for Patch 5.2.

5.7.125

*   Updated TOC for Patch 5.1.

5.7.124

*   Fixed issue introduced with Monk Chi changes in Patch 5.1.

5.7.123

*   Fixed an issue where certain power types such as Sha Power and Alternate Power were causing errors.

5.7.122

*   Added new Shadow Orbs Change and Shadow Orbs Full events that act similar to combo points.
*   Removed shadow orbs from standard power gains (e.g. +1 Shadow Orbs) since it is now treated similar to combo points.
*   Removed Shadow Orbs x3 default trigger due to the new Shadow Orbs Full event.
*   Fixed issue where the shorten numbers and group by thousands options were not being applied to overkill amounts.
*   Added default trigger for Blindside.
*   Removed extra exclamation point from druid berserking default trigger.
*   Added missing Italian localization files.

5.7.119

*   Fixed issue where combo point gains and full combo points were not being displayed (reported by dondasch).

5.7.118

*   Updated for Patch 5.0.4 / Mists of Pandaria Beta
    *   Monk is now an available class for triggers and class coloring.
    *   Added new Chi Change and Chi Full events that act similar to combo points.
    *   Added support for dynamic max chi and holy power.
    *   Removed chi from standard power gains (e.g. +1 Chi) since it is now treated similar to combo points.
    *   Updated supported power types to include Alternate, Dark Force, Chi (Light Force), Shadow Orbs, Burning Embers, and Demonic Fury.
    *   Removed the following triggers since they no longer apply: Counterattack, Eradication, Hot Streak, Impact, Riposte, Viper Sting
    *   Removed the following skills from default suppressions and throttling since they no longer apply: Arcane Empowerment, Desecration, Ferocious Inspiration, Mana Spring
    *   Rewrote code that deals with party and raid members to use the new Blizzard APIs.
    *   Updated "Active Talents" trigger condition to use the new Blizzard API.
    *   Modified remaining existing triggers to work with their new values.
    *   Modified several skill IDs to reflect their new values.
    *   Added default trigger for Vital Mists x5.
    *   Added default trigger for Mana Tea x20.
    *   Added default trigger for Elusive Brew at 5, 10, and 15 stacks.
    *   Added default trigger for Power Guard x3.
    *   Added new events for Alternate Power Gains and Losses so they may be customized.
    *   Added temporary workaround for UnitGUID bug when in a group. Triggers that involve party/raid members will not work currently due to this.
    *   Updated environmental damage handler for environmental type changes.
    *   Updated TOC for Patch 5.0.4.
*   Added new option to shorten large numbers using si suffixes (32765 displays as 33k).
*   Added new option to separate large numbers into digit groups (32765 dispays as 32,765).
*   Fixed taint issues cause by the \_ global variable.
*   Converted class names to use Blizzard provided localizations.
*   Removed old temporary workaround for raid flags added in Patch 4.2.
*   Added Italian localization from Kelhar@Runetotem-EU.

5.6.117

*   Money strings will now show properly on all supported languages.
*   Updated Simplified and Traditional Chinese translations from yleaf.

5.6.113

*   Converted all sounds to .ogg from .mp3.

5.6.112

*   Modified combat event log parser to work with the absorb changes in Patch 4.3.

5.6.111

*   Updated German translations from mojosdojo.
*   Updated Simplified and Traditional Chinese translations from yleaf.
*   Updated TOC for Patch 4.3.

5.6.108

*   Removed item cooldown tracking debug print.

5.6.107

*   Added support for item cooldowns:
    *   Created new event for customizable item cooldown notifications.
    *   Added Item Cooldown Complete to the available trigger events.
    *   Added Item ID and Item Name condition handling for the main trigger events that support them.
    *   Cooldown exclusions now accept skill IDs, item names, and item IDs in addition to skill names.
  
*   Added monochrome, monochrome + thin, and monochrome + thick to available outline font settings for pixel font lovers.
*   Modified the custom font and sound validation routines to work with arbitrary case extensions.
*   Changed custom font validation error message to a more descriptive message when the font can't be set versus the more generic ttf message.

5.5.106

*   Added option to customize color of shadowflame damage.
*   Added option to customize color of frostfire damage.

5.5.105

*   Modified combat event log parsers to work with the changes in Patch 4.2 without extra indirection.
*   Changed Traditional Chinese default font by yleaf.
*   Updated Simplified and Traditional Chinese translations from yleaf.
*   Updated TOC for Patch 4.2.

5.5.100

*   Added logic to detect and merge off-hand strikes with main hand strikes.

5.5.99

*   Removed Happiness as an available power type since it no longer exists as of Patch 4.1.
*   Added logic to handle the changed combat log event format in Patch 4.2 on the PTR without breaking the current version (Blizzard is changing it again).
*   Updated LibStub to the latest version (14 Jan 2011, 1.0.1).
*   Updated CallbackHandler to the latest version (14 Jan 2011, 1.0.7).
*   Updated LibSharedMedia to the latest version (05 Nov 2010, 3.0-4).

5.5.98

*   Fixed handling for the always show quest items option that was broken by Patch 4.0.6 (reported by Judgespear).
*   Modified to play sounds even when game sound effects are disabled as allowed by API changes in Patch 4.0.6 (reported by Retlaw).

5.5.97

*   Modified combat event log parsers to work with the changes in Patch 4.1 (committed by mojosdojo, reported by several others).
*   Updated Russian translations from StingerSoft.
*   Updated German translations from mojosdojo.
*   Updated TOC for Patch 4.1.

5.5.91

*   Added the new pet heal events to the options interface so they may be customized and disabled as intended.
*   Updated Korean translations from chkid.

5.5.89

*   Made several updates to the cooldown tracking system:
    *   Implemented a work around for Blizzard's cooldown bug with dismissed pets. Pet cooldowns should no longer be shown before they are actually finished.
    *   Created new event for customizable pet cooldown notifications.
    *   Added an option to customize the color of the skill name in cooldown events.
    *   Changed Skill Cooldown Complete trigger event to Player Cooldown Complete (only detects player cooldowns).
    *   Added Pet Cooldown Complete to the available trigger events.
    *   Added Skill ID as an available condition for player and pet cooldown triggers.
  
*   Created new events for outgoing pet heals, pet heal crits, pet periodic heals (HoTs), and pet periodic heal (HoT) crits.
*   Efflorescense is now detected and displayed as a pet heal.
*   Added default triggers for Blood Swarm and Shadow Infusion x5.

5.5.88

*   Fixed an issue preventing pet cooldowns from being detected.
*   Added a default trigger for Lava Surge.
*   Updated Korean translations from chkid.

5.5.86

*   Added support for pet cooldowns.
*   Added default triggers for Shadow Orb x3 and Berserk.
*   Added Power Change to the available trigger events.
*   Removed Mana Change, Energy Change, Rage Change, and Runic Power Change trigger events since the underlying events no longer exist (replaced with Power Change).
*   Modified default Low Mana trigger to use the new power change event.
*   Removed Hunters from mana based triggers (Viper Sting, Low Mana).
*   Modified hunter auto shots to be treated like standard melee damage.
*   Health and Power Change triggers will now work with party and raid member Unit IDs.
*   Updated Korean translations from chkid.

5.5.83

*   Fixed an issue that caused an error when moving scroll areas with the mouse.
*   Modified the cooldown tracking system to further support dynamic cooldown resets.
*   Updated the cooldown tracking system to support abilities with the same name that have different cooldown lengths such as Feral Charge.
*   Added new Holy Power Change and Holy Power Full events that act similar to combo points.
*   Removed holy power from standard power gains (e.g. +1 Holy Power) since it is now treated similar to combo points.
*   Updated supported power types to include generic eclipse energy.
*   Added additional logic for detecting Lunar and Solar Eclipse energy gains (e.g. +13 Lunar Energy or +20 Solar Energy).
*   Added default trigger for Shooting Stars.
*   Updated Korean translations from chkid.

5.5.79

*   Updated for Patch 4.0.1 / Cataclysm Pre-launch:
    *   Updated supported power types to include soul shards and holy power.
    *   Modified power change detection logic to use new event.
    *   Removed soul shard created notification since it is now considered a power gain.
    *   Removed "hyper regen" option since there are no longer any skills that utilize it.
    *   Removed the following triggers since they no longer apply: Frostbite
    *   Modified several skill IDs to reflect their new values.
    *   Removed .wav files from the supported sound formats in the custom media sound dialog since WoW no longer supports playing .wav files.
    *   Added support for .ogg files to the custom media sound dialog.

5.4.78

*   Removed default suppressions for Abominable Might and Unleashed Rage since they have been changed to passive auras.
*   Removed default Rampage trigger since it has been changed to a passive aura.
*   Updated Eclipse trigger to two separate triggers to account for Lunar and Solar Eclipse.

5.4.77

*   Updated IDs for Abominable Might and Unleashed Rage to new values introduced in Patch 3.3.3.
*   Removed aura hack since Blizzard fixed the bug with aura applications not reporting to the combat log. This will fix the double notifications.
*   Updated Simplified and Traditional Chinese translations from yleaf.

5.4.75

*   Fixed issue with aura hack where certain aura applications (like Missile Barrage) were not being detected every time.
*   Fixed issue where an error could be thrown regarding a bad argument to bit\_band.

5.4.74

*   Implemented a hack to work around Blizzard's bug with the combat log in Patch 3.3. This will allow most of the default triggers to work until Blizzard fixes the bug.
*   Updated Korean translations from chkid.

5.4.71

*   Fixed font issue that was causing lua errors regarding the :SetFont routine.

5.4.70

*   Added an option to disable regular melee swings from being merged.
*   Added an option to hide the merge trailer that is shown when multiple events are merged.
*   Added Aura Refresh to the available trigger events.
*   Added a default trigger for Predator's Swiftness.
*   Optimized font validation logic to reduce CPU usage.
*   Updated HoT crit events to behave like crits as intended.
*   Changed Desecration from the skill ID removed Patch 3.3 (fixes message regarding removed skill ID 63595).
*   Updated Russian translations from StingerSoft.
*   Updated Simplified and Traditional Chinese translations from yleaf.
*   Updated Korean translations from chkid.
*   Updated TOC for Patch 3.3.

5.4.66

*   Created new events for incoming and outgoing periodic heal (HoT) crits.
*   Lowered the minimum allowed cooldown threshold to 3 seconds. The default value is still 5 seconds.
*   Tweaked the animation event initializion logic to prevent some instances where events could briefly flicker at high framerates.
*   Added a recently fired exception to the default Rune Strike trigger to reduce its spaminess.
*   Updated Korean translations from chkid.

5.4.64

*   Added a new option under spam controls to hide full HoT overheals (enabled by default).
*   Modified the current hide full overheals option to only apply to direct (non periodic) heals.
*   Added new events for incoming and outgoing Deflects.
*   Added Deflect as an available miss type for trigger conditions.
*   Modified options module load logic to avoid issue with Blizzard's load on demand routine.
*   Modified TOC to provide assistance to Minion (automatic updater).

5.4.63

*   Modified heal events to use the new combat log format in patch 3.2. This fixes the issue with all heals showing as crits.
*   Added absorb amount as an available condition to heal based triggers.
*   Updated German translations from Archiv.
*   Updated French translations from Devfool.
*   Updated Korean translations from chkid.
*   Updated TOC for Patch 3.2.

5.4.61

*   Added Aura Broken to the available trigger events.
*   Fixed issue with guardians being treated as the player instead of a pet.
*   Added logic to prevent potential errors due to load ordering.
*   Updated Russian translations from StingerSoft.

5.4.59

*   Changed the interaction with Blizzard's default FCT (Floating Combat Text) and damage/healing displays:
    *   The default FCT and damage/healing displays are no longer manually controlled. The settings in the game's Interface Options configuration must be used to control them instead.
    *   The Game Damage and Game Healing checkboxes have been removed from the General tab since they are no longer used.
  
*   Damage done to structures from siege vehicles (and other sources like explosives) will now display.
*   Vehicles are now treated as the player themselves instead of as their pet for incoming and outgoing damage.
*   Added default suppressions for Desecration, Abominable Might, and Unleashed Rage to prevent the spam they generate.
*   Made a minor optimization to the main animation logic.
*   Innervate will no longer activate "Hyper regen" mode since the mana gains from it are now reported in the combat log.
*   ALL mana gains mode will now set the mana gain skill to Unknown.
*   Hyper regen mode will now attribute the gains to the skill that activated it.

5.4.58

*   Added support for the CUSTOM\_CLASS\_COLORS standard.
*   Implemented logic to ensure classes are always known for opponents in arenas.
*   Tweaked class identification code to fix an issue where classes weren't known when they should have been.
*   Fixed issue that caused an error when using the %r event code on health and power change events.
*   Updated Simplified and Traditional Chinese translations from yleaf.
*   Updated Korean translations from chkid.

5.4.55

*   Implemented capability to color unit names according to their class including customization options:
    *   Choose whether or not to enable class coloring on a global basis.
    *   Control color and enabled state for each individual class.
    *   Uses standard class colors defined by Blizzard by default.
    *   Applies to class names shown in triggers as well.
  
*   Made minor optimizations to the merging system and event formatting.
*   Added overkill amounts to available partial effects, but they are disabled by default.
*   Added a default trigger for hostile player PvP trinket usage including who used it. It is set to only show in arenas by default.
*   Changed the event code for killing blows to %n so it works correctly with class coloring.
*   Made the %n event code available for the built-in outgoing dispels event.
*   Fixed an issue where certain new text could briefly appear in the wrong spot when initially displayed on slower PCs.
*   The exclusive skill icons option will no longer be ignored when a scroll area has its icon disabled.
*   Font files that have been removed but are still referenced will now correctly use the default font instead of resulting in errors.
*   Updated Simplified and Traditional Chinese translations from yleaf.
*   Updated Korean translations from chkid.

5.4.52

*   Added the ability to customize the trailer message shown for partial effects.
*   There is now an option to disable icons for each scroll area.
*   Added an option to hide heals that have an effective heal amount of zero (full overheals).
*   Modified cast success and summon trigger events to include recipient conditions. Unfortunately cast start events do not report recipient information, so it is not available for them.
*   Increased the damage, healing, and power thresholds significantly to keep up with inflation.
*   Implemented internal throttling for identical enemy buff gains to reduce spam on fights like Yogg-Saron.
*   Added a preview icon to the scroll areas preview feature for better visual representation of icon settings.
*   Updated Russian translations from StingerSoft.

5.4.49

*   Reworked the cooldown tracking system with dynamic updates in mind:
    *   Dynamically adjusted cooldowns such as glyphed Guardian Spirit will now work correctly.
    *   Cooldowns for skills that are unlearned will be automatically removed (dual spec).
    *   Death Knight cooldowns will now consider rune cooldowns. For example, consider Rune Tap only has 4 seconds remaining, but a blood rune won't be available for 6 seconds. The notification won't display until the rune is available.
    *   The small "time drift" that could occur on long cooldowns should no longer occur.
    *   Removed old pestilence cooldown information.
  
*   Added default trigger for Decimate.
*   Added default trigger for Lock and Load.
*   Modified item exclusions to include quest items.
*   Updated Korean translations from chkid.
*   Updated Simplified and Traditional Chinese translations from yleaf.

5.4.44

*   Created new events for buff and debuff stacks. They only apply when there are 2 or more auras stacked.
*   Changed default loot message to include the amount of the item looted in addition to the total in inventory.
*   Modified Impact trigger to use the new mechanics.
*   Added default trigger for Eradication.
*   Fixed issue with various fonts not working properly.
*   Updated Simplified and Traditional Chinese translations from yleaf.

5.4.42

*   Created an in-game editor for managing custom media:
    *   Entries will persist between game sessions and version upgrades.
    *   Entries are not tied to profiles meaning they will persist through profile resets.
    *   Font entries appear in the font they reference to provide a quick preview of the custom fonts that have been added.
    *   Sound entries provide a play button to preview/test them.
    *   Modified font handling to ensure invalid paths do not throw errors.
    *   The old MSBTFonts.lua and MSBTSounds.lua files have been removed in favor of this new system.
    *   Remember that the media files must already exist **before** WoW is started or they can't be used.
  
*   Added a new loot alerting system with several options:
    *   Provides a total count of how many of the looted item are now in inventory and, optionally, how many items were looted (via %a event code).
    *   Looted items are colored according to their quality (grey, green, etc)
    *   Only display items of selected qualities.
    *   Always display specific items by name.
    *   Always suppress specific items by name.
    *   Always show quest items regardless of exclusions.(subject to Blizzard having the item marked as a quest item).
  
*   Created new events for incoming and outgoing periodic damage (DoT) crits.
*   Added an option to control whether or not the text shadowing effect introduced in version 5.3.37 is applied.
*   Outgoing dispels will now display debuffs cleansed from friendly units as well as buffs from enemy units.
*   Aura gains now show how many are stacked by default. You can remove the %a event code from the respective events if you don't want to see this information.
*   Added Active Talents as an available trigger exception.
*   The blink buff gain and loss events are now ignored.
*   Disabling a scroll area will now ensure all events destined for it are suppressed regardless of their source.
*   Removed references to skills and triggers that are not available as of Patch 3.1.
*   Updated TOC for Patch 3.1.

5.3.41

*   Added missing Korean localization files.
*   Updated Russian translations from StingerSoft.
*   Updated Simplified and Traditional Chinese translations from yleaf.

5.3.37

*   Added an option to specify on which side skill icons show per scroll area.
*   Implemented a shadow offset and changed the default outline to none to improve font crispness.
*   Set the default power throttling duration to 3 seconds to help reduce spam from power returns.
*   Modified reordering code to fix an issue with Korean client global strings.
*   Add Korean localization from Slowhand, Fenlis, and chkid.

5.3.36

*   Updated to work with Patch 3.1 on the PTR. There will be some triggers and skills that will need to be removed once 3.1 goes live.
*   Modified the channeled AoE aura suppression feature to only ignore the aura if it was caused by the player casting it.
*   Updated Simplified and Traditional Chinese translations from yleaf.

5.3.33

*   Implemented a work around for Blizzard's cooldown bug with Death Knights and runes. Only abilities with actual cooldowns should now be shown.
*   Created a default suppression for Ferocious Inspiration to remove the spam it causes.
*   Added logic to ignore buff gain and loss events created by channeled AoE skills (Blizzard, Volley, etc)
*   Added new events for incoming and outgoing damage shields (thorns, retribution aura, etc).
*   Added overkill amount as an available condition to damage based triggers.
*   Added Buff Inactive and In Combat as available trigger exceptions.
*   Killing Blows should no longer be shown for Death Knight ghoul sacrifices.
*   Modified media registration routines to ignore erroneous parameters to prevent issues with other mods.
*   Tweaked internal merging and animation delays to help performance in heavy AoE situations.
*   Updated French translations from Devfool.
*   Updated Simplified and Traditional Chinese translations from yleaf.

5.3.32

*   Fixed Rune Strike trigger.

5.3.31

*   Added default trigger for Kill Shot.
*   Added default trigger for Rune Strike.
*   More Russian translation updates from StingerSoft.

5.3.29

*   Added recently fired exceptions to some triggers like Fingers of Frost to cut down their spaminess during AoE.
*   Resisted dispel effects will now show the icon of the dispelled skill instead of the skill doing the dispelling.
*   Added code to prevent other mods from registering invalid media names.
*   Added a few default triggers for Death Knights.
*   Russian translation update.

5.3.26

*   Modified the angled animation style to maintain consistent movement speed.
*   The reflect event will no longer show the %a event code.
*   Added default trigger for The Art of War.
*   Fixed issue with animation speed not scaling certain styles correctly.

5.3.25

*   Modified the internal media handling to avoid issues induced by other mods via LibSharedMedia.
*   Reworked the animation system to help alleviate some "jerkiness" due to rounding.
*   Added an angled animation style with customizable directions and behaviors.
*   Made some minor optimizations in substitution code handling.
*   Removed Mongoose Bite and Kill Command triggers since they no longer apply.
*   Added default triggers for Sudden Death and Taste for Blood.

5.3.24

*   Updated for Patch 3.0.1 / Wrath of the Lich King Beta.
    *   Added several default triggers for new abliities of various classes.
    *   Updated supported power types to include runes and runic power.
    *   Added support for new damage types.
    *   Added coloring for frostfire damage.
    *   Death Knight is now an available class for triggers.
    *   Runic Power Change and Rune Cooldown are now available main events for triggers.
    *   Added throttling for heals from Blood Presence.
    *   Added the amount absorbed for fully absorbed events with damage color capability.
    *   Modified all partial effects to use the same bracket style as overheals.
    *   Updated combo point handling to work with WotLK.
    *   Modified power gains from leeches to show the correct amount gained instead of the amount leeched.
  
*   Performance enhancements:
    *   Removed delays from the animation system that should make the animations a little smoother on fast systems.
    *   Events that are capable of being merged will now appear more quickly than previously.
    *   Made some minor optimizations in substitution code handling.
  
*   Realm names are no longer shown as a part of name based substitutions for cross-realm players.
*   Rewrote media handling system to provide native Shared Media support.
*   Physical damage coloring is now ignored for outgoing skills that are not "auto attacks."
*   The temporary icon (the little face) will no longer be shown.
*   Zephyr font removed since it doesn't support some glyphs.

5.2.14

*   The hostile condition check for health and power changes will now function properly.
*   The damage amount of hunter autoshots will now be colored according to the physical damage color if it is enabled (White by default).
*   Added Russian localization.

5.2.11

*   Fixed issue with triggers that set a unit id to all party members.

5.2.10

*   Added a button to test the selected sound in the event settings dialog.
*   Dark Pact and other power leech events will now correctly display the amount of mana leeched.
*   Added missing Traditional Chinese localization files.

5.2.9

*   Rewrote the core of the event parser to reduce its CPU usage by about 60%.
*   The trigger system was completely redesigned with the main focus on flexibility.
    *   Triggers now make extensive use of "short-circuiting" to cut down the number of tests needed thereby increasing performance.
    *   Anything that has a patch 2.4 style combat log entry (COMBAT\_LOG\_EVENT\_UNFILTERED) can now be used for a trigger.
    *   The number of available conditions per main event has been substantially increased.
    *   Each parameter for a main event type can now specify various relationships.
    *   Parameters involving strings like skill names and unit names can now choose between an exact match or a search pattern in most cases.
    *   Added a new main event for skill cooldown completions.
  
*   Full paths may now be entered for sounds. This includes path to sound files internal to WoW.
*   Added Traditional Chinese localization.
*   Moved font definitions to localization files so they can be unique per language. MSBTFonts.lua can still be used to add custom fonts.
*   Updated spell dispel/stolen events to the new values implemented by Blizzard in Patch 2.4.3.

5.13

*   The threshold based triggers such as "Low Mana" and "Low Health" will once again display the current amount.

5.12

*   Fixed the error when looting money induced in patch 2.4.2.
*   Fixed the erroneous "Low Mana" warnings when in druid forms.

5.11

*   Redesigned the trigger system to work with the new combat log mechanics and improve flexibility:
    *   The old main conditions have been replaced with main events that can have several conditions for greater control over things such as affected units (target, focus, etc), applications, etc.
    *   The old secondary conditions has been replaced with exceptions. Exceptions will cause the trigger not to fire when they are true. In addition, most exceptions has a "reverse logic" option that causes them to behave as their opposite for high flexibility.
    *   Triggers now try to choose an appropriate icon based on the main event that fired it. It is still possible to specify an icon that will override the default.
    *   All of the default triggers will now work on non-English clients without the need for localization.
    *   Any additional triggers you may have created in previous versions will have to be recreated under the new system.
    *   Added a default trigger for Viper Sting.
    *   Added the default clearcasting trigger to druids.
  
*   Skills like "Mangle (Bear)()" will now be displayed as "Mangle" in the cooldown area.
*   Animations may now be as slow as 20% of normal instead of the previous 50%.
*   Scroll areas can now have a minimum height of 50 down from 100.
*   Increased the allowed font size range to 4-38.
*   Threshold triggers will no longer misfire when shapeshifting.
*   Soul Shard gains will now be displayed again.
*   The %t event type will no longer throw an error.
*   Added a button to the AddOns tab of Blizzard's Interface Options to launch MSBT's options.

5.1

*   The optional icons module is no longer required. This is a significant memory savings for those previously using the module.
*   Unfortunately, the ability to add and customize triggers is disabled for this release while the system is rewritten.
*   Rewrote the parser to work with the new combat log mechanics implemented in Patch 2.4. Since manually parsing text strings is no longer required, things like pets with the same name as party/raid members will no longer cause confusion. There also should no longer be problems with non-English clients that had strange parsing issues due to ambiguous strings.
*   Load up memory usage is now around 221 KiB.
*   Damage from spell reflects will now be shown to the player who reflected it as if they did the damage.
*   The horizontal animation style now has an alternating direction option.
*   Added new events for outgoing (offensive) player and pet dispels.
*   Internal filtering for identical monster emotes has been added to reduce potential spam.
*   Only one five combo point notification will now be shown per combo point cycle.
*   Overhealing will now show on heals that have been excluded from merging.
*   Fixed an issue regarding cooldowns not being displayed for certain skills like Mangle (Bear).
*   Added Simplified Chinese localization. Thanks to elafor and hscui for their work.
*   Updated TOC for Patch 2.4.

5.03

*   Updated LibStub in MSBTIcons to resolve incompatibilities with a newer library version. This should clear up some issues with other mod compatibility.
*   Made icons for triggers obey the enable/disable skill icons option.
*   Updated for Patch 2.3.

5.02

*   Modified the sound system to allow custom registrations for easier sound selection.
*   Triggers may now specify a skill name to use for displaying an icon.
*   Added suitable icons to most of the default triggers.
*   Added parsing for mana gains from sources like Mana Spring totems now that they can be suppressed, if desired.
*   Mana gains during Innervate are now shown if the "Hyper Regen" option is set.
*   Damage from totems and other miscellaneous "pets" will now be displayed.
*   Changed the minimum scroll area width to 10.
*   Fixed a problem that was causing all periodic enemy heals and power gains to be shown instead of only buff gains.
*   Fixed an issue where delayed cooldowns such as combustion were completing before they should.

5.01

*   DoTs and HoTs may now have independent throttle times.
*   Power gains can now be throttled and there is a default Vampiric Touch throttle entry.
*   Power gains now have icons when possible.
*   Added a "Move All" button to the Events tab to allow the whole category to be moved to a new scroll area quickly.
*   Added some logic to counteract ill behaved mods such as Recount and SW\_Stats modifying global strings.
*   Fixed some issues with the options interface not saving certain fields properly.
*   Made search pattern triggers also check secondary conditions to match the behavior of the other condition types.
*   Updated the MSBTIcons module .toc file to prevent certain cases where it wasn't being loaded in the correct order (Thanks dylanm).

5.0

*   Complete code rewrite to further reduce memory usage and CPU utilization. Blizzard's addition of memory and CPU tracking tools to the API were used to help achieve this. The CPU utilization is about 55% less, and the load up memory usage is now around 258 KiB.
*   Redesigned the profile system to use a full master/diff approach. This leads to a substantial memory savings when using multiple profiles. It also adds the benefit of allowing future changes to defaults to take place without having to completely reset user profiles.
*   The options interface was streamlined and rewritten using pure lua. All the tabs and popup frames are now dynamically created only when needed. The options are still load on demand and use no resources when not loaded.
*   Created a new set of spam controls:
    *   Show ALL power gains WARNING: This can and will spam you!
    *   Show hyper regen (mana gains during Evocation and Spirit Tap)
    *   Thresholds for Healing, Damage, and Power Gains
    *   Skill name substitution
    *   Skill suppression (e.g. Vampiric Embrace)
    *   Skill abbreviation option with new %sl event code to override at the event level
    *   Independent throttle times per skill
    *   Merge exclusion list (e.g. avoid merging mutilate)
*   New font opacity setting that follows the same inheritance mechanics as the other font settings, so each individual scroll area and event can have a custom opacity.
*   Added some "high level" controls to the options interface such as a "Toggle All" button to quickly toggle the enable state of all events in the selected category. This allows you to disable all incoming pet events with one click for example. Another example is a "Disable Skill Names" checkbox which quickly allows you to stop all skill names from being displayed without having to modify every single event and remove the %s.
*   Added built-in customizable cooldown notifications.
*   Crits are now separate events so they can be individually controlled.
*   Each scroll area may now have its own independent animation speed.
*   Scroll areas now have a customizable width that the animation styles obey when it makes sense.
*   New horizontal and static animation styles.
*   Created a new default scroll area using the new static animation style.
*   Implemented behaviors in the animation system which allow more customization of animation styles.
*   Added a new selectable behavior (Normal) to the Pow sticky animation style that will not perform the jiggle effect.
*   Added enemy buff gain and monster emote events (spell alert).
*   New money gains notification event.
*   There is now a full set of incoming pet events.
*   Added outgoing pet DoTs.
*   Every event can now be assigned a custom sound. (e.g. full combo points)
*   Several trigger conditions such as Self Buff Gains can now have multiple entries per trigger.
*   Added a debuff application number secondary trigger condition.
*   Added a spell usable secondary trigger condition.
*   Added several new fonts.
*   Added an optional skill icons module.
*   Made some minor tweaks to the default display and throttle settings to improve readability.
*   Fixed a few parsing issues.

4.13

*   Added temporary fix for PlaySoundFile() bug in Patch 2.2.2.
*   Updated for Patch 2.2.

4.12

*   Added the option to disable/enable Blizzard's new built-in healing display above the target's head.
*   Updated for Patch 2.1.

4.11

*   Fixed the issue where crits were being improperly displayed on some non-English clients.
*   Modified the outgoing crit/block/dodge/parry trigger conditions to only apply to the player and not any pets.
*   Added a "Trigger Cooldown" secondary condition.

4.1

*   Rewrote the trigger system to allow for multiple conditions while maintaining efficiency. In addition several commonly requested triggers were added.
*   Triggers may now have a custom sound assigned to them.
*   Added parsing for some new TBC patterns that will fix a few issues where certain events were not showing up.
*   Made several parsing optimizations.
*   Created an event for incoming and outgoing Spell Interrupts.
*   Added Shadowmend to the list of throttled HoTs.

4.03

*   Recharacterized some damage based spells into DoTs so they will now follow the throttling mechanics.
*   Added damage types to environmental damage so it will now have the damage type colors applied.
*   Updated for Patch 2.0.3 / Burning Crusade.

4.02

*   Fixed parsing order error with Foreign languages which resolves a lot of issues on foreign clients with substitution codes showing up instead of the actual data.
*   The soul shard notification event should now work again.
*   The mana gained form the warlock Dark Pact talent will now be displayed.
*   Recharacterized healing from some damage based spells (most notably Vampiric Embrace) into HoTs so they will now follow the throttling mechanics. Basically this means those spells should no longer spam you with healing if you have HoT and DoT throttling enabled (it's on by default).
*   Added parsing for damage taken from the tornado in the arenas.
*   Added French localization.
*   Added more German localization.

4.01

*   Fixed the problem induced by the 2.0 patch where wand damage was not showing up.

4.0

*   Complete code rewrite for even better performance and features.
*   Major Optimizations:
    *   Rewrote the combat parsing engine to significantly increase performance and lower the memory footprint.
    *   Redesigned the suppression system to use a hash table searching algorithm so that any number of suppressions may be added without any appreciable slowdown.
    *   Optimized the default profile handling. Due to the large number of options, the default profile table takes up a decent chunk of memory (around 90 KiB). In the previous versions, the table was always memory resident - even when it wasn't needed. It is now created dynamically only when it's needed, which is the first time you load a new version of the mod or reset a profile to its defaults.
    *   Redesigned the underlying options tables such that shared information amongst the events is only stored once instead of separately for each event. This saves quite a bit of memory, especially when there are multiple profiles.
    *   Created a single pool of dynamically created font strings to be shared by the various scroll areas. Previously a set number of font strings were created for every scroll area.
    *   Load up memory usage is now around 450 KiB.
  
*   Minor Optimizations:
    *   Trigger system will no longer listen for events that there are no triggers for. Previously it received the same events the mod was already parsing and ignored the ones with no triggers.
    *   Reduced the amount of information that needs to be passed around to lower memory usage during operation.
  
*   Rewrote the animation code to work using scaled timing. Previously the animation was created by moving the text a set amount of pixels each update. This had the effect of causing the animation speed to vary greatly depending on system performance. The animations should now keep the same speed regardless of large performance hits, such as those incurred while recording a video or during extreme lag.
*   Each character will now load the last selected profile for that character by default.
*   Changed the default font to Porky, which has glyphs for most common German, French, and Spanish special characters. In addition, most of the fonts were replaced with new versions that support them as well. However, the old Adventure font is still available for those who want to use it.
*   Added an option (enabled by default) to throttle DoTs and HoTs so that only one event for each ability will be displayed within the time period specified (2.5 seconds by default). Any additional DoT/HoT abilities that occur while being throttled are merged into one event to be shown once the throttle period has passed. This will reduce the spam when you have HoTs and/or DoTs on multiple targets.
*   Made scroll areas dynamically creatable and made events/triggers assignable to them.
*   Ability/Spell damage amounts now use a custom color according to their damage type by default. The rest of the message will still show up with the event's selected color. This behavior can be disabled.
*   Partial effects (absorbs, resists, glancing, crushing, overheals, etc) can now be individually enabled, disabled, and color coded.
*   Separated Debuff and Item Buff Fades from Buff Fades into new notification events. Totem buffs are now also handled as buff gains and fades.
*   Added an Extra Attacks notification event which will give notifications for Windfury, Thrash, Sword Spec, etc.
*   Added a Soul Shard Created notification event.
*   Overhauled the interface to include the new features.
*   Added a font registration function so other mod developers can choose to display their custom messages in their own font.
*   Added an animation style registration function so other mod developers can easily provide custom animation styles for MSBT.
*   Provided an additional file named API.html that is a reference for the publicly accessible functions that other mod developers can use to display messages through MSBT and register custom animation styles.

3.11

*   Fixed the bug where in certain circumstances the trigger interface would give an error when trying to setup a new search pattern trigger.
*   Made newly created triggers inherit all font settings instead of specifying a font size by default.

3.1

*   Added support for power gains to yourself from other people.
*   Increased the number of available event types for the trigger system to allow for greater flexibility. Due to the way the trigger system is designed this will not add much overhead since triggers are only parsed against the selected event types.
*   Alphabetized the list of available trigger events to make finding the one you want easier.
*   Removed the default Blessing/Judgement of Wisdom suppression. The user can choose to add one in for it if they prefer.

3.01

*   Fixed the bug where you could only add one suppression and adding a new one was overwriting it.

3.0

*   Implemented a low overhead trigger system. [See documentation above](#TriggerSystem).
*   Implemented a suppression system that allows you to suppress particular messages you don't want to see.
*   Made significant changes to the scroll area settings interface. The new interface shows all three scroll areas at the same time. Each scroll area is now titled with its coordinates and there are editboxes to enter specific coordinates in addition to being able to drag the scroll areas around.
*   Changed the core animation routines to use function pointers in order to eliminate the need for a ton of conditional testing. Previously, every time the animation routine was called (typically 60-70 times per second for every scrolling item), the animation style and scroll direction were checked to calculate how to move the text. Now those items are only checked during the initial animation object setup phase. This should help performance on slower PCs.
*   Added the command "/msbt search pattern" to enable an event searching mode which helps identify event types used in the trigger system. See documentation above for more info.
*   Moved the Low Health, Low Mana, and Execute events into the trigger system. Due to this change the Low Mana and Execute triggers will no longer waste resources checking on classes that don't use mana or have an execute ability. Also moving them into the trigger system made the thresholds at which to show the Low Health, and Low Mana warnings selectable.
*   Made a few minor code performance tweaks to the animation setup "pipeline."
*   Added Killing Blow notification events for both players and NPCs.
*   Added crushing and glancing hit partial effects.
*   The font settings frame can now be moved.
*   Fixed a bug where messages added via the MikSBT.DisplayMessage function were being shown even if the scroll area was set to not show messages.

2.11

*   Disabled Blizzard's new floating text in Patch 1.12 when MSBT is enabled.
*   Updated for Patch 1.12.

2.1

*   Reduced memory usage a little by removing the underlying tables used to store crit information for events that can never be crits. (Down to around 477 KiB)
*   To go along with the above change, the font settings interface for events was reworked so that you can no longer set crit information for events that don't support them.
*   Added a title at the top of the font settings frame to help distinguish what is being modified.
*   Added an Experience Gains notification event.
*   Added the capability for notifications to be displayed "sticky" style.
*   Fixed the bug induced by patch 1.11 where reputation gains and losses weren't being displayed.

2.0

*   MAJOR optimization code rewrite:
    *   Made options load on demand to significantly reduce memory usage and start up time.
    *   Implemented a table recycling system to reuse tables created during combat instead of creating new ones and allowing them to be garbage collected. The net effect is that a ton of garbage collection churn has been eliminated. Thanks go to kergoth and Wobin for tips on how to achieve this.
    *   The combat event parser has been changed to reuse one single table for storing the results of the parsed data.
    *   Streamlined the combat event to screen animation "pipeline."
    *   Namespaced all code to reduce global namespace pollution.
    *   Load up KiB Usage in v1.03 was approximately 1050 KiB. This has been reduced to around 488 KiB. In addition, due to the table recycling system, memory usage during operation is much more consistent instead of continuously increasing until the next garbage collection cycle.
  
*   Added a function to allow messages to be easily displayed through MSBT from external sources.  
    This function is MikSBT.DisplayMessage and is detailed in the included API.html file.
*   Added the command "/msbt stats" to report statistics about the table recycling system.
*   Changed the functionality of AoE merges so that the name reported is "Multiple" instead of the last affected unit.
*   Added the option to disable "game damage" instead of just always doing it.
*   Added the option to disable "sticky crits."
*   Added Execute/Hammer of Wrath notification event.
*   Separated Heals over time (HoTs) and Damage over time (DoTs) into their own events.
*   Added the option to display overhealing.
*   Fixed a bug where crits were not being recognized in non-English clients.

1.03

*   Fixed a bug where options set with a checkbox were not being properly saved on logout.

1.02

*   Fixed a bug where the global string parser wasn't appropriately accounting for the argument order of non-English clients.

1.01

*   Updated for Patch 1.11.

1.0

*   Initial version.

Credits

[Return to TOC](#TOC)  
  

Thanks to:

*   Grayhoof, the author of SCT, for the original mod which inspired this mod.
*   Kergoth and Wobin for their suggestions on optimizations via reduced GC churn and namespacing tips.
*   Farook, Archiv, and Mojosdojo for the German localizations.
*   Calthas and Devfool for the French localizations.
*   Hscui, Netcookies, and yleaf for the Simplified Chinese localizations.
*   Whitepaw and yleaf for the Traditional Chinese localizations.
*   StingerSoft for the Russian localizations.
*   Slowhand, Fenlis, and chkid for the Korean localizations.
*   Kelhar@Runetotem-EU for the Italian localizations.