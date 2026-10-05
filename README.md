# Grimstat game data

Game data for [Grimstat](https://grimstat.com), built and ready to load. There is one file per game
system, and the app loads it by itself when it opens.

`index.json` names each game system's current file. Its `id` is the first twelve hex
digits of the SHA-256 checksum of the file's data, so the same data always has the same id. The app
downloads a file only when the device does not already hold that id.

## Sources

An 11th edition file is merged from three sources:

- Points come from [BSData/wh40k-11e-mfm](https://github.com/BSData/wh40k-11e-mfm), a daily copy of
  the online Munitorum Field Manual. The repository is MIT licensed.
- Unit sizes, wargear options and which leaders join which units come from
  [BSData/wh40k-11e](https://github.com/BSData/wh40k-11e). The repository states no licence.
- Datasheets, abilities, stratagems, enhancements and detachment rules come from Wahapedia's CSV
  export.

A 10th edition file is built from Wahapedia alone.

Powered by Wahapedia, https://wahapedia.ru. Wahapedia asks that this line travels with its data, so
it is repeated in every copy of this dataset.

The rules, points and names in these files are copyright Games Workshop. Warhammer 40,000 and all
associated marks are the property of Games Workshop Limited. This dataset is not affiliated with,
endorsed by, or sponsored by Games Workshop.

## How it is refreshed

Once a day, a workflow in the Grimstat repository runs `pnpm cli publish` and pushes the result
here. A file changes only when its data does. Nothing in this repository is written by hand.
