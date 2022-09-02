# Introduction
## Table of Contents

# World
The world consists of a Pitch (with each 1x1 unit called a 'square'), as well as a Dugouts for each Team. The Dugouts represents lists of inactive Players, and Atoms may exist inside the Dugouts without occupying any space or position.

## Dugouts
### Reserves Box
Players that are currently not on the Pitch, but are neither knocked-out, injured or dead must be in the Reserves Box.
This includes Players that are pushed of the pitch and stunned as a result.

### Knocked-Out Box
Players that are knocked-out must be in the Knocked-Out Box.
### Casualty Box
Players that are either injured or dead must be in the Casualty Box.

## Scopes
### Pitch
The 26x15-sized Pitch uses two distinct coordinate systems:
1. Normalised: Where the (0, 0) square is in the bottom left corner
2. Symmetrical: Where the (0, 0) square is the first square in positive-X centrally located along the Line of Scrimmage, which would be (13, 7) in normalised coordinates.

Unless declared otherwise, all methods should use the symmetrical notation to accomodate for boards of differing sizes. The rest of this document also uses the symmetrical notation.

#### Centre Field
The Centre Field runs across the length of the Pitch between the Wide Zones, and is seperated into each side by team (E.g. Centre A, Centre B)

#### Line of Scrimmage
The line of Scrimmage runs vertically along the centre of the Pitch.
The space adjacent to the Line of Scrimmage on the appropriate side of the field is that team's Line of Scrimmage (e.g. Scrimmage A, Scrimmage B) and has, with a standard Pitch, a size of 1x7 squares.

#### Wide Zones
There are two wide zones on the standard Pitch, one along the upper and one along the lower edge of the Pitch, named Upper Wide and Lower Wide respectively.
Boch scopes are seperated into each Team's side (e.g. Upper Wide A and Upper Wide B).

#### End Zones
The End Zones are the squares furthest from the Line of Scrimmage, with one for each Team. If a standing Player is holding a Ball while in the End Zone of the opposing team, a touchdown is triggered. 

#### Sidelines
Between the Wide Zones and the Edge of the Pitch lie the (Upper and Lower) Sidelines, although for the purposes of this document the squares adjacent to the Sidelines will be called the Sidelines. They are seperated identically to the Wide Zones (e.g. Upper and Lower, A and B).

# Atoms
## Player
A player is a figure on the board and 

### Properties

- Movement Allowance (MA)
- Strength (ST)
- Agility (AG)
- Armour Value (AV)
- Skills

#### Types
- Blitzer: 
- Catcher: 
- Thrower: 
- Lineman: 
- Runner: 
- Blocker: 

### States
- Has Ball : bool
- Moves left : int
- Has Blitzed : bool
- Has Passed : bool
- (Has Handed-off) : bool
- (Has Fouled) : bool
- Knockdown : int (0 is up, 1 is stupor, 2 is prone, 3 is stunned, 4 is stunned this turn)
- Condition : int (0 on pitch, 1 in reserves, 2 mild knock-out, 3 serious knock-out, 4 injured, 5 dead)


### Actions
Actions return ...

- strength
- agility
- 


## Ball
The ball only exists when it is not being held by a player. The ball does not take an action, but has methods pertaining to its behaviour according to player's actions.

### Properties
Currently, since all balls should act identically, there is only an ID to identify the version or implementation of the ball
- ID

### States
- Being Held : bool
- 

# Beings
Due to the nature of Blood Bowl having only ever one player or ball per square, there are no Beings.

# Managers
Managers are objects that apply logic to the World, its Scopes and/or its Entites.

## Referee
The Referee manages the entire game, and therefore all Entities in the World.
Coaches request actions which the referee may accept or decline based on the rules of the game. If declined, the referee must provide a reason.

### Properties
Currently, since all referees should act identically, there is only an ID to identify the version or implementation of the referee
- ID

### States


## Coach
The Coach manages his team by playing the game (not to be confused with a Player, which is a figure on the pitch)

### Properties
- ID
- Name
- Fan factor
- Players

### States
- Turn: int
- Re-rolls : int
- Score : int
- Has Blitzed : bool
- Has Passed : bool
- (Has Handed-off) : bool
- (Has Fouled) : bool

# Events
## Referee

### Roll
The referee rolls a number of n-sided dice and applies modifiers.

