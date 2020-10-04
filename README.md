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
`1.N.0` = version number, e.g. `1.0.0`
`buildid` = buildid hex -- this doesn't perform any function other than showing on the page, e.g. `7fc1baff976aeca4`
`item` = Slot 1 address for Player 1, e.g. `ABADD888`
`villager` = Villager addresses for replacing a villager on a Mystery Tour island. I only need the two, `0`, and `1`, where `0` is the first address that the second villager address is derived from, and `1` is the 3rd. Look at a villager code to see what I mean.
&nbsp;&nbsp;`curt` = this is the offset for the address used with "curt codes" to replace which villager shows up when using a curt amiibo.

If you need help with something I didn't explain well enough on here, or want access to this repo to help with updates, DM me.