# PSG Systems

## Designs

### Colours

Each colour has a 'price' based on the difficulty of procuring the dyes:

1. Light grey (argent vulgaris) and brown
2. Colours of plants that grow in a region (flowers, cactus, beetroot)
3. Black
4. Lapis lazuli, gold (or) and white (argent puris)
5. Colours not found in the build area

If using glazed terracotta, the following must be observed:

- White: Yellow, light blue
- Orange: White, cyan
- Magenta: none, arrows only
- Light blue: white, dark blue
- Yellow: brown
- Lime: Yellow
- Pink: white/light grey
- Grey: light grey
- Light grey: cyan, white, dark grey
- Cyan: white, dark grey
- Purple: black
- Blue: light blue, black
- Brown: cyan
- Green: white, lime
- Red: none
- Black: red, dark grey 

If applying villager ethnicities, the following must be observed:

- Plains: brown (and any colour)
- Desert: pale yellow, green, orange
- Jungle: brown, yellow, dark green
- Savanna: red, white, dead leaf green
- Snowy: light blue, white, brown
- Swamp: dark green, purple
- Taiga; bone white, brown

### Banners

Consist of up to 1-2 metals and 1-2 colours (or furs)

Metals are iron/silver, and gold

Colours are grey, red, orange, lime, light blue, cyan, blue, purple, magenta, pink and brown

Furs are black

Divisions are:

- per fess (2c)
- per pale (2c)
- per bend (2c)
- per bend sinister (2c)
- per saltire (2-4c): (per pale +) chevron + chevron inv.
- per chevron (2c)
- per pile (2c): chevron inv.
- per pall (3c): per pale + chevron inv.

Ordinaries are:

- cross
- saltire
- cross and saltire
- pale
- canadian pale: pale dexter + pale sinister
- bar: fess
- fess: base fess + chief fess
- chief
- bend
- bend sinister
- canton: chief dexter canton
- badge: base sinister canton (grey, brown, gold, lime, light blue), personal banners only

Charges are:

- roundel
- lozenge
- roundel in lozenge
- flower
- creeper
- skull and crossbone
- skull*: white skull, background-coloured per fess inverted
- thing
- apple*: red roundel, background-coloured thing
- moon*: white roundel, background-coloured flower, background-coloured pale sinister
- sun*: yellow flower, yellow roundel
- dragon**: purple base, black cross, purple masoned, black flower, purple inverted chevron

*: chief or base only

**: chief only

Special banners are

- heart: red base, base fess, white bordure indented, red lozenge, white chevron inv., chief fess
- dragon's head: purple base, black creeper, black bordure indented, black inverted chevron
- cross pattée: red base, white saltire, red cross, 2x white bordure
- cross fleury: white base, red paly, white base fess, white chief fess, white lozenge, red base indented, red chief indented, red cross, white bordure indented
- cross cerclée: white base, red bordure indented, white saltire, red fess, red pale, white bordure
- framed book: brown base, light grey fess, yellow bordure indented, white cross, red pale, bordure
- book: white base, black paly, white paly, brown per pale, brown fess, red pale
- wolf/fox: white base, black lozenge, light grey bordure indented, light grey roundel, light grey creeper, light grey inverted chevron
- rabbit: white base, black roundel, white flower, black chevron inv., white saltire, black bordure indented, white base indented
- skull: black base, white bordure indented, white fess, black base fess, white creeper charge, black chief fess
- steaming cauldron: white base, light gray roundel, brown bend sinister, black base fess, light grey chevron inv., light grey bordure indented, orange base indented, light grey bordure
- nether portal: purple base, magenta paly, purple masoned, magenta bordure indented, black bordure
- fishing rod: white base, black lozenge, red base sinister canton, black per bend inverted, brown bend sinister, black per bend sinister, black bordure indented
- enderman: purple base, magenta paly, black cross, black pale, black per fess inverted, black chief fess
- flower: black base, lime thing, green flower, black per bend inverted, red chief dexter canton, black bordure indented, black chief indented
- mushroom: black base, white cross, red per fess, black bordure indented, 2x black chief fess
- small carrot: orange base, green pale dexter, black lozenge, black per fess inverted, orange roundel, black per bend, black bordure indented
- large carrot: lime base, black bend sinister, black per pale, orange lozenge, black per bend sinister inverted, black bordure indented, black per pale dexter
- horseshoe: light grey base, black chief fess, black bordure indented, black bordure, black base fess, black inverted chevron, black roundel
- crown : black base, yellow lozenge, yellow creeper, black roundel, yellow chevron, black base fess, black per fess
- anvil: light grey base, grey creeper, light grey chief fess, light grey pase fess, light gray bordure, grey base fess
- frog: black base, lime lozenge, black chevron, lime flower, black creeper, black base fess, black bordure
- turtle: blue base, lime flower, blue skull, brown roundel, blue bordure, blue chief fess
- bread: brown base, black bordure indented, black pale sinister, black bordure
- enchantment table: light blue base, red inverted chevron, black pale, black per fess inverted, white base fess, white chief fess, white bordure
- bone: black base, white inverted chevron, white chevron, white fess, black bordure indented, black chief indented, black base indented
- bow: black base, light grey paly, brown saltire, black per bend, black per bend sinister inverted, black bordure

