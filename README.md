# weather-app-assets

Weather app assets. Use as git submodule in the main app.

Add to new weather-app project

```
cd src
git submodule add https://github.com/[organization]/weather-app-assets assets
git commit -m "Added assets as a submodule"
```

Clone existing weather-app project with submodule

```
git clone --recurse-submodules https://github.com/[organization]/weather-app
```

## Scripts

Repository contains scripts to generate geolocations as json-file and some utility scripts for checking data in those files. Geolocation files in json-format are alternative for Smartmet Server geonames-database and may be used if geonames.org doesn't have good quality data for specific country. The default data source for geolocation data is Overture Maps https://overturemaps.org/ but scripts can be customized for local data sources.

### create_locations_json.sh

Generates `locations/locations.json` file in the format that the app understands. Following variables must be adjusted for local installations:

```
BBOX="19,59,32,71"
TIMEZONE="Europe/Helsinki"
COUNTRIES="AX,FI"
LANGUAGES="fi,sv,en"
```

### create_countries_json.sh

Generates `locations/countries.json` file in the format that the app understands. Following variables must be adjusted for local installations:

```
LANGUAGES="fi,sv,en"
```

### search_locations.sh

Searches location name in `locations/locations.json` file. Outputs results to console. For example:

`./search_locations.sh tampere`

### count_locations.sh

Calculates number of locations in `locations/locations.json` file and outputs result to console.
