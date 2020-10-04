# ACNHCG-info
Animal Crossing New Horizons Code Generator version and offset information.

I've set up this repository to make it easier for trusted community members to update offsets for the code generator.

The generator can figure out most of the other codes on its own, it just needs initial offsets to seed its calculations. So a given section for a version `1.N.0` might look something like:

```json
  "1.N.0":{
    "buildid":"c0dec0dec0dec0de",
    "item":"CODECOD1",
    "villager":{
      "0":"CODECOD2",
      "1":"CODECOD3",
      "curt":"CODECOD4"
    }
```

And it's also totally cool to just leave off information you don't have like:

```json
  "1.N.0":{
    "buildid":"c0dec0dec0dec0de",
    "item":"CODECOD1"
```

**Legend**  
| Key | Description |
| ------------- | ------------- |
| `1.N.0`  | version number, e.g. `1.0.0`  |
| `buildid`  | buildid hex -- this doesn't perform any function other than showing on the page in the footer, and in the how-to for file naming, e.g. `7fc1baff976aeca4`  |
| `item` | Slot 1 address for Player 1, e.g. `ABADD888`  |
| `villager` | Villager addresses for replacing a villager on a Mystery Tour island. I only need the two, `0`, and `1`, where `0` is the first address that the second villager address is derived from, and `1` is the 3rd. Look at a villager code to see what I mean. |
| `curt` | this is the offset for the address used with "curt codes" to replace which villager shows up when using a curt amiibo. |
| `s1_to_s21` | This is the offset from Player 1, Slot 1, to Player 1 Slot 21. It's been `-B8` since 1.0.0 (as of 1.5.0), so this probably won't change. This is also used for all other players Slot 1 -> Slot 21 conversions. |
| `p1s1_to_p2s1` | This is the offset from Player 1 Slot 1 to Player 2 Slot 1 -- it used to be `-1DB10` since 1.0.0, but it looks like it's `76390` as of 1.5.0. |
| `p2s1_to_p3s1` | This is the offset from Player 2 Slot 1 to Player 3 Slot 1, and was also used to increment each other player -- it used to be `6D6D0` since 1.0.0, but it looks like it's `76390` as of 1.5.0, normalizing it with the slot 1 to slot 2 transition. |

If you need help with something I didn't explain well enough on here, or want access to this repo to help with updates, DM me.