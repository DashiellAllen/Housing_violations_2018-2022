# Housing_violations_2018-2022
Analysis of Violations per Building in New York City for 2022 data set — January 1st, 2022- December 31st, 2022

Data The spreadsheets come from the following sources:

Name of source: NYC Open Data, “Open HPD Violations” name_of_spreadsheet.xlsx: Notable Buildings Each of the spreadsheets contains, among others, the following columns relevant to the analysis:

Notable Buildings — This Google Sheet contains the 13 buildings owned by Robert Izsack and Max Rovt that were found in JustFixed. Inside this dataset, there can be found a tab called “Analysis_Per_Building.” Inside that tab, there is an analysis of the average number of violations that six of the buildings have.

Housing Violations NYC 2022 — This Jupyter Notebook contains the average number of violations per building in New York City for 2022.

Methodology
We want to The notebook Housing Violations NYC 2022 performs the following analyses:

Part 1: To get the average of violations per building in NYC we took the following steps:

Downloaded as .csv all violations from January 1 - December 31, 2022 from NYC Open Data. Created a jupyter notebooks file and uploaded the csv. Used the “GroupBy” python function to view how many “ViolationIDs” (a unique ID tagged to every violation) were associated with each “BuildingID” (a single ID used for all violations in a building). Used “describe” to view the average number of “ViolationIDs” per “BuildingID” (i.e. violations per building).

Part 2: In this part, the goal was to get an average of violations filed in 2022 still open in the six buildings with known cap rates owned by Robert Izsack and Max Rovt. To do that: We used the data from Just Fix/ Who Owns What to identify the properties Robert Izsack and Max Rovt own. Based on information shared by the Landlords group, we decided to establish our analysis on six of the 13 properties owned by Izcack and Rovt because their cap rates are available. Using this data portal, we identified the violations of each of the six properties by filtering the information with their Registration ID number. We downloaded the filtered information as a csv. We created a Google Sheets where we uploaded the six buildings with the number of violations

We created a pivot table and calculated the average for the six buildings, which was 32.5.

Outputs: N/A

Running the analysis yourself: You can run the analysis yourself. To do so, you'll need the following installed on your computer: Python 3 The Python libraries specified in requirements.txt

Licensing All code in this repository is available under the MIT License. The data file in the output/ directory is available under the Creative Commons Attribution 4.0 International (CC BY 4.0) license. All files in the data/ directory are released into the public domain.

Feedback / Questions? Contact: Dashiell Allen, Deidre Foley, María Mónica Fernández, or Génesis Dávila Santiago

A short paragraph with findings:

According to our Jupyter Notebook analysis based on NYC Open Data, the average number of violations per building for 2022 was 5.8. However, our Google Sheets [Notable Buildings/Violations_Per_Building] analysis shows that the six buildings with an identified cap rate owned by Max Rovt and Robert Izsak was more than six times higher than the average number of violations for 2022, with 32.5 violations per building.

