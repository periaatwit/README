Overview:
Each and every thing in the game, including the player, is a "Interactable" with unique statistics determined by the type of item. Every interactable has a container that holds items. Through ties created by door items or stored objects, the world is connected.

Item Types and Properties:
Interactable (Base Class):
Name: Given name of the object for interaction.
Description: Displayed when looked at, including contained items.
Contains: List of items stored.
UseCase: Text displayed when interacted with.
TakeAble: Determines if the object can be picked up or dropped.
BreakAble: Indicates if the object can be broken.
BrokenItem: Item dropped when broken.
BreakKey: Object needed in the player's inventory to break the item.
Room:
Indicated as a place to be interacted with by Player objects and has saved coordinates (now UNUSED). Only objects in the same room can be interacted with by players.
Wall:
Holds a direction that is saved for orientation and is utilized when the player performs actions like "Looking Left."
Door:
Linked destination and can be locked with a defined item (currently only keys can unlock doors).
Key:
Carries a pre-selected "target" to look for, typically a Door object. When the user uses it, the door unlocks if the target object is in the same room as them.
Player:
Has a designated room and the player is the conduit for all actions. Objects can be picked up and dropped using the player's "contains" as an inventory.
ObjectTree and Hidden Objects:
Since It might be difficult to search among nested objects, the utility class ObjectTree() was developed to print each component that is available behind a bigger one. "-" behind the object indicates that it is a hidden object.
For example tree, refer to the file worldTree.txt.
Text Engine:
After processing user input as a string, the text engine separates it into nouns, verbs, and adjectives. An alias dictionary is applied to each keyword in order to change related terms into predetermined ones. In an ideal system, the verb defines a Player method, and the noun points to an Interactable that is supplied to it. Default choices and assumptions are used to address edge cases and unclear circumstances.
# README
