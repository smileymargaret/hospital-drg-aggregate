# NYC Hospital Chargemaster: Data Aggregator
In the U.S., understanding health care costs is... complicated. This lack of understanding is driven by limited transparency around pricing for health care services and procedures.

In order to address the lack of transparency, the Federal governing body, the Center for Medicaid and Medicare Services (CMS), passed a mandate ordering hospital systems to make their Chargemasters publicly available on their websites. Chargemasters (Charge Description Masters) are list prices of how much the most common procedure or product costs within that hospital system on average, usually throughout a calendar year. 

Since the passage of this mandate, many hospitals have complied, but there is one substantial problem in making them usable: the Chargemasters are often hidden across countless hospital websites in a wide array of formats. 

## Project Description
Differing and hidden sources for hospital pricing makes it difficult, if not impossible, to understand and analyze hospital costs or  compare price options. The following project demonstrates how Python can be used to solve this persistent issue in healthcare.

This code provides an aggregator for these Chargemasters across 18 acute general hospitals in New York City and develops a readable output to have clean, accessible, and singular point of reference for service costs across hospitals.

Having this data aggregated together as a single dataset allows for data analysis and applications that can be used to inform individuals on the cost of care. This code provides high-level analysis and functions for search capabilities available with this data.

The aggregator pulls data from 18 acute care hospitals in the Bronx, Brooklyn, Manhattan and Queens within New York city. The data was pulled in August 2020 from the following hospital websites available in the `/data` path:
- Mount Sinai
- Mount Sinai Beth Israel
- Mount Sinai Brooklyn
- Mount Sinai Morningside
- Mount Sinai Queens
- Mount Sinai West
- Montefiore
- New York Presbyterian
- Bellevue
- Coney Island
- Elmhurst
- Harlem
- Jacobi
- Kings County
- Lincoln
- Metropolitan
- Queens
- Woodhull

The following code imports these files, cleans, standardizes (adding unified columns and headers), and merges them into a single source using the imported CMS industry standard MS-DRG code set (available in the `/data` path).

Because there are multiple options that may not be relevant to those utilizing the data, defined functions were created to allow for more accessible search within the aggregate categories as well as data analysis through plotting. 

## Dependencies
The Project is a Python based app, built on `Python 3.8.5`. Please install or update Python prior to utilizing.

The project also imports:
- `pandas` for data manipulation and cleaning
- `xlrd` for loading and reading data sources in Excel
- `csv` for writing to a CSV
- `gspread` to output to Google Spreadsheets
- `oauth2client` to connect to Google's API
- `numpy` for mathematical functions
- `matplotlib` for graphic capabilities

If you do not have these dependencies, please install them first with `pip install`.

## Usage
Standardize and aggregate NYC hospital pricing using the following industry standards:
- `DRG`: Diagnosis Related Group
- `DRG Description`
- `MS`: Medical or Surgical Setting
- `MDC`: Major Diagnostic Categories
- `MDC Description`

Output the aggregator as a spreadsheet in the following formats in the code below: 
- CSV
- Google Sheets: Please note, you must output the CSV first as Google Sheets reads them as the input, and activate the Google API to generate your credentials.

Search for price results using the following functions: 
- `borough_search()`: Provides cost estimates based on the borough inputted by the user
- `hospital_search()`: Provides cost estimates based on the hospital inputted by the user
- `procedure_search()`: Provides cost estimates based on the major diagnostic category or procedure inputted by the user
- `diagnosis_search()`: Provides filtered results for cost estimates based on the diagnosis inputted by the user

## Support
Contact the Author: Margaret Smiley (margaretcsmiley@gmail.com)

## Roadmap
This project and analysis paints a clear picture on the variance of hospital costs within New York. In order to apply this analysis and the tools provided, next steps include:
- Aggregating Chargemasters across the U.S.
- Making the data web accessible through API development
- Revising assumptions with help from subject matter experts and licensing, making the project open source

But making health care data accessible is only the first step in true price transparency; Understanding the underlying health care data is the crucial, and much more challenging task at hand. 

Hospital chargemasters only provide insight into the average listed price for their top Diagnosis Related Groups. Most patients seeking care are insured through different products that not only limit their out of pocket expenses, but also potentially limit the health care providers and hospitals they are able to access. Understanding this would take coordination with Health Insurance Companies, State, and Federal Government alike to make accurate assumptions.

Additionally, not all services or procedures are available or identifiable with Diagnosis Related Groups, let alone services or procedures provided outside of a hospital setting. For this, more advocacy and policy is needed to make health care data a publicly accessible asset.

## Contributing
There is no license for this project at this time, however, please contribute through a Pull Request and use by Forking!

## Authors and acknowledgment
Author: Margaret Smiley (margaretcsmiley@gmail.com)

Thank you to General Assembly, namely Carelton Smith, Candace Roberts, and Adam Ostrich for the tools and education to develop this project!

## Project status
Last updated by Author: August 27th, 2020
