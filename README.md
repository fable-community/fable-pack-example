# Example

> **Warning** Support for installing packs in Fable is still being worked on.  
> You can pre-create packs and validate them, but acually adding them to your server will have to wait for ker0olos/fable#73 to be merged.

---

When using a code editor like "VS Code" and adding:

```json
"$schema": "https://fable.deno.dev/schema.json",
```

You will be able to get helpful auto-completions and validation errors while writing your pack's manifest.

You can also run `/packs validate fable-community/example` or `/packs validate fable-community/example test-branch`
or from your terminal run `deno run -A https://raw.githubusercontent.com/ker0olos/fable/main/src/validate.ts ./manifest.json
`

Wanna try installing this pack instead? run `/packs install fable-community/example`

---

## Quick introduction

Start by picking an id for your pack (be extra careful because chaning your id after people start using your pack will break people's obtained characters).

```json
{
  "id": "example"
}
```

You can also define a `title` (it appears when people are looking at your pack details instead of your pack's id).

```json
{
  "title": "Example"
}
```

Other metadata include:

```json
{
  "description": "An example pack to demonstrate how to create a manifest",
  "author": "Fable Community",
  "image": "https://example.com/image.png",
  "url": "https://github.com/fable-community/example",
}
```

> Want a more serious/full example? Checkout the official vtubers pack manifest:  
> https://github.com/ker0olos/fable/blob/main/packs/vtubers/manifest.json

## Adding Media

Media, can be anything. Anime, Manga, Video Games, Football Leauges, Boy Bands.

To add a media to your pack: it needs to be defined under `media.new`, like this: 

```json
"media": {
  "new": [
    {
      "id": "media-1"
    },
    {
      "id": "media-2"
    }
  ]
},
```

Check the `manifest.json` file in this repo for all the details about the data that a media can hold: like `title`, `images`, `trailer`, `externalLinks`.

### Conflicts

Your media conflicts with another famous pack's media but you don't want to replace the other pack? Adding the conflicted media ids under `media.conflicts` like so, will disable those specific media while leaving the other pack itself and its other content functional. The format is like this `other-pack-id[:]conflicted-media-id`.

```json
"media": {
  "conflicts": [
    "anilist:145478",
    "anilist:118123",
  ],
},
```

## Adding Characters

To add characters to your pack it needs to be defined under `characters.new`, like this: 

```json
"characters": {
  "new": [
    {
      "id": "character-1"
    },
    {
      "id": "character-2"
    }
  ]
},
```

Check the `manifest.json` file in this repo for all the details about the data that a character can hold like `name`, `images`, `description`, `externalLinks`.

### Conflicts

Your character conflicts with another famous pack's character but you don't want to replace the other pack? Adding the conflicted character ids under `characters.conflicts` like so, will disable those specific characters while leaving the other pack itself and its other content functional. The format is like this `other-pack-id[:]conflicted-character-id`.

```json
"characters": {
  "conflicts": [
    "anilist:206017",
    "anilist:206013",
  ],
},
```
