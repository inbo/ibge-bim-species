# ibge-bim-species

Validation of species list of Brussels Environment Departement

## Appendix 1. Test connectivity

Test connection to database by following documentation in [test connectivity script](http://inbo.github.io/ibge-bim-species/test_connectivity.html) (Appendix 1). Please, be aware that connection to `ibge_dev` database is restricted and login credentials are needed.

## Workflow

The steps followed during validation are divided in a series of scripts:

1. [Get taxa](http://inbo.github.io/ibge-bim-species/get_taxa_from_db.html) from table `biodiv.taxon`.
2. [Find (un)used taxa](http://inbo.github.io/ibge-bim-species/detect_unused_taxa.html), i.e. taxa not mentioned as parents or in use in linked tables.
3. [Correct taxonomic information](http://inbo.github.io/ibge-bim-species/apply_corrections_names_by_ref_file.html) by reading reference file. See Appendix 2 to know how this file has been created.

## Appendix 2. Build reference file correcting taxonomic information

We build a reference file to correct taxonomic informations in order to improve match and provide description of the problems while matchin to GBIF Taxonomy Backbone. This is performed in a two-step procedure:

1. [Add kingdom]()`add_kingdom_detect_anomalies.Rmd`: add kingdom by following internal parent IDs where possible, detect anomalies (suspected duplicates)
5. `match_taxa_gbif_backbone.Rmd`: match taxa to [GBIF Taxonomy Backbone](https://www.gbif.org/dataset/d7dddbf4-2cf0-4f39-9b2a-bb099caae36c)



## Contributors

[List of contributors](https://github.com/inbo/ibge-bim-species/graphs/contributors)

## License

[MIT License](https://github.com/inbo/ibge-bim-species/blob/master/LICENSE) for the code and documentation in this repository.
