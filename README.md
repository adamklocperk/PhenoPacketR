A unified toolkit for programmatically creating, annotating, and sanitizing GA4GH‑compliant phenopacket JSONs from Excel templates.

## Installation

``` r
# Directly from GitHub
remotes::install_url("https://github.com/adamklocperk/PhenoPacketR/releases/download/v0.1.3/PhenoPacketR_0.1.3.tar.gz")
```

## Quickstart - each patient as one .xlsx file

``` r
library(PhenoPacketR)

# 1. Create a phenopacket template
create_template()
```

...then fill in all the required data into the template. You can duplicate it as many times as you want, one for each patient.

``` r
# 2. Create the phenopackets from ALL .xlsx files in the in_dir directory,
# output them either into the working directory (default) or into the out_dir
create_phenopackets(
      in_dir = "PPs",
      out_dir = "PPs"
      )
```

## Quickstart - several patients in one .xlsx file

``` r
library(PhenoPacketR)

# 1. Create 3 phenopacket templates, one for general header data,
# one for phenotypic features, one for genomic interpretations
create_templates_tall()
```

...then fill in all the required data into the templates. Each patient/feature/variant/gene go on a new row.

``` r
# 2. Create phenopackets from your header template
create_phenopackets_tall()

# 2. Annotate with HPO-based phenotypes from the phenotypic feature template
annotate_phenomics_tall(
      in_xlsx = "phenopacket_phenotypic_template.xlsx"
      )

# 3. Annotate with genomic interpretations from the genomic variant template
annotate_genomics_tall(
      in_xlsx = "phenopacket_genomic_template.xlsx"
      )
```

## Quickstart - exporting existing phenopackets back to templates

``` r
library(PhenoPacketR)

# 1. Create a phenopacket template
create_populated_templates_from_phenopackets(
   pp_dir = "folder_with_phenopackets",
   out_dir = "fodler_to_which_we_save_the_templates"
)
```

...then you can edit those and use them for creation of updated phenopackets.

## Contributing

Please open issues or pull requests on [GitHub](https://github.com/adamklocperk/PhenoPacketR). Contributions and suggestions are welcome!

## License

GPL-3 © 2025 Adam Klocperk
