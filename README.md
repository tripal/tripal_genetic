# Tripal Genetic

This repository is meant to house a best practices and API focused Tripal extension module in the future. Currently it is an indication of intent and a location to begin discussions on what is most helpful for this module to contain.

## Possible scopes / goals

Each of the following would be an optional submodule housed in this repository. In this way, we can combine maintainence efforts and work together to make a more cohesive set of tools while also ensuring that no specific Tripal site needs to enable any more functionality then they need to reduce bloat.

### 1. Provide an API for managing the genotype_call chado table.

There are multiple groups currently using the genotype_call table to manage their genotypic data (e.g. KnowPulse, TreeGenes/CartograPlant, MainLab consortium of Tripal sites). Each group has their own set of needs and materialized views for interacting with this table. The proposed API provided by this module would allow modules using it to define their needs and this module would provide materialized view sync functionality optimized for the large datasets typically handled by the genotype_call table.

### 2. Provide a Tripal importer for Genotypic data stored in VCF files.

There is currently a [Genotypes Loader](https://github.com/UofS-Pulse-Binfo/genotypes_loader) module developed and maintained by the University of Saskatchewan, Pulse Bioinformations group. There is potential for moving that module into this repository and the original developers are happy to take into account different data storage conventions when upgrading this module to Tripal 4.

### 3. Support for Genetic Maps and associated data.

There is a beautiful [Tripal Mapviewer](https://gitlab.com/mainlabwsu/tripal_map) module developed and maintained by Main Lab Bioinformatics. While this specific module is likely too complex for inclusion as a submodule here, it would be nice to provide a set of data storage best practice Tripal importers that are compatible with that tool. This submodule could also provide a place for Tripal fields related to genetic maps which are beyond the scope of TripalMap.

### 4. Create content types and provide Tripal Fields to enhance pages.

According to [Tripal Issue #281](https://github.com/tripal/t4d8/issues/281), core Tripal is considering removing the existing content typer creation and data type specific fields out to community-driven extensions focused on each data realm. This would be one such module. The current core Tripal Content Types we would look to take over creation of are:

| Category | Label                       | Term Name                   | Term Accession | Ontology |
|----------|-----------------------------|-----------------------------|----------------|----------|
| Genetic  | Genetic Map                 | Genetic map                 | data:1278      | EDAM     |
| Genetic  | QTL                         | QTL                         | SO:0000771     | Sequence |
| Genetic  | Sequence Variant            | sequence_variant            | SO:0001060     | Sequence |
| Genetic  | Genetic Marker              | genetic_marker              | SO:0001645     | Sequence |
| Genetic  | Heritable Phenotypic Marker | heritable_phenotypic_marker | SO:0001500     | Sequence |
