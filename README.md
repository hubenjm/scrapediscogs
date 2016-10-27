# scrapediscogs.py
Music SQL database builder and query framework based on the discogs API.

This is a relatively simple module that defines the MusicDatabase object, which interfaces with the database on www.discogs.com.
The main use is to provide a way to analyze one's own music collection.
It is simple to read in a text file containing the artist name and album title for a collection of albums in csv format.
The ```MusicDatabase.add_data(input_file_location)``` routine goes through each line of the text input and searches www.discogs.com using their Python API.
It then scrapes the different meta data for the given album and populates an SQL database using sqlite3.

Once the database has been constructed, the user can then run standard SQL queries on the data.

# Instructions

To get started, you must obtain a token ID in order to make queries to www.discogs.com through their API. To do this, see https://www.discogs.com/developers/#page:authentication,header:authentication-request-token-url.
Essentially, you need to register an account there and then go to https://www.discogs.com/settings/developers.

# Design

All of the core functionality is included in the file scrapediscogs.py.

# Usage

```
from scrapediscogs import MusicDatabase
x = MusicDatabase(db_location)
x.add_data(album_list_location)
for a in x.find_album(album_title):
  print a
```

# Future

* Clean up, turn into bonafide app, and submit to PyPi
