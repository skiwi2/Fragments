# Fragments
An unique Trading Card Game.

# Rules
This section will cover all the rules and general gameplay.

## Overview
This game is played between two players with as goal to get the opponents life to zero. Each player needs to make a deck of at least 90 cards, there will be a select number of cards available for free when you start and it is possible to acquire more cards through Booster Packs.

## Cards
There are several types of cards in this game and there is a rarity associated with every card.

### Rarity
A card can be a Common, Uncommon or Rare. The rarity does not effect anything else than the complexity of the card.

### Types of cards
All cards have the following attributes:
 - Name
 - Image
 - Resource Cost
 - Rarity
 - Card Text
 - Flavor Text

#### Resource
A card that can be used to gain resources that are refilled at the end of every turn. You can now play cards that cost resources. A common card text you will see on resource cards is the ability to add an object to a creature slot. Resource cards may only be played once every turn.

#### Creature
A card that can be used to combat other creatures and to deal damage to the opponent directly. It has the following extra attributes:
 - Attack Power
 - Health
 - Range

Creatures always consist of multiple fragments, each fragment has their own name and amounts of Attack Power, Health and Range. The sum of Attack Power of all fragments should add up to the Attack Power on the creature, the same holds for Health and Range. The fragments play a big role in combat.

#### Spell
A card that is used to change the state of the board, this can only be used on your turn.

#### Direct Spell
A card that is used to have a direct effect on the board, this can be used when the window to play Direct Spells is up.

#### Permanent
A card that effects the state of the board permanently, until it is destroyed.

## Gameplay
This section will explain how the game is played.

### Basic concepts
Each of the following concepts exist one for every player unless stated otherwise.

#### Player
The player is the one that the opponent needs to defeat, he starts with 10000 Health and is defeated when it reaches zero.

#### Deck
The pile of cards a player can draw from. Upon entering the game this needs to consist of at least 90 cards. Cards in the deck should never be visible to any player.

#### Hand
The cards which you can play if you are allowed to do so.

#### Graveyard
The pile of cards which are no longer in play.

#### Void
The cards that can under no circumstances be returned to the current match.

#### Field
The region where the combat will happen. The field consists of 9 Creature Slots that are horizontally laid next to each other. The slots can have enchantments (buffs or debuffs) applied to them which will effect a creature if it is placed in that slot.

Another concept related to the field is distance, this is best illustrated with an illustration.

<table>
  <tr>
    <td>&nbsp;</td>
    <td>&nbsp;</td>
    <td>&nbsp;</td>
    <td>&nbsp;</td>
    <td>A</td>
    <td>&nbsp;</td>
    <td>&nbsp;</td>
    <td>&nbsp;</td>
    <td>&nbsp;</td>
  </tr>
  <tr>
    <td>5</td>
    <td>4</td>
    <td>3</td>
    <td>2</td>
    <td>1</td>
    <td>2</td>
    <td>3</td>
    <td>4</td>
    <td>5</td>
  </tr>
</table>

If you look at slot A, then the distance to the directly opposite slot is 1, and you add one for every horizontal slot you encounter.

The field has a maximum of 9 slots, when a new creature enters the field when it is full, then all card text will still resolve, but it will be placed in the Reserves section of the field. Creatures in Reserves cannot enter combat. When a slot becomes available, then the creature that entered the Reserves first, will enter that slot immediately.

Slots can have effects on them, which are represented as objects having at least 1 Health, during Combat Resolution the slot entity will always be attacked before the creature gets attacked.

### Detailed gameplay
The game is played in turns, where each turn consists of the following phases. In some turns you will not be able to play cards and you can only play cards on your opponents turn on some occasions.

When playing a card the opponent will always have a 5 second time window in which he can cast Direct Spells.

#### Draw Phase
You draw one card from your deck into your hand.

#### Event Phase
Random events may be triggered, these events effect all players.

#### Upkeep Phase
Effects that trigger at the start of the turn are triggered.

#### Main Phase 1
You can play any card that is eligible.

#### Combat Phase
The combat phase consists of the following steps:

 - You select with which creatures you want to attack the opponent.
 - The opponent can choose with which non-exhausted creatures to block, they need to be in range of the attacking creature.
 - The opponent gets a 5 second time window in which he can cast Direct Spells.
 - Combat is resolved, see the section Combat resolution for the details.
 - If a creature is not blocked, then it will deal damage equal to its Attack Power to the opponent.
 - The creatures Attack Power, Health and Range are calculated again based on the remaining fragments.
 - All creatures with zero Health will be removed and put in the Graveyard.
 - All attacking creatures enter an exhausted state.

##### Combat resolution
In combat, both the attacker and defender simultaneously deal damage equal to their Attack Power to the Health of the defender. In this section you thus have both the original attacker attacking the original defender, and the original defender attacking the original attacker.

If an object is present on the slot, which has Attack Power, Health and Range values just like any other fragment, then it gets targeted first during the combat resolution.

