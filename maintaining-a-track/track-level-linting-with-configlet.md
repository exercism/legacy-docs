# Track-Level Linting With Configlet

If the `config.json` file is incomplete or broken, a lot of other things break.
To make things easier we made a small tool to help verify the config:
https://github.com/exercism/configlet#configlet

You can download the latest release from the releases page in the [configlet
repo](https://github.com/exercism/configlet/releases), or you can use the
`bin/fetch-configlet` command from the root of the language track repository,
which will make a guess at what operating system and architecture you have and
attempt to download the right one.

Verify the config by calling `bin/configlet .` (notice the dot). This says
_check the config of the language track that is stored right here).