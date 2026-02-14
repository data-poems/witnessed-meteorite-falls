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
  - n<1K
---

# Witnessed Meteorite Falls - NASA Catalog

1,097 meteorites observed falling to Earth (1688-2013)

NASA meteorite catalog filtered to witnessed falls only. Unlike discovered meteorites, witnessed falls have documented fall dates, trajectories, and fresh samples uncontaminated by terrestrial weathering.

## Dataset Structure

[Check the demo notebook for data exploration examples]

## Usage

```python
from datasets import load_dataset

# Load the dataset
dataset = load_dataset("lukeslp/witnessed-meteorite-falls")

# Or load from local files
import json
with open('data.json') as f:
    data = json.load(f)
```

## Citation

```bibtex
@dataset{witnessed_meteorite_falls_2026,
  title = {Witnessed Meteorite Falls - NASA Catalog},
  author = {Steuber, Luke},
  year = {2026},
  url = {https://huggingface.co/datasets/lukeslp/witnessed-meteorite-falls}
}
```

## Author

**Luke Steuber**
- Website: [lukesteuber.com](https://lukesteuber.com)
- Bluesky: [@lukesteuber.com](https://bsky.app/profile/lukesteuber.com)
- Email: luke@lukesteuber.com

## License

CC0-1.0
