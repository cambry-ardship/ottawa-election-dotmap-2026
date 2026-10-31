# Ottawa's 2026 mayoral vote

An animated dot map of every vote cast in Ottawa's 2026 mayoral election, placed in the voting place it came from.

Each voting place's dots match its official totals (rounded to the dot size). Which household voted which way is unknown, so dots keep swapping colours with others in their voting place. Zoomed out, the map switches from 1 dot = 1 voter through coarser levels to hexagons.

## How it's built

- **Results:** City of Ottawa 2026 Statement of Votes Cast, by voting place. Ward advance votes are spread over each ward's voting places, and citywide special advance and mail-in votes over all voting places, in proportion to each candidate's election-day votes.
- **Placement:** residential buildings from the Statistics Canada National Address Register (June 2026) are assigned to the City's 2026 voting subdivisions; each voting place's votes are placed at its buildings in proportion to their residential units.
- **Front end:** MapLibre GL JS, deck.gl (colour fades computed on the GPU in OKLab), and a Protomaps basemap.

## Running locally

The basemap needs HTTP range requests, which Python's built-in server doesn't support. Use the included server:

```
python3 serve.py 8000
```

then open http://localhost:8000/.

## Sources and licences

- Contains information licensed under the [Open Government Licence – City of Ottawa](https://ottawa.ca/en/city-hall/open-transparent-and-accountable-government/open-data#open-data-licence-version-2-0) (election results, voting subdivisions).
- Adapted from Statistics Canada, National Address Register. This does not constitute an endorsement by Statistics Canada of this product ([Statistics Canada Open Licence](https://www.statcan.gc.ca/en/reference/licence)).
- Basemap © [OpenStreetMap](https://openstreetmap.org/copyright) contributors, via [Protomaps](https://protomaps.com).
