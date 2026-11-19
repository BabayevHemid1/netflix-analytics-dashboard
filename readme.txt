NETFLIX ANALYTICS — POWER BI PROJECT
Opening the Project and Saving as PBIX
Extract the entire ZIP archive. Do not rename the folders or change their relative locations.
Open Netflix.pbip using an up-to-date version of Power BI Desktop on Windows. If .pbip files are not recognized, go to File → Options and settings → Options → Preview features, enable Power BI Project (.pbip) save option, and restart Power BI Desktop.
Select Home → Refresh. This step is required because the project does not include a preloaded data cache. Data is loaded from the embedded CSV; no external file path or internet connection is required.
Select File → Save As → Power BI (*.pbix) and save the report as Netflix_Dashboard.pbix.
Report Pages
Overview: Key metrics, movie/TV show split, years added to the catalog, content ratings, and genres.
Country and Genre Analysis: Distinct countries and genres, titles with missing country information, and top-10 rankings.
Catalog: A list of titles with release year, type, content rating, duration, country, and date added.
Filters apply within each page and are not automatically synchronized across pages. Selecting a chart element filters other visuals on the same page. Top-10 rankings may display more than 10 entries when counts are tied.

Data and Calculations
7,787 distinct titles: 5,377 movies and 2,410 TV shows.
Movie share: 69.05%; TV show share: 30.95%.
118 known countries, 42 genres, and an average movie runtime of 99.3 minutes.
Release years: 1925–2021; dates added: January 1, 2008–January 16, 2021.
507 titles have missing country information; 10 titles have missing dates added. Data for 2021 does not cover the full year.
Country and genre fields are split by commas, and surrounding whitespace is removed. A title can belong to multiple countries or genres, so the sum of their counts may exceed the total catalog count.
Total titles are calculated using DISTINCTCOUNT(show_id). The “No information” category is excluded from the country count.
duration represents minutes for movies and the number of seasons for TV shows. These units are not averaged together.
rating represents an age/content classification, not an audience score or IMDb rating.
The dataset contains no sales, viewership, or revenue data; these metrics are therefore not included.
Data/NetFlix.csv is the original source copy. Editing this file does not automatically update the embedded data. To update the embedded data, modify the semantic model’s NetflixSource Power Query query.
DAX and Data Model
Netflix is the main table. The Countries and Genres bridge tables have many-to-one relationships with Netflix through show_id. Bidirectional filtering allows country and genre selections to filter titles.

Measures.dax contains all measures for reference; no separate import is required.

Validation and Limitations
Metrics have been compared against the source CSV. JSON syntax, Microsoft project file schemas, file references, model columns, and visual positions within page boundaries have been checked.

Windows and Power BI Desktop are not available in the environment used to generate this project. Opening the project, executing Power Query/DAX, interactive selections, and conversion to .pbix have therefore not been tested in Power BI Desktop in that environment.

The preview images and PDF are illustrative previews based on the same page layout, not screenshots captured from Power BI. Fonts and chart appearance may differ in Power BI Desktop.
