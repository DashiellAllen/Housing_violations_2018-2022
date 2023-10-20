# Analysis of Violations per Building in New York City — January 1st, 2018 - December 31st, 2022
This repository contains data, analytic code, and findings that support a portion of the Advanced Data class’ final project.

## Data
This analysis uses two spreadsheets that list Class B and C housing maintenance code violations from the New York City Department of Housing Preservation and Development (HPD). 

The spreadsheets come from [“Open HPD Violations” from NYC Open Data](https://data.cityofnewyork.us/Housing-Development/Housing-Maintenance-Code-Violations/wvxf-dwi5/explore/query/SELECT%0A%20%20%60violationid%60%2C%0A%20%20%60buildingid%60%2C%0A%20%20%60registrationid%60%2C%0A%20%20%60boroid%60%2C%0A%20%20%60boro%60%2C%0A%20%20%60housenumber%60%2C%0A%20%20%60lowhousenumber%60%2C%0A%20%20%60highhousenumber%60%2C%0A%20%20%60streetname%60%2C%0A%20%20%60streetcode%60%2C%0A%20%20%60zip%60%2C%0A%20%20%60apartment%60%2C%0A%20%20%60story%60%2C%0A%20%20%60block%60%2C%0A%20%20%60lot%60%2C%0A%20%20%60class%60%2C%0A%20%20%60inspectiondate%60%2C%0A%20%20%60approveddate%60%2C%0A%20%20%60originalcertifybydate%60%2C%0A%20%20%60originalcorrectbydate%60%2C%0A%20%20%60newcertifybydate%60%2C%0A%20%20%60newcorrectbydate%60%2C%0A%20%20%60certifieddate%60%2C%0A%20%20%60ordernumber%60%2C%0A%20%20%60novid%60%2C%0A%20%20%60novdescription%60%2C%0A%20%20%60novissueddate%60%2C%0A%20%20%60currentstatusid%60%2C%0A%20%20%60currentstatus%60%2C%0A%20%20%60currentstatusdate%60%2C%0A%20%20%60novtype%60%2C%0A%20%20%60violationstatus%60%2C%0A%20%20%60rentimpairing%60%2C%0A%20%20%60latitude%60%2C%0A%20%20%60longitude%60%2C%0A%20%20%60communityboard%60%2C%0A%20%20%60councildistrict%60%2C%0A%20%20%60censustract%60%2C%0A%20%20%60bin%60%2C%0A%20%20%60bbl%60%2C%0A%20%20%60nta%60/page/filter) downloaded with the following filters:
- `Housing_Maintenance_Code_Violations-6.csv`
  - Class: B and C only
  - Dates: 1/1/18-12/31/2022
- `Notable_buildings.csv`
  - Class: B and C only
  - Dates: 1/1/18-12/31/2022
  - BuildingID: IDs of Izsak/Rovt-owned buildings only
    - We obtained the building IDs from the 13 buildings owned by Robert Izsak and Max Rovt from [JustFix](https://whoownswhat.justfix.org/en/address/BROOKLYN/3030/OCEAN%20AVENUE/portfolio).

Each of the spreadsheets contain, among others, the following columns relevant to the analysis:
- ViolationID — Unique identifier of a violation against conditions in rental dwelling units and buildings.
- BuildingID — Unique identifier of a building.
- Class — Indicator of seriousness of the violations, where A is the least serious and C is the most serious.

**For the purpose of this analysis, we decided to use only the [Class B and C violations](https://www.lawhelpny.org/resource/hpd-violations-checklist) because they represent a greater hazard to the health and safety of tenants.**
- Class B violations are classified as hazardous and include but are not limited to:
  - Roaches or mice
  - Bedbug infestation
  - Mold on ceilings or walls
  - Cracks in tile floor, shower tub; defective wood floors
  - No smoke detector and/or carbon monoxide detector in apartment
  - Broken or defective cabinets, door handles, air ventilators  
- Class C violations are classified as immediately hazardous and include but are not limited to:
  - Holes in the wall/floor and rats/mice are coming in (especially if minors in the house)
  - No hot water (or not consistent).
  - No heat during the heating season.
  - Broken/defective faucets, shower, toilet (e.g., doesn’t flush)
  - Broken stove top, oven, refrigerator (doesn’t cool food)
  - Lead-based paint (if minor age 7 or younger)
  - No window guards (if minors in house).
  - No lock on an entrance door to the building.


## Findings
According to the analysis, the cumulative average number of class B and C HPD violations in NYC apartment buildings between 2018 and 2022 was **13.7**. However, there were large outliers - the maximum number of violations in a single building was 647, and 50% of buildings contained 4 or fewer violations.

The 13 buildings owned by Robert Izsak recorded an average of **45** class B and C HPD violations each, between 2018 and 2022.

**Compared to the citywide average, the buildings owned by Robert Izsak have more than three times the class B and C HPD violations of the city-wide average.**

## Methodology
The notebook `10-2023-building-violations-analysis.ipynb` performs two analyses:

**Part 1: Find the average number of violations per building in NYC.**
- Upload `Housing_Maintenance_Code_Violations-6.csv` to the Jupyter Notebook.
- Use the “GroupBy” function to view how many “ViolationIDs” (a unique ID tagged to every violation) were associated with each “BuildingID” (a single ID used for all violations in a building). 
- Use “describe” to view the average number of “ViolationIDs” per “BuildingID” (i.e. violations per building).

**Part 2: Find the average of violations for the 13 buildings owned by Robert Izsak and Max Rovt.**
- Upload `notable_buildings.csv` to the Jupyter Notebook.
- Use the “GroupBy” function to view how many “ViolationIDs” (a unique ID tagged to every violation) were associated with each “BuildingID” (a single ID used for all violations in a building). 
- Use “describe” to view the average number of “ViolationIDs” per “BuildingID” (i.e. violations per building).


## Outputs
The notebooks output this spreadsheet which contains both citywide and Izsak/Rovt-owned building averages for Class B and C violations: `TKTK-name-of-output-file`


## Running the analysis yourself
You can run the analysis yourself. To do so, you'll need the following installed on your computer: 
- Python 3
- Pandas, a Python library


## Licensing 
All code in this repository is available under the [MIT License](https://opensource.org/licenses/MIT). The data file in the output/ directory is available under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0) license. All files in the data/ directory are released into the public domain.


## Feedback / Questions? 
Contact [Dashiell Allen](dashiell.allen10@journalism.cuny.edu), [Deidre Foley](deidre.foley18@journalism.cuny.edu), [María Mónica Fernández](monica.fernandez262journalism.cuny), or [Génesis Dávila Santiago](g.davilasantiago06@journalism.cuny.edu).


