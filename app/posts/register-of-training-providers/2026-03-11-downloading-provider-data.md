---
title: Downloading provider data
description: We added links to download the provider list as a CSV or ODS file
date: 2026-03-11
tags:
  - providers
  - data
related:
  items:
    - text: Searching and filtering the list of training providers
      href: /register-of-training-providers/searching-and-filtering-the-list-of-training-providers/
    - text: Using CSV file format
      href: https://www.gov.uk/guidance/using-csv-file-format
    - text: Using Open Document Formats (ODF) in your organisation
      href: https://www.gov.uk/guidance/using-open-document-formats-odf-in-your-organisation
    - text: Creating and sharing spreadsheets
      href: https://www.gov.uk/guidance/creating-and-sharing-spreadsheets
screenshots:
  items:
    - text: Providers list
      src: downloading-data--providers-list.png
---

We added a way to download provider data as a CSV (comma-separated values) or ODS (open document spreadsheet) file.

## Why we did this

The Register of training providers holds data that other teams and services need to access and work with. Making data available for download means users can work with it in tools they already use, without needing direct access to the service or its API.

We chose to support both CSV and ODS formats because:

- CSV is a widely used, open format recommended by government for sharing data
- ODS is the open document standard endorsed by government for spreadsheets
- both formats work without proprietary software

## What we considered

### Simple download links

We added two simple download links next to the 'Add provider' button on the provider list page. This keeps the download action close to the data it relates to.

If a user has filtered the list, selecting a download link will download only the filtered results. This avoids the need for a separate filtering step within the download flow.

### Button menu component

We considered using the Ministry of Justice design system's button menu component. This would have combined both download options into a single 'Download data' button with a dropdown.

We decided against this because:

- it requires JavaScript to work
- it adds complexity that needs validation through user research and testing
- it depends on a third-party design system, unless we built our own version

### A download flow

We considered a multi-step download flow where users could choose the data type, apply filters, and select an output format. We decided this was too complex for a first iteration. We will consider it if research shows users need more control over what they download.

## How it works

Two download links appear on the provider list page, next to the 'Add provider' button:

- Download providers (CSV)
- Download providers (ODS)

Selecting a link immediately downloads a file to the user's device. We do not show an intermediate step.

### File naming

We name the file 'training-providers' followed by a timestamp. For example:

```text
training-providers-20260316-164503.csv
```

### Filtered downloads

If a user has filtered the provider list, the downloaded file contains only the filtered results. The filters include:

- provider type
- accreditation status
- academic year
- archived providers

### Data included in the files

The files contain the following fields:

| Field | Description |
| --- | --- |
| provider_id | The unique identifier (UUID) used by the service |
| operating_name | The provider's operating name |
| legal_name | The provider's legal name |
| provider_type | The type of provider |
| accreditation_status | The provider's accreditation status |
| ukprn | UK Provider Reference Number |
| urn | Unique Reference Number |
| provider_code | The provider code |
| academic_years | The academic years the provider is active |
| archived | Whether the provider has been archived |

## Limitations

Users cannot download different types of provider data in bulk, such as accreditations, addresses, or partnerships. They also cannot download data for individual providers.

We wanted to understand how users use this data before adding more options.

## Further considerations

- Adding a way to download accreditations, addresses, and partnerships
- Creating a download flow with more control over data type, filters, and output format
- Adding a way to download activity logs
- Processing files in the background if data volumes grow large, so users can return to download a generated file

*[API]: Application programming interface
*[CSV]: Comma-separated values
*[ODS]: Open document spreadsheet
*[ODF]: Open Document Format
*[UUID]: Universally unique identifier
*[UKPRN]: UK Provider Reference Number
*[URN]: Unique Reference Number
