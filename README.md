# Discretize GW2API - extended

This repo serves as an api, that fills the long outstanding gaps of the api.guildwars2.com. For example, firebrand tome skills are missing.

A program can easily interact with this api:

```
curl https://discretize.github.io/discretize-gw2api/api/skills/epilogueashesofthejust.json
```

The name of the requested skill/component/item must be normalized! For the discretize projects we use this normalization function:

```js
const normalize = (string) =>
  string
    .replace(/[^A-Za-z]/g, "")
    .toLowerCase()
    .trim();
```

## Adding new skills/items/something to this api

Please check the existing skills and build upon that.

1. Create a new file with a normalized name (only upper/lowercase letters, no spaces, no numbers, no special characters).
2. Open the game and look at the tooltip of the skill/item/something you want to add.
3. Replicate the tooltip! The best course of action is to look for another skill, that is included in the official api and grab relevant bits out of that skill.

Note: Some icons are probably hard/impossible to locate in the api. For now we will go with wiki links in that case.
