# ibge-bim-species

Validation of species list of Brussels Environment



## Workflow

1. `test_connectivity.Rmd`: test connection with `ibge_dev` database (credentials needed)
2. `get_taxa_from_db.Rmd`: get all taxa from table `biodiv.taxon` and save them in [/data/input/taxa.tsv`](./data/input/taxa.tsv)
3. `add_kingdom_detect_anomalies.Rmd`: add kingdom by following internal parent IDs where possible, detect anomalies (suspected duplicates)
4. `occurrences_overview_anomalous_taxa.Rmd`: get overview about number of occurrences linked to anomalous taxa found in previous step
5. `match_taxa_gbif_backbone.Rmd`: match taxa to [GBIF Taxonomy Backbone](https://www.gbif.org/dataset/d7dddbf4-2cf0-4f39-9b2a-bb099caae36c)



## Contributors

[List of contributors](https://github.com/inbo/ibge-bim-species/graphs/contributors)

## License

[MIT License](https://github.com/inbo/ibge-bim-species/blob/master/LICENSE) for the code and documentation in this repository.