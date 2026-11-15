# Grimstat game data

Game data for [Grimstat](https://grimstat.com), built and ready to load. There is one file per game
system, and the app loads it by itself when it opens.

`index.json` names each game system's current file. Its `id` is the first twelve hex
digits of the SHA-256 checksum of the file's data, so the same data always has the same id. The app
downloads a file only when the device does not already hold that id.

`wh40k-11e/points-history.json` holds each datasheet's points at every Munitorum Field Manual
update since 17 Jun 2026. The app shows it on the datasheet and in Rising and falling.

## Sources

An 11th edition file is merged from four sources:

- Points come from the official Munitorum Field Manual at
  [mfm.warhammer-community.com](https://mfm.warhammer-community.com/en), read once a day.
- Datasheets, unit sizes, wargear options, abilities, stratagems, enhancements and detachment rules
  come from Wahapedia's CSV export. The core rules come from Wahapedia's core rules page.
- Datasheets that Wahapedia does not list, the detachments the points list shares between
  factions, and which enhancements each unit may take come from catalogues Grimstat keeps.
- The Dark Angels, Space Wolves and Blood Angels Legends datasheets come from the Legends faction packs, free PDFs on
  [warhammer-community.com](https://www.warhammer-community.com/en-gb/downloads/warhammer-40000/).
  Where a pack describes a datasheet, the characteristics, weapons and abilities of the catalogues
  stand, and the pack adds the composition, the loadout, the keywords, the Leader and Support units and the
  characteristics the catalogues lack.

The points history up to 14 Oct 2026 comes from an earlier copy of the Munitorum Field Manual, under
the MIT licence at the end of this page. After that it comes from the daily reading of the official
site.

A 10th edition file is built from Wahapedia alone.

Powered by Wahapedia, https://wahapedia.ru. Wahapedia asks that this line travels with its data, so
it is repeated in every copy of this dataset.

The rules, points and names in these files are copyright Games Workshop. Warhammer 40,000 and all
associated marks are the property of Games Workshop Limited. This dataset is not affiliated with,
endorsed by, or sponsored by Games Workshop.

## How it is refreshed

Once a day, a workflow in the Grimstat repository runs `pnpm cli publish` and pushes the result
to the `staging` branch. It reads every published tournament list against the staged data and the
data on `main`, and moves `main` on only when the staged data reads them as well. The app reads
`main`. A file changes only when its data does. Nothing in this repository is written by hand.

## Licence of the points history up to 14 Oct 2026

MIT License

Copyright (c) 2026 BSData

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
