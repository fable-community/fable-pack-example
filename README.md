# Example

> **Warning**

Support for installing packs in Fable is still being worked on.

You can pre-create packs and validate them, but acually adding them to your server will have to wait for ker0olos/fable#51
Don't worry it's 100% confirmed, we just don't think it's our prioity since people aren't fighting to make packs right now.

---

When using a code editor like "VS Code" and adding:

```json
"$schema": "https://fable.deno.dev/schema.json",
```

You will be able to get helpful auto-completions and validation error while writing your manifest

---

## Quick introduction

Start by picking an id for your pack, be careful because, chaning your id after people start using your pack will break everything.

```json
{
  "id": "example"
}
```

You can define a `title`, which acts like a display name, when people are looking at your pack details.

```json
{
  "title": "Example"
}
```

Other metadata includes:

```json
{
  "description": "An example pack to demonstrate how to create a manifest",
  "author": "Fable Community",
  "image": "https://example.com/image.png",
  "url": "https://github.com/fable-community/example",
}
```

## Adding Media

Media, can be anything. Anime, manga, game, football leauge, boy band.

To add a media yo your pack it needs to be defined under `media.new`, like this: 

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

Check `manifest.json` file in this repo for all the details about the data that a media can have like `title`, `images`, `trailer`, `externalLinks`.

You media conflicts with some other pack's media but you don't want to straight out remove the other pack? Adding the conflicted media ids under `media.conflicts` like so, will disable those specific media while leaving the pack itself and its other content functional.

```json
"media": {
  "conflicts": [
    "anilist:145478",
    "anilist:118123",
  ],
},
```

## Adding Characters

To add characters yo your pack it needs to be defined under `characters.new`, like this: 

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

Check `manifest.json` file in this repo for all the details about the data that a character can have like `name`, `images`, `description`, `externalLinks`.

You characters conflicts with some other pack's characters but you don't want to straight out remove the other pack? Adding the conflicted character ids under `characters.conflicts` like so, will disable those specific characters while leaving the pack itself and its other content functional.

```json
"characters": {
  "conflicts": [
    "anilist:206017",
    "anilist:206013",
  ],
},
```

---

> Want a more serious/full example? Checkout the official vtubers pack manifest:  
> https://github.com/ker0olos/fable/blob/main/packs/vtubers/manifest.json
