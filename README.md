# Collectible Card Game (CCG) Framework Documentation

## Table of Contents
- [JSON Structure Overview](#json-structure-overview)
- [Game Structure](#game-structure)
- [Card Examples](#card-examples)
- [Game Rules](#game-rules)
- [Usage Examples](#usage-examples)

## JSON Structure Overview

Here is a comprehensive JSON sample for a CCG (Collectible Card Game) framework, covering cards, players, decks, and game state:

```json
{
  "game": {
    "title": "Elemental Clash",
    "players": [
      {
        "name": "Player1",
        "health": 20,
        "mana": 3,
        "hand": [101, 102, 103, 104, 105],
        "deck": [106, 107, 108, 109, 110, 111, 112, 113, 114, 115]
      },
      {
        "name": "Player2",
        "health": 20,
        "mana": 3,
        "hand": [201, 202, 203, 204, 205],
        "deck": [206, 207, 208, 209, 210, 211, 212, 213, 214, 215]
      }
    ],
    "turn": 1,
    "activePlayer": "Player1"
  },
  "cards": [
    {
      "id": 101,
      "name": "Lightning Mage",
      "type": "Creature",
      "cost": 4,
      "attack": 3,
      "health": 4,
      "ability": "When played, deal 2 damage to any target."
    },
    {
      "id": 102,
      "name": "Fire Elemental",
      "type": "Creature",
      "cost": 3,
      "attack": 4,
      "health": 2,
      "ability": "Deal 2 damage to enemy hero when played."
    },
    {
      "id": 103,
      "name": "Healing Potion",
      "type": "Spell",
      "cost": 2,
      "ability": "Restore 5 health to target."
    },
    {
      "id": 104,
      "name": "Stone Guardian",
      "type": "Creature",
      "cost": 5,
      "attack": 2,
      "health": 8,
      "ability": "Taunt: Enemies must attack this creature first."
    },
    {
      "id": 105,
      "name": "Wind Sprint",
      "type": "Spell",
      "cost": 1,
      "ability": "Draw 2 cards."
    },
    {
      "id": 201,
      "name": "Ice Shard",
      "type": "Spell",
      "cost": 3,
      "ability": "Deal 4 damage and freeze target for 1 turn."
    },
    {
      "id": 202,
      "name": "Forest Druid",
      "type": "Creature",
      "cost": 3,
      "attack": 2,
      "health": 3,
      "ability": "At end of turn, gain +1/+1."
    }
  ],
  "rules": {
    "startingHandSize": 5,
    "maxHandSize": 7,
    "winCondition": "Reduce opponent's health to 0"
  }
}
```

## Game Structure

The CCG framework consists of several core components:

### Game Object
- **title**: The name of the game
- **players**: Array of player objects (typically 2 players)
- **turn**: Current turn number
- **activePlayer**: Name of the player whose turn it is

### Player Structure
Each player has:
- **name**: Player identifier
- **health**: Current health points (game ends when reaches 0)
- **mana**: Available resources to play cards
- **hand**: Array of card IDs currently in player's hand
- **deck**: Array of card IDs remaining in player's deck

## Card Examples

The framework supports different card types:

### Creature Cards
Creature cards have attack and health values and can engage in combat:
- **Lightning Mage**: A balanced creature with a targeted damage ability
- **Fire Elemental**: High attack, low health with direct damage
- **Stone Guardian**: Defensive creature with taunt ability
- **Forest Druid**: Growth-oriented creature that gets stronger over time

### Spell Cards
Spell cards provide immediate effects:
- **Healing Potion**: Restoration spell for health recovery
- **Wind Sprint**: Card draw for hand advantage
- **Ice Shard**: Damage spell with additional freeze effect

## Game Rules

The rules object defines core game mechanics:
- **startingHandSize**: Number of cards each player starts with (5)
- **maxHandSize**: Maximum cards a player can hold (7)
- **winCondition**: Primary victory condition (reduce opponent's health to 0)

## Usage Examples

### Playing a Card
```json
{
  "action": "playCard",
  "cardId": 101,
  "target": "Player2"
}
```

### Drawing a Card
```json
{
  "action": "drawCard",
  "player": "Player1"
}
```

### End Turn
```json
{
  "action": "endTurn",
  "player": "Player1"
}
