---
license: cc0-1.0
task_categories:
  - feature-extraction
language:
  - en
tags:
  - meteorites
  - nasa
  - astronomy
  - space
  - geospatial
  - earth-science
  - observed-events
  - planetary-science
pretty_name: Witnessed Meteorite Falls - NASA Catalog
size_categories:
  - 1K<n<10K
dataset_info:
  features:
    - name: latitude
      dtype: float64
    - name: longitude
      dtype: float64
    - name: name
      dtype: string
    - name: description
      dtype: string
    - name: category
      dtype: string
    - name: date
      dtype: string
    - name: mass_g
      dtype: float64
    - name: meteorite_class
      dtype: string
    - name: fall_type
      dtype: string
  splits:
    - name: train
      num_examples: 1097
---

# Witnessed Meteorite Falls - NASA Catalog

1,097 meteorites observed falling to Earth from 1688 to 2013.

## What's Inside

- 1,097 witnessed falls (not discovered finds)
- 325 years of documented observations
- Precise fall dates and locations
- Petrologic classifications
- Mass where available

## Witnessed vs Found

Most meteorites are "finds" -- discovered long after landing. Witnessed falls make up about 3% of the catalog but have exact fall dates, documented trajectories, and minimal contamination from weathering.

## Filtering Criteria

- Fall type: "Fell" only
- Excludes: "Found" meteorites
- Reduces NASA catalog by 97.1%

## Date Range

| Metric | Value |
|--------|-------|
| Earliest | 1688 |
| Latest | 2013 |
| Span | 325 years |

## Record Structure

```json
{
  "latitude": 44.8833,
  "longitude": -93.2,
  "name": "Murchison",
  "description": "CM2 - 100000g",
  "category": "witnessed_meteorite_falls",
  "date": "1969-09-28",
  "mass_g": 100000,
  "meteorite_class": "CM2",
  "fall_type": "Fell"
}
```

## Notable Witnessed Falls

- Murchison (1969) -- Australia, CM2 carbonaceous chondrite, amino acids discovered
- Allende (1969) -- Mexico, CV3, oldest material in solar system
- Peekskill (1992) -- New York, caught on video hitting a car
- Chelyabinsk (2013) -- Russia, largest airburst since Tunguska

## Usage

```python
import json
import pandas as pd

with open('witnessed_meteorite_falls.json') as f:
    falls = json.load(f)

df = pd.DataFrame(falls)
print(f"Total witnessed falls: {len(df):,}")

# Find carbonaceous chondrites (rare, organic-rich)
carbonaceous = df[df['meteorite_class'].str.startswith('C', na=False)]

# Falls by century
df['century'] = (pd.to_datetime(df['date']).dt.year // 100) * 100
by_century = df.groupby('century').size()
```

## Source & License

Public Domain -- U.S. Government Work. Data from NASA Meteoritical Bulletin via Open Data Portal.

https://data.nasa.gov/Space-Science/Meteorite-Landings/gh4g-9sfh

## Distribution

- **Kaggle**: [lucassteuber/witnessed-meteorite-falls](https://www.kaggle.com/datasets/lucassteuber/witnessed-meteorite-falls)
- **HuggingFace**: [lukeslp/witnessed-meteorite-falls](https://huggingface.co/datasets/lukeslp/witnessed-meteorite-falls)
- **GitHub Gist**: [Demo Notebook](https://gist.github.com/lukeslp/795a4f4b59954b3f30f3b80a7c77a481)

## Author

Luke Steuber | luke@lukesteuber.com | @lukesteuber.com (Bluesky)

## Structured Data (JSON-LD)

```json
{
  "@context": "https://schema.org",
  "@type": "Dataset",
  "name": "Witnessed Meteorite Falls - NASA Catalog",
  "description": "1,097 meteorites observed falling to Earth from 1688 to 2013. Witnessed falls are scientifically valuable due to minimal contamination and known fall dates.",
  "url": "https://www.kaggle.com/datasets/lucassteuber/witnessed-meteorite-falls",
  "sameAs": "https://huggingface.co/datasets/lukeslp/witnessed-meteorite-falls",
  "license": "https://creativecommons.org/publicdomain/zero/1.0/",
  "creator": {
    "@type": "Person",
    "name": "Luke Steuber",
    "url": "https://lukesteuber.com"
  },
  "keywords": ["meteorites", "NASA", "astronomy", "witnessed falls", "planetary science", "geospatial"],
  "temporalCoverage": "1688/2013",
  "spatialCoverage": {
    "@type": "Place",
    "name": "Global"
  },
  "distribution": [
    {
      "@type": "DataDownload",
      "encodingFormat": "application/json",
      "contentUrl": "https://www.kaggle.com/datasets/lucassteuber/witnessed-meteorite-falls"
    }
  ]
}
```
