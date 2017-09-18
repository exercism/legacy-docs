# Maintainer Configuration

Each maintainer should be listed in the `config/maintainers.json` file.

This file is used for two purposes:

1. to update the maintainer team for the track repository using a bot
2. to (optionally) display maintainers on the website

## Maintainer Sync Bot

TODO: the bot is written, but not yet deployed/installed. Document this when the bot is turned on.

## Featuring Maintainers on Website

We feature the maintainers of each track on the website. Ideally, the maintainer bio will be tailored to the track, giving a friendly view into each maintainer's background and interest in the language, and even (perhaps) what they enjoy most about maintaining the track, or what type of things they tend to focus on.

The bio should be about 40 words long.

The main reasons for including these are to:

* provide a stronger basis for empathy with maintainers
* give well-deserved recognition
* plant a seed in people's minds that Exercism tracks are maintained by people like me... I could do that!

Being featured on the Exercism website is entirely optional, and we're generating all the data with `show_on_website=false` so that if you don't want to bother, you don't have to change anything.

## Alumnus

When you decide to move on, submit and merge a PR that sets the `alumnus` key
for your maintainer entry to one of the following strings:
`alumnum`, `alumnus` or `alumna`.
This is the string that will appear with your bio on the website. These terms
have been chosen to enable you to choose the one you feel most appropriate for
your gender.

## JSON Format

The format for each entry is:

```
{
  "github_username": "iHiD",
  "show_on_website": false,
  "alumnus": null,
  "name": "Jeremy Walker",
  "bio": "A friendly, detailed description of your background/interest in the language, to go on the Exercism track page.",
  "link_text": "My Website",
  "link_url": "http://ihid.co.uk",
  "avatar_url": "http://example.com/iHiD.png",
}
```

The only required field is `github_username`.

If `show_on_website` is missing or `false` then the maintainer will not be featured on the Exercism.io website.
- `show_on_website`

Optional fields:

- `alumnus`: defaults to null if absent.
- `avatar_url`: defaults to your GitHub avatar if `null` or absent.
- `name`: defaults to whatever your public display name on GitHub is. If you have not filled in this field, and there is no name defined on your GitHub profile, we will use your GitHub username as your display name.
- `bio`: if null or absent, it defaults to your public GitHub bio (note that I don't think this is a great default, I would much rather have a bio that is specific to the track). If this is an empty string we will not show a bio at all.
- `link_text`: no default. If absent we will use the `link_url` as the anchor.
- `link_url`: no default. If absent we will link to your GitHub profile.