The attacker will deal damage equal to its Attack Power to a randomly chosen fragment with the most Health of the defender. If the Health of the fragment reaches zero, then it is destroyed and this step will be repeated with as new Attack Power the current Attack Power minus the Health of the fragment that just got destroyed.

#### Main Phase 2
You can play any card that is eligible.

#### End Phase
Effects that trigger at the end of the turn are triggered. The Health of all creatures is reset to their initial Health.

### Random events
Every turn random events can be started. Their effect is unknown to both players and can be assumed to increase as the game progresses. There will be a timer and a progress bar visible to both players.

#### Timer
The timer will indicate in how many turns the random event will take place.

#### Progress bar
The progress bar has a set end and players may choose to fill this progress bar. It can be filled by sacrificing Creatures, Slots, Cards (from Hand, Deck and Graveyard) and Player Health. All cards sacrificed this way will be voided. If the progress bar is full, then the random event will not take place.

## Example cards
In this section some example cards will be listed, themed in a fantasy world where there are different races *and* robots.

### Fresh blood
<table>
  <tr><td>Name</td><td>Fresh blood</td></tr>
  <tr><td>Type</td><td>Resource</td></tr>
  <tr><td>Rarity</td><td>Common</td></tr>
  <tr><td>Card Text</td><td>Gives the player 1 Blood Resource. Add a 25 Health object with as effect give +50 Health every turn to a Creature Slot.</td></tr>
</table>

### Cast iron
<table>
  <tr><td>Name</td><td>Cast iron</td></tr>
  <tr><td>Type</td><td>Resource</td></tr>
  <tr><td>Rarity</td><td>Common</td></tr>
  <tr><td>Card Text</td><td>Gives the player 1 Iron Resource. Add a 200 Health object to a Creature Slot.</td></tr>
</table>

### Lancer Orc
<table>
  <tr><td>Name</td><td>Lancer Orc</td></tr>
  <tr><td>Type</td><td>Creature</td></tr>
  <tr><td>Rarity</td><td>Common</td></tr>
  <tr><td>Cost</td><td>1 Blood</td></tr>
  <tr><td>Attack Power</td><td>200</td></tr>
  <tr><td>Health</td><td>100</td></tr>
  <tr><td>Range</td><td>2</td></tr>
  <tr><td>Fragment 1</td><td>Orc: 100 Attack Power, 100 Health, 1 Range</td></tr>
  <tr><td>Fragment 2</td><td>Lance: 100 Attack Power, 1 Range</td></tr>
</table>

### Bear
<table>
  <tr><td>Name</td><td>Bear</td></tr>
  <tr><td>Type</td><td>Creature</td></tr>
  <tr><td>Rarity</td><td>Common</td></tr>
  <tr><td>Cost</td><td>1 Blood, 1 Any-kind</td></tr>
  <tr><td>Attack Power</td><td>225</td></tr>
  <tr><td>Health</td><td>200</td></tr>
  <tr><td>Range</td><td>1</td></tr>
  <tr><td>Fragment 1</td><td>Head: 100 Attack Power, 50 Health</td></tr>
  <tr><td>Fragment 2</td><td>Body: 100 Health</td></tr>
  <tr><td>Fragment 3</td><td>Legs: 125 Attack Power, 50 Health, 1 Range</td></tr>
</table>

### Mechanized Bear
<table>
  <tr><td>Name</td><td>Mechanized Bear</td></tr>
  <tr><td>Type</td><td>Creature</td></tr>
  <tr><td>Rarity</td><td>Common</td></tr>
  <tr><td>Cost</td><td>1 Blood, 1 Iron, 1 Any-kind</td></tr>
  <tr><td>Attack Power</td><td>300</td></tr>
  <tr><td>Health</td><td>300</td></tr>
  <tr><td>Range</td><td>3</td></tr>
  <tr><td>Fragment 1</td><td>Head: 100 Attack Power, 50 Health</td></tr>
  <tr><td>Fragment 2</td><td>Body: 100 Health</td></tr>
  <tr><td>Fragment 3</td><td>Legs: 125 Attack Power, 50 Health, 1 Range</td></tr>
  <tr><td>Fragment 4</td><td>Armor: 100 Health</td></tr>
  <tr><td>Fragment 5</td><td>Rocket Launcher: 75 Attack, 2 Range</td></tr>
</table>

### The Recycler
<table>
  <tr><td>Name</td><td>The Recycler</td></tr>
  <tr><td>Type</td><td>Creature</td></tr>
  <tr><td>Rarity</td><td>Uncommon</td></tr>
  <tr><td>Cost</td><td>3 Iron, 2 Any-kind</td></tr>
  <tr><td>Attack Power</td><td>200</td></tr>
  <tr><td>Health</td><td>200</td></tr>
  <tr><td>Range</td><td>2</td></tr>
  <tr><td>Card Text</td><td>When you enter combat and the defender loses a fragment, you gain it.</td></tr>
  <tr><td>Fragment 1</td><td>Laser: 200 Attack Power, 2 Range</td></tr>
  <tr><td>Fragment 2</td><td>Body: 200 Health</td></tr>
</table>
