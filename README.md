# Aviation Accident Safety Analysis

## Project Overview

This project analyzes aviation accident data for an airline or airplane insurer interested in understanding aircraft risk. The analysis focuses on identifying aircraft types with lower rates of total destruction and lower likelihood of fatal or serious passenger injuries.

The main safety outcomes used in this project are:

- Fatal or serious injury fraction
- Aircraft destruction rate

These metrics were used together because passenger injury severity and aircraft damage severity do not always tell the same story.

## Business Problem

The client wants to understand which aircraft makes and specific airplane types appear lower risk based on historical accident outcomes. This information can support underwriting, risk assessment, and insurance decision making by showing which aircraft groups have lower passenger injury severity and lower aircraft destruction rates.

To support that decision, this project compares accident outcomes by aircraft size, make, plane type, number of engines, and weather condition.

## Data Cleaning Summary

The original aviation accident dataset was cleaned before analysis. The cleaning process included:

- Filtering to professionally built airplanes
- Limiting the dataset to accidents from 1983 onward
- Creating a fatal or serious injury fraction
- Creating an aircraft destruction indicator
- Standardizing aircraft make and model names
- Combining make and model into a Plane.Type column
- Removing columns with very high missingness
- Saving a cleaned dataset for the analysis notebook

## Analysis Summary

The analysis separated aircraft into small aircraft and large passenger aircraft using a threshold of 20 estimated passengers. Aircraft with 20 or more estimated passengers were treated as large passenger aircraft, while aircraft below that threshold were treated as small aircraft.

The analysis compared aircraft makes and plane types using mean fatal or serious injury percentage and aircraft destruction rate. Additional variables, including number of engines and weather condition, were also reviewed to understand how other factors relate to accident severity.

## Key Findings

At the make level, Bombardier and Boeing appeared to be stronger large passenger aircraft candidates. Bombardier had a low destruction rate, while Boeing had a larger sample size and relatively strong results. McDonnell Douglas had a low injury rate but a higher destruction rate, so it was not treated as the strongest overall recommendation.

At the plane type level, Boeing's stronger performance was not spread evenly across all Boeing aircraft. The Boeing 777, 757, and 787 performed especially well, while the 737 and 737 800 had higher injury percentages. Bombardier CL 600 and Embraer EMB 145 variants also appeared to be strong regional jet candidates.

For smaller aircraft, Maule M 5 210C stood out in the plane type results. Stinson 108 1, Aviat A 1, Bellanca 7ECA, and Boeing A75N1 PT17 were also reasonable candidates, although smaller sample sizes should be considered when interpreting these results.

Number of Engines did not show a simple safety pattern. In this dataset, two-engine aircraft had worse outcomes than single-engine aircraft on both mean fatal or serious injury percentage and aircraft destruction rate, even though engine redundancy might seem like it would reduce risk. Three-engine and four-engine aircraft had lower severity rates, but those groups had much smaller sample sizes, so those results should be interpreted more cautiously.

Weather condition showed one of the clearest relationships with severity. In this dataset, accidents recorded under IMC had much higher fatal or serious injury percentages and destruction rates than accidents recorded under VMC.

## Recommendations

Based on the analysis, the strongest large passenger aircraft recommendations are:

- Boeing 777
- Boeing 757
- Boeing 787
- Bombardier CL 600 variants
- Embraer EMB 145 variants

For smaller aircraft, the strongest recommendations are:

- Maule M 5 210C
- Stinson 108 1
- Aviat A 1
- Bellanca 7ECA
- Boeing A75N1 PT17

These recommendations are based on historical accident records, so they should be used as risk assessment starting points rather than final underwriting decisions by themselves. The analysis does not account for aircraft availability, maintenance history, operating costs, pilot training, aircraft age, or total flight hours.

## Repository Structure

```text
.
├── Aviation_Accidents_Cleaning.ipynb
├── Aviation_Accidents_Data_Analysis.ipynb
├── data/
│   ├── AviationData.csv
│   ├── USState_Codes.csv
│   └── cleaned_aviation_data.csv
└── README.md