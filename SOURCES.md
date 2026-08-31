# Data Sources & Methodology

This document records the provenance and interpretation rules for **Indian Parliament Infographic**. It is intentionally conservative: a published government website is treated as a reference source, not as automatic permission to reproduce every page, image, PDF, graphic, logo, or compilation.

## Current application

The current application is a static Lok Sabha visualization. Its data is embedded in the application rather than maintained as a separate, versioned dataset with machine-readable provenance metadata.

As the project expands, every maintained dataset should record at least:

| Field | Purpose |
| --- | --- |
| `sourceUrl` | Official or otherwise authoritative location from which the data was obtained or validated |
| `retrievedAt` | Date/time when the source was accessed |
| `asOf` | Date the dataset is intended to represent |
| `coverage` | House, session, election, or population covered |
| `notes` | Important interpretation or normalization details |

## Primary reference sources

The following official Digital Sansad resources are the preferred starting points for validating parliamentary membership information:

- Lok Sabha member information: https://sansad.in/ls/ipg/list-of-members
- Rajya Sabha member directory: https://sansad.in/rs/members
- Rajya Sabha terms: https://sansad.in/rs/termsAndConditions
- Digital Sansad copyright/privacy information: https://sansad.in/rs/privacyPolicy
- Parliament Digital Library copyright policy: https://eparlib.sansad.in/help/copyright-policy.jsp

These links are reference sources for validation and future data ingestion. They should not be interpreted as evidence that all content hosted on those sites may be copied into this repository without restriction.

## Facts vs derived statistics

### Source-backed facts

Examples include member names, parties, states/UTs, constituencies, term information, and other attributes explicitly published by an authoritative source.

### Derived statistics

Examples include party seat shares, rankings, percentages, totals, comparisons, distributions, and other values calculated from the application's dataset.

Derived values should be labelled as calculated rather than presented as directly sourced facts. The calculation should be reproducible from the underlying dataset where practical.

## Data freshness

A parliamentary visualization should never imply that its data is permanently current.

When a dataset is refreshed, record both:

1. **Retrieved date** — when the source was accessed.
2. **As-of date** — the point in time that the dataset represents.

A future structured-data implementation should expose this information in the application UI and repository metadata.

## Normalization policy

Official naming should be preserved for factual display where practical. Normalized names may be used for filtering, grouping, or consistent internal identifiers, but normalization should not silently change the underlying fact.

Missing information should remain missing rather than being guessed or inferred without a documented basis.

## Reuse and copyright checks

Before adding externally sourced assets or data to the repository:

- Verify the source and provenance.
- Check the source's copyright/reuse policy.
- Record attribution where required.
- Confirm that photographs, logos, graphics, PDFs, and other protected materials are permitted for the intended use.
- Prefer linking to official material rather than copying it when reuse rights are unclear.
- Keep original project code clearly separated from third-party content.

The fact that information is publicly accessible does not by itself establish unrestricted reuse rights.

## Independent project disclaimer

**Indian Parliament Infographic is an independent visualization project. It is not an official Parliament of India, Lok Sabha, Rajya Sabha, or Digital Sansad product.**

## Future dataset record template

When Rajya Sabha or other structured datasets are introduced, add a record following this pattern:

```text
Dataset: <name>
House/Coverage: <scope>
Source URL: <official source>
Retrieved At: <YYYY-MM-DD>
As Of: <YYYY-MM-DD>
Validation: <how records were checked>
Notes: <normalization, exclusions, or caveats>
```

## Correction policy

Potential data errors should be traceable to a source. A correction should identify the affected field, the authoritative source used to validate it, and the date of verification.
