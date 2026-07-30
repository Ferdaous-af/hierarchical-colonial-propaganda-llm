# Data documentation

The corpus used in this study was retrieved through the Impresso Media Monitoring of the Past platform using the query `Perdicaris`.

The initial research corpus comprises 360 newspaper items in French and German, published between 20 May 1904 and 2 March 1909. Following relevance classification, 305 items classified as `CORE` or `RELATED` were retained for the principal analysis.

## Access and redistribution

The complete newspaper texts are not redistributed through this repository. Access remains subject to the rights, licences, terms of use, and access conditions of Impresso and its contributing institutions.

This folder may contain:

- corpus identifiers;
- retrieval documentation;
- input-schema examples;
- legally redistributable derived data;
- aggregate analytical results;
- documentation required to reconstruct the corpus.

This folder must not contain:

- API credentials;
- private or personal information;
- unauthorized copies of newspaper articles;
- restricted OCR files;
- copyrighted images without permission.

## Suggested input schema

A minimal input table may contain the following fields:

| Field | Description |
|---|---|
| `item_id` | Stable item identifier |
| `newspaper` | Newspaper title |
| `date` | Publication date |
| `language` | Source language |
| `title` | Article title |
| `text` | Article text, where redistribution is permitted |
| `source_url` | Authorized source link |
| `country` | Newspaper country |

Document any changes to retrieval criteria, corpus composition, exclusions, or preprocessing before rerunning the workflow.
