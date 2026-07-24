# data-scraping2

Scrapes the **List of brown dwarfs** table from Wikipedia and saves selected
columns to `dwarfstars.csv`. This is the scraping step of a small star-data
pipeline (scrape → merge → clean).

`scraperprojectpart2.py`:

1. Fetches <https://en.wikipedia.org/wiki/List_of_brown_dwarfs> with `requests`.
2. Parses the page with BeautifulSoup and selects one of the tables on the page
   (index `[7]`).
3. Extracts the star name and the distance, mass, and radius columns from each
   row.
4. Writes them to `dwarfstars.csv` with pandas.

## Requirements

- Python 3.x
- requests, beautifulsoup4, pandas

```bash
pip install requests beautifulsoup4 pandas
```

## How to run

Requires an internet connection (it fetches the live Wikipedia page):

```bash
python scraperprojectpart2.py
```

## Expected output

A file **`dwarfstars.csv`** written to the current directory, with columns:

```
,Dwarfstarsnames,distance,mass,radius
0,...,...,...,...
1,...,...,...,...
...
```

## Note

The script depends on the current structure of the Wikipedia page (it hard-codes
the table index `[7]` and column offsets). If Wikipedia changes the page layout,
the table index or column indices may need adjusting.
