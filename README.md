# Crime-LA: Crime Patterns in Los Angeles

Exploratory analysis of reported crime data in Los Angeles, focusing on temporal patterns (time of day, nighttime crime) and victim demographics (age group), simulating a resource-allocation request for the LAPD.

![LA Skyline](la_skyline.jpg)

## Context

The LAPD needs to allocate policing resources efficiently across 21 geographic divisions. This project uses a modified version of the public Los Angeles Open Data to identify **when** and **where** crime is most frequent, and **who** the most affected victims are.

## Dataset

- **Source:** adapted version of [Los Angeles Open Data](https://data.lacity.org/)
- **File:** `crimes.csv`
- Columns: date/time of the crime, area/division, crime type, victim age/sex/descent, weapon used, location

## Methodology

- Extracted the hour of the crime from the military-time field (`TIME OCC`)
- Aggregated by hour and by geographic area (`groupby`)
- Binned victim ages into groups with `pd.cut`

## Key Findings

- **Peak hour:** the highest volume of crime happens at **12:00 PM (noon)**, with **13,663 incidents** — well above any other hour.
- **Nighttime crime (10 PM–4 AM):** the **Central** division leads with **3,312 incidents** during the night window, followed by 77th Street (2,558) and Hollywood (2,699).
- **Most affected age group:** **26–34 years old** is the most victimized group, with **47,470 victims**, followed by 35–44 (42,157). Minors (0–17) are the least affected group (4,528).

## Tech Stack

`pandas` · `numpy` · `matplotlib` · `seaborn`

## Possible Next Steps

- Cross-reference crime type with time/area for more targeted recommendations (e.g., "reinforce patrols in Central between 10 PM–2 AM for crime type X")
- Analyze trends across months/seasons of the year
