---
sidebar_position: 4
title: Reference's server model
---

## DND-like

```json
{
  "charName": false,
  "statistics": {
    "Strength": {
      "min": 1
    },
    "Dexterity": {
      "min": 1
    },
    "Constitution": {
      "min": 1
    },
    "Knowledge": {
      "min": 1
    },
    "Wisdom": {
      "min": 1
    },
    "Charisma": {
      "min": 1
    }
  },
  "diceType": "1d20+{{ceil(($-10)/2)}}>20",
  "critical": {
    "failure": 1,
    "success": 20
  },
  "total": 27
}
```

## System simple

```json
{
  "charName": true,
  "statistics": {
    "Strength": {
      "min": 3
    },
    "Stamina": {
      "min": 3
    },
    "Agility": {
      "min": 3
    },
    "Constitution": {
      "min": 3
    },
    "Education": {
      "min": 3
    },
    "Knowledge": {
      "min": 3
    },
    "Charisma": {
      "min": 3
    },
    "Power": {
      "min": 3
    },
    "PV": {
      "combinaison": "endurance*2+force"
    }
  },
  "diceType": "1d20+$>20",
  "critical": {
    "failure": 1,
    "success": 20
  },
  "total": 88
}
```