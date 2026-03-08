---
name: upcoming-metal-concerts
description: Search for upcoming metal concerts and festivals by country, city, band, or genre using concerts-metal.com. Use when the user asks about upcoming metal shows, gigs, or festivals.
metadata: {"openclaw":{"emoji":"🤘","requires":{"bins":["python3"]}}}
---

# Upcoming Metal Concerts

Search for upcoming metal concerts and festivals worldwide via concerts-metal.com.

## Usage

```bash
python3 {baseDir}/events.py --country ES --city Valencia
```

## Command Options

- `--country` (optional): ISO country code (default: ES). Use `--list-countries` to see all supported codes.
- `--city` (optional): Filter by city name (case-insensitive, partial match)
- `--band` (optional): Filter by band name (case-insensitive, partial match)
- `--genre` (optional): Filter by genre (case-insensitive, partial match, e.g. "death", "black", "thrash", "metalcore")
- `--list-countries` (optional): Print supported country codes and exit

## Examples

```bash
# All upcoming metal concerts in Spain
python3 {baseDir}/events.py --country ES

# Metal shows in Valencia
python3 {baseDir}/events.py --country ES --city Valencia

# Death metal shows in Germany
python3 {baseDir}/events.py --country DE --genre "death"

# Find a specific band's shows in the UK
python3 {baseDir}/events.py --country GB --band "Kreator"

# List supported countries
python3 {baseDir}/events.py --list-countries
```

## Output

The script prints a JSON array to stdout. Each entry contains:

- `date`: Event date (YYYY-MM-DD)
- `name`: Event/tour name
- `bands`: Array of `{"name": "...", "genre": "..."}` objects
- `venue`: Venue name
- `city`: City name
- `url`: Link to the event page on concerts-metal.com

Present the results to the user as a readable table sorted by date. Include the band lineup and genres.

## Notes

- No API key required. Data is sourced from concerts-metal.com broadcast pages.
- Coverage is excellent for metal, punk, hardcore, and adjacent genres across 50+ countries.
