# Canada Property Tax Rates

This repository provides a directory of historical and current municipal property tax rates across Canada, covering the years 2000 to 2024.

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

## Progress

The repository is currently a work in progress. Please see [table.csv](./table.csv) for a detailed overview of the municipalities and years that have been completed.

## Contributions

Contributions are welcome! If you’d like to help expand this dataset:

1. Check `table.csv` for municipalities that need data.
2. Create or update a `.ts` file following the schema provided above.
3. Submit a pull request with your changes.

### Guidelines for Contributors

1. Ensure that data is accurate and sourced from reliable references.
2. Use `undefined` for years where the property tax rate is unavailable.
3. Format code to match the example provided.

## Usage

This repository can be used in applications or analysis projects involving historical and current municipal property tax rates. The TypeScript format makes it easy to integrate with JavaScript and TypeScript projects.

To use the data, import the rates from the relevant `.ts` file into your project:

```typescript
import rates from './rates.ts';

console.log(rates);
```

## License

This repository is licensed under the MIT License.

<a href="https://www.buymeacoffee.com/zacharywitt" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/lato-yellow.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

