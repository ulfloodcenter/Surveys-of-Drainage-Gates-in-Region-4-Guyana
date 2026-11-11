# Surveys of Drainage Gates in Region 4, Guyana (Version 1)

**Dataset documentation**  
**Resource authors:** Gregory Williams, Emad H. Habib, and Mohamed Morsy  
**HydroShare resource:** https://www.hydroshare.org/resource/fca1ca19b9f748a2b90cf38b2effe549

**Project support:** U.S. National Science Foundation, Award No. 2426270  
**Geographic coverage:** Region 4, Guyana

## 1. Overview and intended use

This resource provides a georeferenced inventory of drainage gates in Region 4, Guyana. It contains **67 point records** with structure identifiers, location information, number of openings, surveyed invert elevations, opening widths, and, where available, gate heights, road centerline elevations, and field observations. Some comments identify nonoperational structures, pumping infrastructure, or measurements requiring follow-up.

The inventory is intended to support drainage-system characterization, hydrodynamic and hydraulic model development, flood-risk assessment, infrastructure screening, and planning of future field verification. It is an infrastructure inventory, **not** a complete engineering design survey or a verified inventory of operational condition.

## 2. Data origin and preparation

The field surveys were **commissioned by the University of Louisiana at Lafayette research project and performed by contracted local surveyors in Guyana**. The survey information was subsequently assembled and made available by the research team in tabular (CSV) and geospatial (ESRI shapefile) formats.

Survey collection dates: April to June 2026

## 3. Files and data structure

The resource includes a CSV inventory and a point shapefile. A shapefile comprises several companion files, which must be kept together, including `.shp` (geometry), `.shx` (geometry index), `.dbf` (attributes), `.prj` (coordinate reference system), and `.cpg` (text encoding). A `.qmd` companion file is also included in the supplied set.

The supplied shapefile contains **67 point features**. The supplied CSV contains **67 rows**. Some shapefile fields are not represented in the simplified CSV; consult the shapefile for the additional fields and original comments. Field names may be truncated in the shapefile format.

## 4. Coordinate reference systems and elevations

- **Shapefile point geometry:** WGS 84 geographic coordinates, **EPSG:4326**, with longitude and latitude in decimal degrees, as specified by the `.prj` file.
- **Eastings and Northings attributes:** Projected coordinates in meters, **consistent with WGS 84 / UTM Zone 21N (EPSG:32621)** when compared with the shapefile point geometry. **Original survey CRS to be confirmed with the survey contractor.**
- **Vertical datum:** Surveyed elevation fields are reported in **meters relative to Georgetown Datum (mGD)**.

**Important for modeling:** Georgetown Datum is a vertical reference and should not be confused with the WGS 84 horizontal coordinate reference system. Before combining surveyed elevations with a DEM, terrain surface, tidal boundary, or hydraulic model, verify that the vertical references are compatible or establish a documented transformation. The datum definition, benchmark realization, and any offset to other vertical datums are **not supplied in this README**.

## 5. Attribute guide

The following fields are present in the supplied shapefile. Descriptions marked for confirmation should be checked against the original survey deliverable.

| Shapefile field | Description | Units / notes |
|---|---|---|
| `ID` | Sequential record identifier | Integer; 1–67 |
| `Type` | Gate identifier, e.g., G1 | Text; despite field name, appears to be an identifier rather than a structural classification |
| `Gate No` | Gate number | Integer; confirm distinction from `ID` |
| `No.` | Additional numbering from source survey | Integer; **meaning to confirm** |
| `NDC ID` | Named administrative area / NDC identifier | Text; abbreviation and coding convention to confirm |
| `Location` | Local place or location description | Text; not populated for all records |
| `Eastings` | Projected easting | Meters; consistent with EPSG:32621 |
| `Northings` | Projected northing | Meters; consistent with EPSG:32621 |
| `Doors/Open` | Number of gate doors/openings | Count; confirm whether value refers to installed openings or functioning openings |
| `Invert, mG` | Surveyed structure invert elevation | mGD; shapefile field name shortened |
| `Width, m` | Recorded gate/opening width | Meters; confirm whether per opening or overall structure width |
| `Height, m` | Recorded gate/opening height, where available | Meters |
| `Note` | Source survey notation or coded reference | Text; code meanings to confirm |
| `CL Road, m` | Road centerline elevation, where available | Presumed mGD; **confirm datum and exact meaning** |
| `Comments` | Field observations and surveyor comments | Text; includes condition and verification notes |
| `field_16`, `field_17` | Empty fields in supplied shapefile | No values; candidates for removal in a cleaned release |

The CSV uses some slightly different field labels, including `Doors/Opening` and `Invert, mGD`, and omits some shapefile attributes. **Users should not assume that the two formats contain identical columns.**

## 6. Completeness, uncertainties, and limitations

The inventory contains 67 records, but the coverage and detail vary among structures. In the supplied shapefile:

- Gate/opening heights are available for **6 of 67** records.
- Road centerline elevations are available for **10 of 67** records.
- Locality descriptions are missing for **32 of 67** records.
- Surveyor comments are present for **26 of 67** records.
- Some comments identify nonworking gates, associated pumping infrastructure, or values needing confirmation.

All 67 records have numerical entries in the invert-elevation and width fields. **A populated number should not be interpreted as independent verification:** at least some survey comments question specific dimensions or invert elevations. Review the original comments before using individual structures in model calibration or design decisions.

No comprehensive positional accuracy, vertical accuracy, benchmark documentation, survey date range, or independent quality-assurance report has been provided with this draft. The dataset should not be used as a substitute for site-specific engineering verification, especially for critical flood-control or operational decisions.

## 7. Recommended use in hydraulic and hydrodynamic modeling

For each structure used in a model, confirm its location, number of openings, opening dimensions, invert elevation, and operational configuration. Give particular attention to entries flagged in `Comments`. Reconcile the Georgetown Datum elevations with the model terrain and water-level boundary references. Where gate height or operational information is absent, document any assumptions made by the modeler.

The inventory does not, by itself, provide a complete representation of gate operation schedules, pump capacities, hydraulic coefficients, or all structure dimensions required for detailed hydraulic parameterization.

## 8. Versioning and citation

**Version 1** represents the initial public inventory. 
