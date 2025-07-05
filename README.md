PhenoPacketR
================

A unified toolkit for programmatically creating, annotating, and
sanitizing GA4GH‑compliant phenopacket JSONs from Excel templates.

## Installation

``` r
# Directly from GitHub
remotes::install_url(
+     "https://github.com/adamklocperk/PhenoPacketR/releases/download/release/PhenoPacketR_0.1.0.tar.gz",
+     repos = NULL, type = "source"
+ )
```

## Quickstart

``` r
library(PhenoPacketR)

# 0. Create templates
generate_templates()

# 1. Create phenopackets from your header template
create_phenopackets("phenopacket_header_template.xlsx")

# 2. Annotate with HPO-based phenotypes from the phenotypic feature template
annotate_phenomics(in_xlsx = "phenopacket_phenotypic_template.xlsx")

# 3. Annotate with genomic interpretations from the genomic variant template
annotate_genomics(in_xlsx = "phenopacket_genomic_template.xlsx")

# 4. Sanitize against the latest HPO
sanitize_phenopackets(hpo_file = "hp_2025-05-06.obo")
```

## Contributing

Please open issues or pull requests on
[GitHub](https://github.com/adamklocperk/PhenoPacketR). Contributions
and suggestions are welcome!

## License

GPL-3 © 2025 Adam Klocperk
