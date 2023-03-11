# Example

When using a code editor like "VS Code" and adding:

```json
"$schema": "https://fable.deno.dev/schema.json",
```

You will be able to get helpful auto-completions and validation errors while writing your pack's manifest.

You can also run `/packs validate fable-community/example` or  
`/packs validate fable-community/example test-branch`
or from your terminal run
```sh
deno run -A https://raw.githubusercontent.com/ker0olos/fable/main/src/validate.ts ./manifest.json
```

Wanna try installing this pack instead? run `/packs install fable-community/example`

---

## Quick introduction

Start by picking an [id](https://github.com/fable-community/docs/blob/main/docs/schema.md#id) for your pack (be extra careful because chaning your id after people start using your pack is not allowed).

<img width="600" src="https://user-images.githubusercontent.com/52022280/224247611-be748894-d98a-4059-a13a-e7382cb846c9.png"/>

You can also define a [title](https://github.com/fable-community/docs/blob/main/docs/schema.md#title) (it appears when people are looking at your pack details instead of your pack's id).

<img width="600" src="https://user-images.githubusercontent.com/52022280/224247651-923e636e-9bfc-401d-a41e-b2111aa22c47.png"/>

Other metadata include:

<img width="600" src="https://user-images.githubusercontent.com/52022280/224247698-016b2a2b-bc02-4196-bfb2-11ea9e4a97d3.png"/>

Check the [docs](https://github.com/fable-community/docs) for more details.

> Want a more serious/full example? Checkout the official vtubers pack manifest:  
> https://github.com/ker0olos/fable/blob/main/packs/vtubers/manifest.json

## Adding Media

Media, can be anything. Anime, Manga, Video Games, Football Leauges, Boy Bands.

To add a media to your pack: it needs to be defined under `media.new`, like this: 

<img width="600" src="https://user-images.githubusercontent.com/52022280/224247721-4ddbc469-587f-41da-ad94-b2315fc36ed2.png"/>

Check [media.json docs](https://github.com/fable-community/docs/blob/main/docs/media.md) for all the details about the data that a media can hold: like `title`, `images`, `trailer`, `externalLinks`.

### Conflicts

Your media conflicts with another famous pack's media but you don't want to replace the other pack? Adding the conflicted media ids under `media.conflicts` like so, will disable those specific media while leaving the other pack itself and its other content functional. The format is like this `other-pack-id[:]conflicted-media-id`.

If you want to add a conflict from another pack use `/media [title] debug=True` with the debug flag as true Fable will print the full media id.

<img width="600" src="https://user-images.githubusercontent.com/52022280/224247747-cb4fe909-9f45-4549-b7a6-245ad3319544.png"/>

## Adding Characters

To add characters to your pack it needs to be defined under `characters.new`, like this: 

<img width="600" src="https://user-images.githubusercontent.com/52022280/224247769-14d3aa00-ce93-487f-aa6b-060639924e6e.png"/>

Check the `manifest.json` file in this repo for all the details about the data that a character can hold like `name`, `images`, `description`, `externalLinks`.

Check [character.json docs](https://github.com/fable-community/docs/blob/main/docs/character.md) for all the details about the data that a character can hold: like `name`, `images`, `description`, `externalLinks`.

### Conflicts

Your character conflicts with another famous pack's character but you don't want to replace the other pack? Adding the conflicted character ids under `characters.conflicts` like so, will disable those specific characters while leaving the other pack itself and its other content functional. The format is like this `other-pack-id[:]conflicted-character-id`.

If you want to add a conflict from another pack use `/character [name] debug=True` with the debug flag as true Fable will print the full character id.

<img width="600" src="https://user-images.githubusercontent.com/52022280/224247805-54785213-937e-4521-bd1a-d73323d94a24.png"/>