Variations are paly, masoned, chequy (white base, black per pale inverted, black chief dexter canton, black base dexter canton, white chief sinister canton, white base sinister canton) or gyronny (white base, black per fess, white chevron inv., black chevron)



## Person

Personal

- Name : str (genarated based on parents, locality and language)
- Age : int (in days, negative means died at that age)
- Gender : bool (for mother/father text only)
- Handedness : bool
- Noisy : bool
- Favorite colour : colour
- (favorite food?)

Daily life

- Wealth : int (in stone coins)
- Profession : Profession

- Bed : Furniture
- Jobsite : Furniture
- Gatherspace : Room
- Prices: {{Commodity: price}, Region : {(Commodity, price), }}

Family and friends

- Family colours / pattern
- Parents : Relationship[2]
- Children : Relationship[]
- Relationships : Relationship[] (attitude is -1 to 1)

Methods:

- summon(x, y, z) : void
  - In the case of a villager:`/summon minecraft:villager {x} {y} {z} {VillagerData:{type:jungle,profession:fletcher,level:1},Offers:{Recipes:[{buy:{id:oak_log,Count:1},sell:{id:oak_log,Count:1}}]},CustomName:'[{"text":"Fred"}]',PersistenceRequired:1b,Age:0}`
  - In the case of a wandering trader: `/summon minecraft:wandering_trader {x} {y} {z} {Offers:{Recipes:[{buy:{id:oak_log,Count:1},sell:{id:oak_log,Count:1}}]},CustomName:'[{"text":"Fred"}]',PersistenceRequired:1b}`

### Traits

#### Skills

Work:

- Construction (1 to 5): Ability to place blocks
- Mining (1 to 5): Ability to remove blocks
- Tending (1 to 5): Ability to interact with plants and animals
- Stocking (1 to 5): Ability to store and retrieve items
- Perception (1 to 5): Ability to perceive the environment passively
- Observation (1 to 5): Ability to gain knowledge through active observation

Social:

- Charisma (0 to 5): Ability to improve relations through interactions
- Entertaining (0 to 5): Likelihood of improving mood through interactions
- Deception (0 to 5): Ability to create false information

Intellect:

- Memory (0 to 64): Size of memory
- Planning (0 to 5): Ability to plan ahead
- Creativity (1 to 5): Ability to innovate
- Numeracy (0 to 5): Ability to perform calcuations
- Literacy (0 to 5): Ability to read and write
- Language (0-5): Ability to communicate

Locomotion:

