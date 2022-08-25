# Analysis of criminal court data from Austin, Dallas, Houston and San Antonio — 2019 to 2021

This repository contains data, analytic code, and findings that support portions of the article, “[Porch piracy: are we overreacting to package thefts from doorsteps?](https://www.theguardian.com/us-news/2022/aug/25/porch-piracy-package-thefts-doorstep-delivery),” published on August 25, 2022. Please read that article, which contains important context and details, before proceeding.

## Data

This analysis uses four spreadsheets obtained through public records requests from four district courts. Names and addresses (with exception of the values that indicate homelessness) have been removed from published data:
- Bexar county (San Antonio): [`data/bexar_county/R007531_-__RITM0071593_20150101_to_20210809.xlsx`](data/bexar_county/R007531_-__RITM0071593_20150101_to_20210809.xlsx)
- Dallas county (Dallas): [`data/dallas_county/PIA_243697_dataset.xlsx`](data/dallas_county/PIA_243697_dataset.xlsx)
- Harris county (Houston): [`data/harris_county/DATA - Vo.xlsx`](data/harris_county/DATA - Vo.xlsx)
- Travis county (Austin): [`data/travis_county/DataExport.xlsx`](data/travis_county/DataExport.xlsx) (felony), [`data/travis_county/LamVo_Criminal_Export_08232021.xlsx`](data/travis_county/LamVo_Criminal_Export_08232021.xlsx) (misdemeanor)


The data includes information about cases involving package theft and shoplifting. The penal codes used to request and filter these cases are listed in the [`data/requested_codes.csv`](data/requested_codes.csv) file and were sourced from two sites:
- package theft codes: https://www.dps.texas.gov/section/crime-records/appendix-k-offense-codes
- shoplofting codes: https://statutes.capitol.texas.gov/Docs/PE/htm/PE.31.htm, https://www.dps.texas.gov/administration/crime_records/docs/cjis/offenseCodesStatuteOrder.rtf


## Methodology

The notebook [`notebooks/01-all-crime-analysis.ipynb`](notebooks/01-all-crime-analysis.ipynb) performs the following analyses:

- loads data from five different sources and renames common columns so datasets can be combined. Common data values include unique ids ('case_id'), date of entry ('offense_or_input_date'), location of the alleged perpetrator ('street_name'), race of the alleged perpetrator  ('race'), and gender of the alleged perpetrator ('sex').
- filter data to just package theft and export it for reporting purposes
- summarizes data for each data set by race and by street address
- totals all felonies and aggregates them by street address

## Outputs

The notebooks output folder contains various analyses, including:
- [`output/overall_stats_cities.csv`](output/overall_stats_cities.csv): a tally of all package theft cases in all four cities
- [`output/packagetheft_summaries.csv`](output/packagetheft_summaries.csv): summaries of cases by city and by race of the alleged perpetrator
- [`output/recurring_addresses.csv`](output/recurring_addresses.csv): summaries of cases by city and by address of the alleged perpetrator, primarily produced to get a tally of homeless perpetrators


## Running the analysis yourself

You can run the analysis yourself. To do so, you'll need the following installed on your computer:

- Python 3
- The Python libraries specified in [`requirements.txt`](requirements.txt)

## Licensing

All code in this repository is available under the [MIT License](https://opensource.org/licenses/MIT). The data file in the output/ directory is available under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0) license. All files in the data/ directory are released into the public domain.

## Feedback / Questions?

Contact Lam Thuy Vo at lam.vo@journalism.cuny.edu.