### Illegal Procedure
Player calls out opposite player for starting turn before incrementing turn counter. If the turn counter is incremented before the illagal procedure is raised, then the raise is invalid
If valid, accused immediately ends turn or uses a re-roll (choice of accused). If no more re-rolls are available, then the accusing gains a re-roll. 
If invalid, the accusing loses a re-roll. If no more re-rolls are available, then the accused gains a re-roll. 
TODO: Clarify what happens when the turn counter isn't incremented and the opponent doesn't react to it up to the next turn.

### Start Game
A new game has begun. This may include determining certain rules of the game, and is followed by a Start Drive.

### Start Drive
A new drive has begun. This consists of a toss of the coin to determine the kicking Team and is followed by a setup for the kicking Team, then a setup for the receiving Team, followed by the kick-off and the first turn for the receiving Team.

### Kicker is Team
Announces the kicker Team

### Call Setup
A Coach provides the formation of their Team. The kicking Team will go first (on an empty pitch), the receiving team will go second (with the formation of the kicking team visible).
The following must be adhered to for the formation to be valid:
1. No more then two Players per Team on each Wide Zone
2. At least three Players per Team must be on the Line of Scrimmage

An illegal formation will result in a second and third attempt. If all attempts fail, they are provided with a default formation.

### Kick-off
The Coach of the Kicking team may choose a square in the opposing Team's half of the Pitch, from where a kick-off of the Ball's Kick-off Scatter is called.
Following a kickoff, the receiving Team starts their turn.

### Kick-off Table
2D6 are thrown, and the result is read from the table and resolved.

### Touchback
A coach must give the ball to any player on their team.

### Team's Turn
It is the announced team's turn to play. The four-minute countdown is started.

### Turnover
The referee may end a turn prematurely when one of the following takes place:
1. A player on the moving team is Knocked Down
2. A passed ball or hand-off is not caught by a member of the moving theam before the ball comes to rest
3. A player from the moving team fails to pick up the ball
4. A touchdown is scored
5. The four-minute time limit for the turn runs out
6. A pass attempt is fumbled
7. A thown player with the ball fails to land successfully
8. A player is ejected for a foul
After a turnover, armour and injury rolls for players that were knocked down are completed, any dropped balls are bounced and stunned players are made prone. 
The coach may take no action until it is their turn again.

### Choose
FIXME: A coach is given a choice, including:
- Whether to end the turn or lose a re-roll in the case of illegal procedure

### Drive Finished


### Half Finished

### Overtime
The game has ended in a draw and the referee has called overtime. 

### Game Finished

### Award/Confiscate Re-Roll
A coach is given an additional re-roll or forced to use a re-roll to no effect as a punishment.

## Team/Coach
### Setup Team
Communicate the setup the team would like to use.
Typically in response to a Call Setup by the Referee when called by name.

### Pick Square
The coach chooses a square.
This is usually in response to a query from the Referee.

### Pick Player
The coach chooses a player.
This is usually in response to a query from the Referee, for example in the case of a touchback or when activating a player.

### Pick Dice
The coach chooses a dice.
This is usually in response to a query from the Referee, for example when Blocking with multiple dice or using a re-roll.

### Increase Turn Marker
The coach signals they have started their turn.

### End Turn
The coach signals they have finished their turn.

### Use Player
The coach signals the player they will act with next.

### Move with Player

### Block with Player
The coach should determine whether they wish to follow up in case of a push when attempting to block

### Blitz with Player

### Pass with Player

### (Hand-off with Player)

### (Foul with Player)

### Finished with Player
The coach signals they have finished with the player, allowing the coach to manage a new player

### Use Re-roll
Results in any dice (barring AR, Injury or Casualty rolls) rolled for a friendly player who is on-pitch during their turn being re-rolled.

### Substitute Player

## Player
### Move

### Block

### Blitz
A move directly followed by a block. The player is allowed to move MA-1 squares.

### Pass

### (Hand-off)

### (Foul)

### Dodge

### Knock Down

### Injure

### Stand up

### Pick up

### Catch


## Ball
### Kick-off Scatter
The ball is scattered with a distance of a D6.
Before continuing, a Kick-off Table is called.
If it lands on an empty square, bounce.
If it lands off the pitch or into the kicking team's half, a Touchback is called.

### Bounce
A scatter that results in movement by a single block.

### Scatter
Scatters may be consecutive and move along multiple squares at a time.
After all scatters have been executed, if it lands on a player, attempt a catch. If it fails, bounce.

# Notes on Extra Rules
## Custom Teams

## Star Players

## Kick-off Table

## Weather

## Handing-Off

## Going for it

## Block Assists

## Interceptions

## Fumbles

## Fouls

