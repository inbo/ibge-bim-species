# ibge-bim-species (archived)

Validation of species list of Brussels Environment Departement. This project has been closed and the repository archived.

## Appendix 1. Test connectivity

Test connection to database by following documentation in [test connectivity script](https://github.com/inbo/ibge-bim-species/blob/master/src/test_connectivity.html) (Appendix 1). Please, be aware that connection to `ibge_dev` database is restricted and login credentials are needed.

## Improve parent ID 

### Workflow

The steps followed during validation are divided in a series of scripts:

1. [Get taxa](https://github.com/inbo/ibge-bim-species/blob/master/src/parentid_1_get_taxa_from_db.html) from table `biodiv.taxon`.
2. [Flag used taxa](https://github.com/inbo/ibge-bim-species/blob/master/src/parentid_2_detect_used_taxa.html), i.e. taxa mentioned in higher taxonomy or in use in linked tables.
3. [Correct taxonomic information](https://github.com/inbo/ibge-bim-species/blob/master/src/parentid_3_apply_corrections_names_by_ref_file.html) by reading a reference file. See Appendix 2 to know how this file has been created.
  4. [Match to GBIF Taxonomy Backbone](https://github.com/inbo/ibge-bim-species/blob/master/src/match_used_corrected_taxa_gbif.html).
  5. [Assign parent IDs](https://github.com/inbo/ibge-bim-species/blob/master/src/parentid_5_set_parentids_after_match_to_gbif.html) based on parent relationships in GBIF Backbone

### Appendix 2. Build reference file correcting taxonomic information

We build a [reference file](https://github.com/inbo/ibge-bim-species/blob/master/references/corrected_taxa.tsv) to correct taxonomic informations in order to improve match and provide description of the problems while matchin to GBIF Taxonomy Backbone. This is performed in a two-step procedure:

1. [Add kingdom](https://github.com/inbo/ibge-bim-species/blob/master/src/appendix_2_1_add_kingdom.html): add kingdom by following internal parent IDs where possible
2. [Match taxa to GBIF Taxonomy Backbone](https://github.com/inbo/ibge-bim-species/blob/master/src/appendix_2_2_match_taxa_gbif_backbone.html): try to match taxa to [GBIF Taxonomy Backbone](https://www.gbif.org/dataset/d7dddbf4-2cf0-4f39-9b2a-bb099caae36c) in three matching attempts with decreasing restrictions. A reference file with no exact matches is saved for check by experts.

## Contributors

[List of contributors](https://github.com/inbo/ibge-bim-species/graphs/contributors)

## License

[MIT License](https://github.com/inbo/ibge-bim-species/blob/master/LICENSE) for the code and documentation in this repository.
