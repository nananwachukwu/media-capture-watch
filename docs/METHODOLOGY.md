# Methodology

## Data Collection

This dataset was compiled through systematic review of publicly available information about Big Tech and AI companies' funding relationships with journalism and media organizations.

### Sources

Primary sources include:

- **Trade publications:** Digiday, Press Gazette, Nieman Lab, Columbia Journalism Review
- **Academic research:** Tow Center for Digital Journalism (CJR), Reuters Institute
- **Industry databases:** CB Insights, AI Watch Dog, aiwatch.dog/licensing
- **Official announcements:** Company press releases, blog posts, and SEC filings
- **Grant databases:** Lenfest Institute, American Journalism Project, Google News Initiative

### Inclusion Criteria

A deal is included if it meets ALL of the following:

1. Involves a technology or AI company as the funder/partner
2. Involves a journalism or media organization as the recipient
3. Has been publicly reported or announced
4. Can be verified through at least one credible source

### Data Fields

| Field | Description | Notes |
|-------|-------------|-------|
| Company | The tech/AI company | Must be publicly identified |
| Program | Name of the deal or initiative | Official name where available |
| Type | Category of deal | Content License, Grant, Revenue Share, etc. |
| Amount | Financial value | "Undisclosed" when not publicly known |
| Year | Year deal was announced or became active | Integer |
| Recipients | Media organizations involved | Comma-separated |
| Description | Brief summary | Factual description |
| AI-Related | Whether deal is connected to AI products | Boolean |
| Source | URL to public reporting | Required for all entries |

### Limitations

- **Undisclosed amounts:** Many deals, particularly content licensing agreements, do not have publicly disclosed financial terms. These are included with qualitative descriptors.
- **Completeness:** This dataset captures major publicly reported deals but is not exhaustive. Private arrangements, informal partnerships, and deals that haven't been reported are not included.
- **Categorization:** Some deals span multiple categories. We assign the primary category based on the dominant characteristic of the arrangement.
- **Temporal accuracy:** Some deals are announced in one year but become active in another. We use the announcement year.
- **Geographic bias:** The dataset has stronger coverage of US, UK, and European deals due to English-language source availability.

### Updates

The dataset is updated on a rolling basis as new deals are reported. Each update is tracked via git commit history. Community contributions are welcome via GitHub issues or pull requests.

### Contact

For questions about methodology, corrections, or to contribute data, please open a GitHub issue.