- Speed (1 to 5): Ability to sneak, walk and sprint
- Swimming (0 to 5): Ability to swim
- Riding (0 to 5): Ability to ride
- Rowing (0 to 5): Ability to row

#### Biology

Functionality of various biological systems, have a higher likelihood of starting off high

- Vision (0-5): Ability to see
- Hearing (0-5): Ability to hear
- Movement (0-5): Ability to move

#### Evolution

Constant values determined at birth (may not provide a clear advantage or disadvantage)

- Temperature (3 to 10): Preferred biome temperature (10ths)
- Rainfall (0 to 10): Preferred biome rainfall (n/10ths)

#### Nature

Determined at birth, drifts with age, can be impacted by experiences

- Calm (0 to 5): Likelihood of resting (increases with age)
- Careful (0 to 5): Likelihood of avoiding risk (increases with age)
- Open (0 to 5): Multiplier for mutating traits (decreases with age)
- Astute (0 to 5): Multiplier for learning skills (decreases with age)
- Emotional (0 to 5): Multiplier for effect of mood (decreases with age)
- Adventurous (0 to 5): Likelihood of travelling/moving
- Curios (0 to 5): Likelihood of inspecting something
- Extroverted (1 to 5): Likelihood of socially interacting
- Brave (1 to 5): Likelihood of not panicking
- Alert (1 to 5): Multiplier for perception
- Impatient (0 to 5): Likelihood of decreasing mood while waiting
- Optimistic (-5 to 5): Likelihood of over-/underestimating
- Independent (0 to 5): Likelihood of separating from a group

#### Personality

Shifts slightly on a daily basis, 

- Friendly (-5 to 5): Multiplier for negative/positive relationship changes
- Forgiving (0 to 5): Relationships return to neutral
- Greedy (-5 to 5): Multiplier for profit margin (in %)
- Passionate (0 to 5): Multiplier for profit margin based on relationship
- Impulsive (0 to 5): Multiplier for profit margin based on mood
- Criminal (0 to 5): Likelihood of acting against the law
- Decadent (-5 to 5): Multiplier for satisfaction from luxury
- Flexible (1 to 5): Likelihood of updating prices, changing professions et al.
- Focused (-5 to 5): Multiplier on depth vs. breadth

#### Values

Values represent the ideology of an individual

- Conservative-progressive (-5 to 5): Should things change?
- Secular-traditional (-5 to 5): Should we honour traditions?
- Polygamy-monogamy (-5 to 5): Should relationships be exclusive?
- Androcentrist-gynocentrist (-5 to 5): Should women be in charge?
- Control-liberty (-5 to 5): Should we be free?
- Militant-peaceful (-5 to 5): Should we be peaceful?
- Closed-open (-5 to 5): Should we interact with others?
- Unionist-separatist (-5 to 5): Should we function independently?
- Autocracy-democracy (-5 to 5): Should everyone be in charge?
- Segregative-egalitarian (-5 to 5): Should everyone be equal?
- Lenient-strict (-5 to 5): Should we be decisive?
- Punishment-reform (-5 to 5): Should criminals be given chances?

### Actions

+ hunger() : int
+ eat(food : Food) : int
+ sleep() : int

+ work() : int
+ steal() : int
+ introduce(person : Person) : int
+ chat(person : Person) : int
+ gossip(person : Person, gossip : Gossip) : int
+ teach(person : Person, trait : string) : int
+ offer(person : Person, offer : Offer) : int
+ bump_into(person : Person) : int
+ pickpocket(person : Person) : int
+ fight(person : Person) : int
+ wander(pos : Position) : int
+ admire(furniture : Furniture) : int
+ approach(pos : Position) : int
+ play(people : [Person], furniture : Furniture) : int
+ panic() : int
+ flee(pos : Position) : int
+ hide(location : Location) : int
+ patrol(waypoints : [Position]) : int
+ chase(pos : Position) : int
+ attack(mob : Mob) : int

