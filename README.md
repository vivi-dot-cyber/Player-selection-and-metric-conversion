# Player-selection-and-metric-conversion
ArcPy script tool that extracts players by country and position, converts height/weight to metric units, and outputs cleaned feature classes for the latest season. Fully parameterized for ArcGIS Pro.
Overview
This project automates the process of selecting hockey players by country and position, converting height and weight into metric units, and exporting cleaned feature classes for further analysis. The script is fully parameterized for use as an ArcGIS Pro script tool, allowing users to select any roster dataset, country layer, and attribute fields without modifying the code.
This project demonstrates spatial selection, attribute filtering, data cleaning, and unit conversion using ArcPy.

# Key Features
- Selects the most recent season automatically
- Extracts players located within a target country
- Filters players by multiple positions
- Converts:
- Height (feet/inches → centimeters)
- Weight (pounds → kilograms)
- Creates separate output feature classes for each position
- Fully parameterized for ArcGIS Pro script tool use
- No hard‑coded paths or field names

# Write‑Up
This project required selecting hockey players based on country and position, converting height and weight into metric units, and exporting cleaned feature classes. I began by identifying the necessary fields and designing a workflow that could be reused with different datasets. To make the script tool flexible, I parameterized all inputs, including the geodatabase, roster layer, country layer, attribute fields, target country, and positions.
One challenge was ensuring the script always used the most recent season. I solved this by scanning the season field with a SearchCursor and selecting the maximum value. Another challenge was converting height stored as text (e.g., 6'2") into centimeters. I wrote a helper function to parse the string, convert feet and inches into total inches, and then convert inches to centimeters. Weight conversion from pounds to kilograms was handled similarly.
The script uses spatial selection to identify players located within the target country, then creates separate output feature classes for each position. Each output includes new fields for height in centimeters and weight in kilograms. The final script is fully reusable as an ArcGIS Pro script tool and does not rely on any hard‑coded paths or values.
