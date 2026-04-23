# Google Search API Wrapper

Built this in 2022 for my own scripts. I wanted programmatic Google results as a second source: to verify what AI models were telling me, to cross-check, to feed agents their own search layer. Google's Custom Search JSON API was the cleanest path, but the setup is fiddly: stand up a Programmable Search Engine, get an API key, wire it up, parse the response. I wrapped all of that behind one `response()` call. Open-sourced it in 2024 alongside my AI toolkits.

Google's search API is still fiddly. This is still a nice option.

Python wrapper for Google's Custom Search JSON API. Text and image search.

## Install

```bash
git clone https://github.com/ramonclaudio/Google-Search-API-Wrapper.git
cd Google-Search-API-Wrapper
pip install -r requirements.txt
```

## Setup

1. Get an API key at the [Programmable Search Engine intro page](https://developers.google.com/custom-search/v1/introduction) ("Get a Key").
2. Create a Search Engine at the [Control Panel](https://programmablesearchengine.google.com/controlpanel/all). Pick specific sites or the entire web, enable image search if you want it.
3. Copy the Search Engine ID (`cx`) from the Overview page.
4. Put both in `.env` (or rename `example.env`):

```
api_key=your_api_key_here
cx=your_cx_id_here
```

## Usage

### Text search

```python
from google_search_api import GoogleSearchAPI

print(GoogleSearchAPI().response(method='text', max_results=5, query='Your query'))
```

### Image search

```python
from google_search_api import GoogleSearchAPI

print(GoogleSearchAPI().response(method='image', max_results=5, query='Your query'))
```

## License

MIT
