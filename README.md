initial
# Collectible Card Game (CCG) Framework Sample JSON

Here is a general JSON sample for a CCG (Collectible Card Game) framework, covering cards, players, decks, and game state:

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
    }
    // ... more card definitions ...
  ],
  "rules": {
    "startingHandSize": 5,
    "maxHandSize": 7,
    "winCondition": "Reduce opponent's health to 0"
  }
}
```

This sample covers the basic structure for cards, players, decks, and rules in a CCG framework.
