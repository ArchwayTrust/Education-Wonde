# Wonde Ingestion
Spark notebooks for ingesting education data from Wonde API. They're built for use in Fabric but should mostly be platform agnostic.

- Wonde API Reference (https://docs.wonde.com/docs/api/sync) 
- Requires API developer key from Wonde.
- If using Fabric recommend creating a workspace inside a Fabric capacity (you can turn F2 on and off to keep it cheap) and then setting up a "Bronze" lakehouse.

### /Notebooks/_Config.ipynb
Global parameters including storage locations and azure key vault path.
Also setup up imports and gets the API secret.

### /Notebooks/_WondeStructs.ipynb
Houses struct defintions for data coming out of Wonde API. These are often nested structures and need to be flattened before writing to delta.
- Currently only a small section of the student structure is in here for test purposes.

### /Notebooks/_WondeAPI.ipynb
Core function for getting data from the API

### /Notebooks/GetStudents.ipynb
Currently static and pulls data for one school. Flattens a struct and writes delta to datalake. Currently just overwrite.



