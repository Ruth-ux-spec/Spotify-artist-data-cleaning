# Spotify Artist Data Cleaning & Analytics

A data cleaning and analysis project using Python (pandas) on a messy, real-world dataset of global Spotify artists.

## Dataset
- *Input:* spotify_artists.csv (120 rows, 10 columns)
- *Output:* cleaned_spotify_artists.csv (106 artists)

## Problems in the raw data
- Numbers stored as text ("28797,6", "25,574.20", NA, null, ?)
- Inconsistent text (F / female / Female, US / USA / United States)
- Duplicate artists (21 Savage vs 21savage, Karol G vs KAROL G)
- Blank and junk rows, and missing stream values

## What I did
1. *Load and inspect:* loaded the CSV and normalized column names (lowercase, no spaces, underscores).
2. *Convert numbers:* turned messy strings into valid floats; placeholders became NaN; fixed two-digit years like '08.
3. *Standardize categories:* unified sex, country_of_origin, primary_genre and artist_type.
4. *Impute and deduplicate:* removed the junk row and 13 duplicates, then filled missing total streams using lead + feature streams, then the genre median, then the overall median. I also corrected the Bad Bunny record, because the duplicate rule had kept the wrong row.
5. *Summary and export:* produced summary analytics and saved the cleaned file.

## Key findings
- 106 artists, about 3.86 million million (3,863,894M) total streams
- Top 3: Drake, Taylor Swift, Bad Bunny
- R&B and Reggaeton have the highest average streams per artist
- The United States leads by country of origin
- Solo artists average more streams (about 37,762M) than groups (about 29,083M)

## Notes
- Missing totals were estimated, so imputed values are approximations, not real figures.
- Missing debut_year, lead_streams_m and feature_streams_m values were left as missing on purpose.

## Tools
Python, pandas, NumPy, Jupyter Notebook

## Files
- cleaned_spotify_artists.csv: cleaned dataset
- spotify_artists.csv: original raw data
- Jupyter notebook: all code for Tasks 1 to 5
