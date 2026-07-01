# Account

> Version: 0.1.0
>
> Status: Draft
>
> Last Updated: 2026-07-01

---

# Purpose

The Account entity represents a Guardian Tales player profile inside the Guardian Tales Knowledge Platform (GTKP).

An Account stores the player's progression, owned resources, unlocked content, inventory and optimization preferences.

It is the root entity of the platform.

---

# Responsibilities

The Account is responsible for:

- Identifying a player profile
- Storing progression
- Linking owned Heroes
- Linking owned Weapons
- Linking Accessories
- Linking Relics
- Linking Merchandise
- Tracking Collections
- Tracking completed content
- Tracking resources
- Storing planner settings
- Providing data for recommendation engines

---

# Identity

Each Account must have a unique identifier.

Example

```
account-000001
```

---

# Lifecycle

Account

↓

Created

↓

Configured

↓

Imported

↓

Updated

↓

Optimized

↓

Archived

---

# Relationships

An Account contains:

- Inventory
- Heroes
- Weapons
- Accessories
- Shields
- Cards
- Relics
- Merchandise
- Collections
- Teams
- Game Progress
- Planner
- Recommendations

---

# Core Properties

## Identification

- accountId
- accountName
- server
- region

---

## Progression

- guardianLevel
- worldCompleted
- orbitalLiftFloor
- towerProgress
- expeditionProgress
- deceitfulNightmareProgress
- bossRushProgress
- raidParticipation
- colosseumRank
- arenaRank

---

## Inventory

The Account references a single Inventory entity.

The Inventory stores all owned assets.

---

## Resources

Examples

- Gold
- Gems
- Coffee
- Stamina
- Hero Crystals
- Mileage Tickets
- Magic Metal
- Awakening Stones
- Blessing Materials

---

## Collections

Stores collection completion.

Examples

- Hero Collections
- Weapon Collections
- Item Collections

---

## Planner

Stores user preferences.

Examples

Preferred Content

Investment Priority

Favorite Heroes

Ignored Recommendations

---

## Metadata

- creationDate
- lastUpdate
- gameVersion
- dataSource

---

# Business Rules

## Rule 1

One Account owns exactly one Inventory.

---

## Rule 2

A Hero may belong to many Accounts.

---

## Rule 3

An Account never stores duplicated Hero definitions.

Only references.

---

## Rule 4

Official Game Data is never modified by an Account.

---

## Rule 5

Recommendations are generated from Account data.

They are never manually stored.

---

# Validation Rules

Required

- accountId
- accountName

Optional

- planner
- metadata

---

# Dependencies

Account depends on

- Inventory
- Hero
- Weapon
- Collection
- Recommendation

---

# Examples

Example Account

```

Player

↓

Guardian Level 350

↓

143 Heroes

↓

126 EX Weapons

↓

All Story Completed

↓

Arena Top 100

↓

Raid Active

↓

Planner Enabled

```

---

# Future Extensions

Future versions may include

- Guild Information
- Friend List
- Achievement History
- Battle Statistics
- Resource History
- Multi-account Management

---

# Notes

The Account entity is the entry point for every optimization engine inside GTKP.

Every recommendation starts from an Account.