## Skills
Certain basic skills may be part of any game (unless skills are disabled):
- Block: Affects Block Dice
- Catch: Re-roll failed catch, hand-off or intercept
- Dodge: Re-roll failed dodge and affects Block Dice
- Pass: Re-roll missed pass
- Sure Hands: Re-roll failed pick-up, immune to Strip Ball

If playing with extra rules, the following skills may be included:
- Accurate: D6+1 when passing
- Always Hungry: 1 on D6 when throwing results in attempt to eat, else ignored; another 1 on D6 causes death, else fumble
- Animosity: 1 on D6 when hand-off or passing to Player of different race results in refusal
- TODO: Ball & Chain: special behaviour
- Big Hand: No tackle zone or pouring rain modifiers when picking up
- Blood Lust: 1 on D6 results in attacking Thrall or turnover with move to Reserves Box
- TODO: Bombardier: Exploding Ball that causes Knock-downs
- Bone-head: 1 on D6 results in stupor
- Break Tackle: Dodge with Strength instead of Agility
- TODO: Chainsaw: special behaviour
- Claws: When knocking down with armour roll 8+ after modifiers, ignore armour
- Dauntless: If ST+D6 > opponent's ST, then act as equal strength (excluding assists)
- Decay: Roll Casualties twice and apply both
- Dirty Player: +1 on Armour or Injury when fouling
- Disturbing Presence: D6-1 on all players passing, intercepting or catching if within three squares (even when knocked down)
- Diving Catch: +1 to catch from accurate pass; may catch ball in tackle zone
- Diving Tackle: Land prone in space of dodging Player, who gets -2 on Dodge
- Dump-Off: When being blocked, Quick Pass (without ending turn)
- Extra Arms: +1 to pick up, intercept and catch
- Fan Favourite: +1 FAME for Kick-Off Table
- Fend: Blocker may not follow up (unless using Blitz)
- Foul Appearance: 1 on D6 causes opponent's block to be ignored
- Frenzy: Must follow up when blocking and repeat blocking same opponent if pushed or stumbled
- Grab: On block, place opponent on any adjacent empty square instead of pushing
- Guard: Assists even if in tackle zone (except foul)
- Hail Mary Pass: Pass to any square, 1 on D6 is fumble, otherwise miss and three scatters.
- Horns: ST+1 on Blitz Block
- TODO: Hypnotic Gaze: Stupor instead of block
- Juggernaut: Immune to Fend, Stand Firm and Wrestle on Blitz, Both Down may be Pushed
- Jump Up: Stand up for free, except with intention to block, in which case AG+2 and no stand up on fail
- Kick: Half scatter of kick-off if not in Wide Zone or Line of Scrimmage
- Kick-Off Return: Move up to three tiles after scatter but before Kick-Off Table in own half
- Leader: Extra re-roll if on pitch
- FIXME: Leap: 

# Notes on Leagues

## Custom Teams

## Inducements

## Injuries

## Star Player Points

## Improvement Rolls

## Spiralling Expenses

# Notes on Tournaments

## Alternate MVP Rules

## Alternate Expense Modifications

## Alternate Inducements

## Special Play Cards

## Free Fan Factor

## Additional Gold

# Special Balls


# Sevens

# Street Bowl

# Dungeon Bowl

- Only one drive
- Quick and short passes only

## Generated Map

At least:
- 4 Corridors (2 wide)
- 3 Small Rooms
- 1 Large Room
- 2 End Zones (as far apart as possible)
- 6 Chests
- Exactly 6 Teleporters

## Chests
One contains ball, all others cause knockdown to all adjacent players.

## Teleporters
Roll dice to determine which teleporter has been teleported to.
If teleported twice per turn, injury roll
If value rolles is equal to the number of the teleporter the player is teleporting from, they are removed from the game.

## Doorways and Walls

### Push into Wall
### Ricochets

# Death Bowl

# Beach Bowl

# Custom Game Variations

## Alternate Game Parameters
- Number of turns per half
- Number of halfs
## More Teams
### Doubles/Triples etc.

### 

## Alternate Formation Rules
Allowing different numbers of minimal and maximal Players, as well as only allowing or disallowing certain traits, per region on the Pitch allows for the start of the game to behave radically different.

### E.g. *Blood Crucible*
Players may be placed on the opponent's side of the Pitch while following other Formation rules

## Multiple Balls

## Non-Standard Pitch

### Alternate Sizes

### Alternate Layouts

#### E.g. Dungeon Bowl

### Alternate Tiling
Using a tiling system with fundamentally different shapes or 

#### E.g. Hexagonal
Well-suited for two, three or six teams

## Non-Standard Referre

## Limited Visibility

## Changing rules

