# Changelog
## General

1. Renamed Character to Creature because Character is reserved class in Java.
2. Renamed Printer class to UI, as it also handles input from user
3. Removed movePlayer and setPosition from CaveHandler
4. Observer pattern to handle item interaction
5. Factory pattern to lower coupling


## Interaction diagrams

### Open backpack
1. Changed openBackpack() to getBackpack() on Player class
2. calls open on the backpack from Game class
3. Backpack calls printBackpack on self


### Use item
1. Removed ActionDispatcher
2. Removed getDefaultAction
3. Now ItemHandler uses the item's "use()"
4. ItemHandler calls "removeItem(item)" on itself

### Display Item Info
1. There was no need to return the item

### End game session
1. Pass constant instead of string to setState()

### Initialize Game
1. setGameInstance renamed to setCurrentState
2. No longer returns game to the menu state as it has no use there

### Interact with character
1. Character class is now named Creature
2. Fight class handles the fight instead of CharacterHandler
3. Added loop that handles the fight event that takes place in the Fight class
4. The creature needs to be removed from the cave after he is dead so added interaction with the cave

### Move Direction
1. Event no longer prints
2. Gets player position from Cave

### Enter Cave
1. Current cave now belongs to Game object
2. Game loads map data from cave which gets the map from the MapLoader class
3. Game adds item to the Cave by getting items from ItemHandler

### Pick up item
1. printItemInfo before dialog
2. the dialog returns "remove from cave". If true the item is removed from cave