+ mount_use(mob : Mob) : int
+ boat_use() : int
+ minecart_use() : int
+ portal_use(portal : Portal) : int
+ lightning_strike() : int
+ cure() : int
+ kill(killedby : Mob) : int

### Relationship

- Person : Person
- Attitude : int (from -1 to 1)
- Cooldown : int 

Methods

- Chat (shifts attitude slightly based on ideological alignment in specific axis)
- Gift (increases attitude based on item value)
- Request (decreases attitude if cooldown not yet 0)
- Trade (increases attitude)

### Commodity

A commodity is either a good (item) or a service

#### Item

- ID
- Enchantment-value (total level of enchantments)
- Condition (durability in % of max. durability)
- Rarity (may be inherent to item type or increased upon enchantment, otherwise)
  1. Common (just a regular item, copy of copy/tattered): white
  2. Uncommon (has been renamed, copy of original): yellow
  3. Rare (belonged to a famous individual, original work): aqua
  4. Epic (was used to achieve something great): light_purple
  5. Legendary (this is an item that changed the world, absolutely priceless): red
- Origin : R

#### Service

- Name : str
- Profession : Profession
- Mastery : int
- Method : function

### Profession

Worker

- Glassmaker (Leatherworker) : Cauldron (Glass Pane)
- Lumberjack (Mason) : Stonecutter (Axe)
- Mason : Stonecutter (Pickaxe)
- Miner (Leatherworker) : Cauldron (Pickaxe)
- Potter (Leatherworker) : Cauldron (Pot)
- Builder (Leatherworker) : Cauldron (Brick)

Food

- Baker (Butcher) : Smoker (Cookie)
- Butcher : Smoker (available meat)
- Cowherd (Shepherd) : Loom (Stick)
- Farmer : Composter (Hoe)
- Fisherman : Barrel (Fishing Rod)
- Goatherd (Shepherd) : Loom (Horn)
- Poultry Farmer (Shepherd) : Loom (Seed)
- Shepherd : Loom (Shears)
- Hunter (Fletcher) : Fletching Table (Sword/Bow/Crossbow)

Tools and clothes

- Armourer : Blast Furnace (Chestplate)
- Enchanter (Cleric) : Brewing Stand (enchanted book)
- Mechanic (Armorer) : Blast Furnace (Lever)
- Fletcher : Fletching Table (Arrow)
- Leatherworker : Cauldron (available leather)
- Toolsmith : Smithing Table (Ingot)
- Weaponsmith : Grindstone (Sword)
- Weaver (Shepherd) : Loom (String)

Public service

- Gravedigger (Leatherworker) : Cauldron (Shovel)
- Healer (Cleric) : Brewing Stand (available potion)
- Surgeon (Butcher) : Smoker (Shears)
- Civil Servant (Librarian) : Lectern (currency)
- Gardener (Farmer) : Compost (Shovel)
- Captain (Weaponsmith) : Grindstone (Compass/Spyglass)

Academia

- Cartographer : Cartography Table (map)
- Cleric : Brewing Stand (book)
- Explorer (Cartographer) : Cartography Table (compass/spyglass)
- Librarian : Lectern (book and quill)
- Leader (Cleric) : Brewing Stand (watch)
- Speaker (Librarian) : Lectern (watch)

Other

- Unemployed
- Nitwit (unemployable/retired)
- Wandering Trader
- {...} Merchant (Wandering Trader) : (item for sale)



## Furniture

- Name (possessive or type)
- Owner (/Person)
- Room
- Position
- Facing



## Room

- Name (possessive or function)
- Owner (/Person)
- Function (enum)
- Box (interior space as 3Drect)
- Furniture (Furniture[])



## Building





## Community/Location



- Name



## Food

Food has an energy value (food points) as well as a quality rating (1-5):

