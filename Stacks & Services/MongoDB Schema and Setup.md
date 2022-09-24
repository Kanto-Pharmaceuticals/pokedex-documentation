---
aliases:
  - MongoDB Schema and Setup
  - Database Schema and Setup
  - Data Schema
tags:
  - backend
  - design
title: MongoDB Schema and Setup
date created: Friday, September 23rd 2022, 6:26:01 pm
date modified: Friday, September 23rd 2022, 8:39:38 pm
---

# MongoDB Schema and Setup

**Type:** MongoDB (Self-hosted)
**Name:** `pokedex`
**Collections:** `[trainers, pokemons, items, badges]`
**Tools:** [MongoDB](https://www.mongodb.com/compatibility/docker), [Compass](https://www.mongodb.com/products/compass), and [Postman](https://www.postman.com)

## Shaping the Data

It is important to note that this is not a data modelling project, and thus only simple data models are used.  Collections for `trainers` have been separated from `pokemons`, `items`, and `badges` in order to simplify the validation process in the backend.  Associations are two-way between linked collections.

### Simple Tree Chart of Collection Relationships

```ascii
trainers
 ├─pokemons
 │  └─items
 ├─items
 └─badges
```

### Trainer JSON Document Shape in MongoDB

```json
// trainer schema
"trainer": {
	// trainer information
	"id": string,
	"name": string,
	"email": string,
	"password": string,
	"roles": ["Rookie", "Novice", "Great", "Ultra", "Challenger", 
					 "Master"],
	"pokedex": [...pokemon.id],
	"inventory": [...items.id],
	"achievements": [...badges.id],
	// timestamps and versions
	"createdAt": date,
	"updatedAt": date,
	"__v": integer,
}
```

### Pokémon JSON Document Shape in MongoDB

```json
// pokémon schema
"pokemon": {
	// pokemon instanced information
	"id": string,
	"name": string,
	"species": string,
	"trainer": trainer.id,
	"items": [...items.id],
	// timestamps and versions
	"createdAt": date,
	"updatedAt": date,
	"__v": integer,
}
```

### Items JSON Document Shape in MongoDB

```json
// item schema
"item": {
	// items instanced information
	"id": string,
	"name": string,
	"owner": [trainer.id, pokemon.id],
	// timestamps and versions
	"createdAt": date,
	"updatedAt": date,
	"__v": integer,
}
```

### Badges JSON Document Shape in MongoDB

```json
// badge schema
"badge": {
	// badges instanced information
	"id": string,
	"name": string,
	"owner": [trainer.id],
	// timestamps and versions
	"createdAt": date,
	"updatedAt": date,
	"__v": integer,
}
```
