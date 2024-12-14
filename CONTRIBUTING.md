# Contributing to Canada Property Tax Rates

Thank you for your interest in contributing to the Canada Property Tax Rates project! This document outlines the guidelines for contributing to ensure a smooth and efficient collaboration.

## How to Contribute

1. Check the Progress
- Review the [table.csv](./table.csv) file to see which municipalities and years need data.
- Check the Issues tab on GitHub for tasks labeled help wanted or good first issue.

2. Add or Update Data
- Data should be added or updated in the appropriate `.ts` file, following the directory structure and file format described below.
- Add the years that you have completed to the [table.csv](./table.csv) along with a link to the source your data came from

3. Submit a Pull Request
- After making changes, submit a pull request (PR) for review.
- Ensure your PR follows the coding and formatting guidelines described below.

## Directory Structure

The `.ts` files in this repository use the [Geographic Unique Identifier (GEOUID)](https://www150.statcan.gc.ca/n1/pub/92f0138m/92f0138m2019001-eng.htm) to indicate the geographic scope of the data:

1. `rates.ts`: The root file. Contains data for all municipalities (a.k.a. census subdivisions (CSD)) across Canada. 
2. `RE/rates.[PRUID].ts`: Segmented by geographical region of Canada.
3. `PR/rates.[PRUID].ts`: Segmented by province and territory.
4. `CD/rates.[CDUID].ts`: Segmented by census division. Contains data for all municipalities within the census division.

### For Reference: 

#### PRUID
```
  10: Newfoundland and Labrador
  11: Prince Edward Island
  12: Nova Scotia
  13: New Brunswick
  24: Québec
  35: Ontario
  46: Manitoba
  47: Saskatchewan
  48: Alberta
  59: British Columbia
  60: Yukon
  61: Northwest Territories
  62: Nunavut
```

#### PRUID (Region)
```
  1: Atlantic
  2: Quebec
  3: Ontario
  4: Prairies
  5: British Columbia
  6: Territories
```

## File Format

Each file (e.g., rates.ts) exports an array of objects. Each object in the array represents a municipality and follows this schema:

```typescript
{
  id: string; // Dissemination Geography Unique Identifier (dguid)
  name: {
    en: string; // Municipality name in English
    fr: string; // Municipality name in French
  };
  province: string; // Province abbreviation (e.g., ON, QC, BC)
  rates: Array<{
    year: number; // Year 
    rate: number | undefined; // Property tax rate for the year or undefined if missing
  }>;
}
```

## Resources for contributors

1. Official Geographic Unique Identifier (GEOUID) Documentation -  [Geographic Unique Identifier (GEOUID)](https://www150.statcan.gc.ca/n1/pub/92f0138m/92f0138m2019001-eng.htm)
2. Wowa property tax data - [Wowa](https://wowa.ca/calculators/property-tax)