1. Poor quality food has a saturation ratio ('nourishment') of 0.2 (except cake, cookies and honey; including poisonous potato)
2. Low: 0.6 (except poisonous potato and pumpkin pie)
3. Normal: 1.2 (except rabbit stew)
4. Good: 1.6 (including rabbit stew and pumpkin pie)
5. Excellent: 2.4 (including cake, biscuits, honey)

A person's food satisfaction is calculated by the difference between the average food quality weighted by energy (rounded up if optimist, down if pessimist) and their wealth.

### Farming

#### Crops

#### Livestock

#### Other

### Cooking

#### Furnace space

Furnace space is a measure to determine whether something can be smelted/burned/cooked.

A furnace has 

#### Ingredients

- Apple > +8 gold ingot for golden apple
- Beetroot > 6 for beetroot soup
- (Always 1 bowl per person)
- Carrot > +8 nuggets for golden carrot; +mushroom, +cooked rabbit +baked potato for rabbit stew
- Cocoa Beans > 1 + 2 wheat for 8 (16 food total always done)
- Cooked Rabbit > +mushroom +carrot +baked potato for rabbit stew
- Honey > 3 sugar if otherwise unavailable and eggs available
- Mushrooms > +carrot +cooked rabbit +baked potato for rabbit stew, otherwise 2 for mushroom stew
- Potato > baked potato (requires furnace space)

### Villagers

- Require 3 bread (15), 12 carrots (36), 12 potatos (12/60) or 12 beetroot (12) to breed -> assume 



## Economy

A value of a commodity is based on the amount of labour required, where one unit is 0.05 simulated seconds (1 ticks). It should be noted that the simulation runs in seconds, therefore a maximum of 20 actions (each costing 1 tick) can be achieved per second. There are no 'free' actions that produce value.

The maximum speed at which a person places or breaks blocks while working, feeds an animal, places or removes a single item from an inventory, is determined by their appropriate skill in building, breaking, feeding, stocking, :

1. 1/s
2. 2/s
3. 5/s
4. 10/s
5. 20/s

The resulting nominal value is the value of all ingredients, the value of durability lost, and the amount of labour (in ticks)

### Currency

If a currency is in place, then these are the denominations:

1. Stone coins (base currency, renamed buttons)
2. Iron coin (renamed iron nuggets)
3. Gold coin (renamed gold nugget)
4. Emerald
5. Diamond

The exchange rate between them is determined based on the amount in global circulation (e.g. ratio between number of stone coins and number of iron nuggets in circulation dictates exchange rate). The regulatory body may purchase excess iron and gold to turn it into currency.

### Microeconomy

### Macroeconomy

##### Taxes

###### Income Tax

All prices are increased by a certain margain, the surplus goes to the government via the local civil servants (who receive a cut of taxes based on mastery).

###### Inheritance Tax

Upon death, a part of the inheritance goes to the government via local civil servants.

###### Wealth Tax

Every day, everyone pays a fraction of their wealth to the government (influenced by government policy)

##### Government spending

###### Governance

Government projects (building new government buildings, paying government employees) will draw funds.

###### Military

Depending on the current state and level of militarisation of the government, funds may be invested in building military infrastructure and employing and training personell.

###### Public services

If the state is so inclined, it may provide or subsidise public services. Otherwise these may be privately operated.

###### Research

A progressive government may subsidise research.

###### Social services 

A socially inclined government may redistribute wealth to the poor.

## Needs

### Physiological

#### Food

#### Sleep

#### Water

#### Light

### Safety

#### Housing

Houses

#### Education

Apprenticeships, schools, libraries

#### Protection

Laws, law enforcement, defences, preventative measures

#### Healthcare

#### Emergency Services

Fire fighting, garrisons, food reserves

### Belonging

#### Communication

#### Social Spaces

### Esteem

#### Travel

#### Luxury

### Self-actualisation

#### Art

Statues, gardens, mosaics, architecture

#### Environmental Protection

Rare species and environments



## Policy

### Military

### Health and Safety

### Employment

