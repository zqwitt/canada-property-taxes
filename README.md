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


# Taux d'imposition foncière au Canada

Ce dépôt propose un répertoire des taux d'imposition foncière municipaux historiques et actuels à travers le Canada, couvrant les années 2000 à 2024.

## Structure du répertoire

Les fichiers `.ts` de ce dépôt utilisent l'identificateur géographique unique (IDUGEO) pour indiquer la portée géographique des données :

1. `rates.ts` : Fichier racine. Contient les données pour toutes les municipalités (ou subdivisions de recensement (SDR)) du Canada.
2. `RE/rates.[PRIDU].ts` : Segmenté par région géographique du Canada.
3. `PR/rates.[PRIDU].ts` : Segmenté par province et territoire.
4. `CD/rates.[DRIDU].ts` : Segmenté par division de recensement. Contient les données pour toutes les municipalités dans la division.

### À titre de référence :

#### PRIDU
```
  10 : Terre-Neuve-et-Labrador
  11 : Île-du-Prince-Édouard
  12 : Nouvelle-Écosse
  13 : Nouveau-Brunswick
  24 : Québec
  35 : Ontario
  46 : Manitoba
  47 : Saskatchewan
  48 : Alberta
  59 : Colombie-Britannique
  60 : Yukon
  61 : Territoires du Nord-Ouest
  62 : Nunavut
```

#### PRIDU (Région)
```
  1 : Atlantique
  2 : Québec
  3 : Ontario
  4 : Prairies
  5 : Colombie-Britannique
  6 : Territoires
```

## Format des fichiers

Chaque fichier (par exemple, rates.ts) exporte un tableau d'objets. Chaque objet dans le tableau représente une municipalité et suit ce schéma :

```typescript
{
  id: string; // Identificateur unique des géographies de diffusion
  name: {
    en: string; // Nom de la municipalité en anglais
    fr: string; // Nom de la municipalité en français
  };
  province: string; // Abréviation de la province (par exemple, QC, ON, BC)
  rates: Array<{
    year: number; // Année 
    rate: number | undefined; // Taux d'imposition foncière pour l'année ou undefined si absent
  }>;
}
```

## Progrès

Ce dépôt est actuellement un travail en cours. Veuillez consulter [table.csv](./table.csv) pour une vue détaillée des municipalités et des années complétées.

## Contributions

Les contributions sont les bienvenues ! Si vous souhaitez aider à enrichir cet ensemble de données :

1. Consultez `table.csv` pour identifier les municipalités qui nécessitent des données.
2. Créez ou mettez à jour un fichier `.ts` en suivant le schéma indiqué ci-dessus.
3. Soumettez une pull request avec vos modifications.

### Directives pour les contributeurs

1. Assurez-vous que les données sont exactes et proviennent de sources fiables.
2. Utilisez `undefined` pour les années où le taux d'imposition foncière n'est pas disponible.
3. Formatez le code conformément à l'exemple fourni.

# Utilisation

Ce dépôt peut être utilisé dans des applications ou projets d'analyse impliquant des taux d'imposition foncière municipaux historiques et actuels. Le format TypeScript facilite son intégration avec des projets en JavaScript et TypeScript.

Pour utiliser les données, importez les taux du fichier .ts pertinent dans votre projet :
```typescript
import rates from './rates.ts';

console.log(rates);
```

# Licence

Ce dépôt est sous licence MIT License.