### Economy

### Crime

### Social

### Services

### Property



## Progress

### Experiences

Experiences are used to 

### Food

##### Foraging

##### Hunting

- Tame wolves
- Invisibility (requires invisibility potion)

Firearms and Ammunition (see Fletcher for coverage)

- Bow (requires Fletcher)
- Crossbow (requires Mechanic)
- Tipped arrows (requires Potions)

- Spectral arrows (requires Glowstone)

##### Fishing

Corresponding to required mastery:

1. Shoreside fishing
2. Fishing piers
3. Fishing dinghy
4. Fishing boats
5. Fishing ships

May be discovered independently (requires enchanting):

- Luck of the Sea
- Lure

##### Farming

##### Other

### Industry

#### Tools and weapons

Corresponding to required mastery:

1. Wood (requires lumberjack)
2. Stone (requires miner)
3. Iron (requires toolsmith)
4. Diamond (upon discovery)
5. Netherite (upon discovery, will require explorer with access to Nether)

Additionally, a corresponding professional will be required to manufacture any tools or weapons better than stone:

- Armourer: Armour and Shield
- Toolsmith: Flint and Steel, Hoe, Shovel, Pickaxe
- Weaponsmith: Sword, Axe, Shears

#### Forestry

Corresponding to required mastery:

1. Individual trees
2. Logging site
3. Logging camp
4. Sawmill (requires Mechanic)
5. Tree farm

#### Masonry

Corresponding to required mastery, the following items may be produced:

1. Stone from rockfaces/basins
2. Quarry site
3. Quarry camp
4. Stone bricks / smooth stones
5. Polished/chiselled stones

Independently unlockable (though similarly restricted):

- Bricks (upon discovery of Clay)
- Nether Bricks (upon discovery of the Nether)
- Quartz (upon discovery of quartz)

Corresponding to required mastery, the following services may be provided:

1. Gravestones, plackards and Milestones
2. Small pillars, monoliths and obelisks
3. Cenotaphs, tombs and small fountains
4. Statues and columns
5. Plazas, Arches, Palaces

#### Mining

Corresponding to required mastery:

1. Surface caving (requires a cave or quarry)
2. Mineshafts
3. Mining camp
4. Deep mine
5. Deepslate mining

Independently unlockable:

- Nether mining

#### Leatherwork

Corresponding to required mastery:

1. Leather clothing
2. Item frames
3. Bookbinding (requires paper)
4. Dyed leather
5. Saddling > Allows equestrianism

#### Fletching

Corresponding to required mastery:

1. Bow and Arrow > Allows bow enchantments to be discovered
2. Crossbow (requires Mechanic) > Allows crossbow enchantments to be discovered
3. Shooting range (requires Redstone, Wheat)
4. Spectral Arrow (requires Glowstone)
5. Tipped Arrow (requires Potions)

#### Glasswork

Corresponding to required mastery:

1. Glass blocks
2. Glass panes
3. Glass bottles
4. Stained glass
5. Glass mechanics (unlocks daylight detector)

Independently unlockable:

- Tinted glass (upon discovery of stained glass and Amethysts)
- Beacons (upon discovery of Nether Star)
- End crystal (upon defeating the Ender Dragon)

#### Pottery

Corresponding to required mastery:

1. Bricks
2. Terracotta
3. Flower pots
4. Dyed terracotta
5. Glazed terracotta

#### Mechanics

Corresponding to required mastery:

1. Redstone-free components
2. Non-metal redstone components
3. All components requiring only wood, stone, metal or redstone
4. All redstone components
5. Allows construction of complex automated systems

Independantly unlockable:

- Copperwork (requires Copper)
- Spyglass (requires Copper and Amethyst)

### Magic Levels

##### Potions

Brews achievable by all clerics (once discovered, after blaze rod is discovered)

- Water bottle, milk bucket
- Mundane potion (requires any of spider eye, rabbit's foot, sugar, redstone, melon and gold, ghast tear, blaze rod, magma cream)
- Thick potion (requires glowstone)

- Form:
  1. Splash potions (gunpowder discovered)
  2. Lingering potions (dragon's breath from explorer, requires End)

Effect (corresponds to required mastery):

1. Awkward potion (requires nether wart and glass maker)
2. Lvl 1 potion (each potion must be discovered individually)
3. Enhanced potions (applies to all potions)
4. Dark potions (requires fermented spider eye, each individually)
5. Potion of luck (chance to be discovered by level 4 cleric)

##### Enchantments

For the sake of simplicity, levels from https://minecraft.fandom.com/wiki/Enchanting/Levels are used with the median value for each enchantment:

| Name/Lvl                 | I    | II   | III  | IV   | V    |
| ------------------------ | ---- | ---- | ---- | ---- | ---- |
| A: Protection            | 6.5  | 22   | 28.5 | 39.5 | -    |
| A: Fire Protection       | 14   | 22   | 30   | 38   | -    |
| A: Feather Falling       | 8    | 14   | 20   | 26   | -    |
| A: Blast Protection      | 9    | 17   | 25   | 33   | -    |
| A: Projectile Protection | 6    | 12   | 18   | 24   | -    |
| A: Respiration           | 25   | 35   | 45   | -    | -    |
| A: Aqua Affinity         | 21   | -    | -    | -    | -    |
| A: Thorns                | 35   | 50   | 65   | -    | -    |
| A: Depth Strider         | 17.5 | 27.5 | 37.5 | -    | -    |
| A: Frost Walker          | 17.5 | 27.5 | -    | -    | -    |
| A: Curse of Binding      | 37.5 | -    | -    | -    | -    |
| A: Soul Speed            | 17.5 | 27.5 | 37.5 | -    | -    |
| S: Sharpness             | 11   | 22   | 33   | 44   | 55   |
| S: Smite                 | 15   | 23   | 31   | 39   | 47   |
| S: Bane of Arthropods    | 15   | 23   | 31   | 39   | 47   |
| S: Knockback             | 30   | 50   | -    | -    | -    |
| S: Fire Aspect           | 35   | 55   | -    | -    | -    |
| S: Looting               | 40   | 49   | 58   | -    | -    |
| S: Sweeping Edge         | 12.5 | 21.5 | 30.5 | -    | -    |
| B: Power                 | 8.5  | 18.5 | 28.5 | 38.5 | 48.5 |
| B: Punch                 | 24.5 | 44.5 | -    | -    | -    |
| B: Flame                 | 35   | -    | -    | -    | -    |
| B: Infinity              | 35   | -    | -    | -    | -    |
| T: Efficiency            | 26   | 36   | 46   | 56   | 66   |
| T: Silk Touch            | 40   | -    | -    | -    | -    |
| T: Fortune               | 40   | 49   | 58   | -    | -    |
| F: Luck of the Sea       | 40   | 49   | 58   | -    | -    |
| F: Lure                  | 40   | 49   | 58   | -    | -    |
| Tr: Channeling           | 37.5 | -    | -    | -    | -    |
| Tr: Impaling             | 11   | 19   | 27   | 35   | 43   |
| Tr: Loyalty              | 31   | 34.5 | 38   | -    | -    |
| Tr: Riptide              | 33.5 | 37   | 40.5 | -    | -    |
| C: Multishot             | 35   | 0    | 0    | 0    | 0    |
| C: Piercing              | 25.5 | 30.5 | 35.5 | 40.5 | 0    |
| C: Quick Charge          | 31   | 41   | 51   | 0    | 0    |
| Unbreaking               | 37.5 | 38   | 46   | -    | -    |
| Mending                  | 25.5 | -    | -    | -    | -    |
| Curse of Vanishing       | 37.5 | -    | -    | -    | -    |

A: Armor; S: Sword; B: Bow; T: Tool; F: Fishing rod; Tr: Trident; C: Crossbow

When a cleric attempts a spell, depending on their level they will make use 20, 40, 60, 80 and 100 levels per attempt. Spells must have been discovered for use. For that to occur, the corresponding item must have been unlocked first.

### Infrastructure

#### Lighting

Corresponding to required mastery:

1. Torches on posts
2. Lanterns on posts
3. Fire beacons
4. Street lanterns
5. Redstone lamps (requires Glass Mechanics)

#### Equestrian

Corresponding to required mastery:

1. No accommodation
2. Occasional water trough
3. Lean-tos (requires Saddle)
4. Stables
5. Relay stables with accommodation

#### Roadways

Roadways are separated into 16-block chunks (based on core thread where available).

Corresponding to required mastery:

1. Trail (disturbed landscape)
2. Path (visible from afar)
3. Route (established)
4. Street (paved)
5. Avenue (pristine)

Routes and above may also benefit from the following enhancements:

- Bridges
- Milestones (requires )
- Tunnels (requires Miner)
- Soulspeed lane (requires Soul Speed)

Additionally, a route may be abandoned, which results in a deteriorated and/or overgrown path

#### Railway

Corresponding to required mastery:

1. No accommodation
2. Regular single-line tracks, basic stop with furnace minecart (requires Mechanic)
3. Powered single-line tracks, basic stop
4. Powered double-line tracks, basic station
5. Powered double-line tracks, advanced station

#### Water Crossing

Corresponding to required mastery:

1. No accommodation
2. Raft
3. Ferry
4. Wooden bridge
5. Stone bridge

#### Exotic

Corresponding to required mastery:

1. No accommodation
2. Nether portal (requires Deep Mine or local Ruined Portal)
3. Ender pearl dispensary (requires Mechanic)
4. Riptide/Elytra launching point (requires Elytra)
5. Trans-Nether transport hub

#### Postal service

Corresponding to required mastery:

1. No accommodation
2. Courier service
3. Equestrian service
4. Rail service
5. Express item pipelines

#### Harbour

Corresponding to required mastery:

1. No accommodation
2. Pier
3. Docks
4. Harbour
5. Port

#### Trade

Corresponding to required mastery:

1. No accommodation
2. Cart
3. Stall
4. Shop
5. Store

#### Housing

Corresponding to required mastery:

1. Tent
2. Hut (single room)
3. House (multiple rooms)
4. Residence (>1 room per inhabitant)
5. Mansion (>2 rooms per inhabitant)

#### Defence

##### Walls

Corresponding to required mastery:

1. None
2. Palisades
3. Trenches
4. Earth wall
5. Stone wall

##### Guards

Corresponding to required mastery:

1. None
2. Guardpost
3. Garrison
4. Training site
5. Golem foundry (requires Mechanic)

#### Plumbing

Corresponding to required mastery:

1. None
2. Wells and Outhouses
3. Sewage canals and ground-level water
4. Bathhouses
5. Underground sewers and aqueducts

#### Education

Corresponding to required mastery:

1. None
2. Bookshelves (Furniture) (requires Bookbinding)
3. Guildhall (requires a Master in the appropriate profession)
4. School 
5. University 

#### Healthcare

Corresponding to required mastery:

1. None
2. Herbalist's Hut
3. Pharmacy
4. Clinic
5. Hospital

### Aesthetics

#### Banners

Corresponding to required mastery:

1. 2-colour fields or variation, level 1-3 colours
2. 3-colour fields and charges or variation
3. 4-colour fields and charges or variation, level 1-4 colours
4. 4-colours fields or variations with charges
5. Any banner and any colour

The discovery of banner patterns becomes universally accessible, so long as it is possessed by the weaver in question.

#### Paintings

...

#### Gardening

Corresponding to required mastery:

1. ...
2. ...
3. ...
4. ...
5. Lavish and exotic displays (in an appropriate environment)

