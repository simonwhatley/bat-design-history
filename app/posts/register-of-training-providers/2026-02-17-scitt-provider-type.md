---
title: SCITT provider type
description: We made SCITT a concrete provider type so the filter reflects what users see in the provider list
date: 2026-03-17
tags:
  - providers
  - provider types
  - filters
related:
  items:
    - text: Updating how we show provider type
      href: /register-of-training-providers/updating-how-we-show-provider-type/
    - text: Searching and filtering the list of training providers
      href: /register-of-training-providers/searching-and-filtering-the-list-of-training-providers/
---

We made school-centred initial teacher training (SCITT) a concrete provider type so the provider type filter matches what users see in the provider list.

## The problem

In the service, a SCITT was not a standalone provider type. Instead, it was derived from two attributes:

- provider type: school
- accreditation status: accredited

This caused a problem with the provider type filter. The filter did not include 'school-centred initial teacher training (SCITT)' as an option because the system treated SCITTs as schools. A user filtering by 'School' would see both schools and SCITTs, with no way to tell them apart.

There was a secondary problem: if a SCITT lost its accreditation, the system would reclassify it as a 'school'. This did not reflect the real-world identity of the provider.

We should not expose system complexity in the user interface. The filter needed to reflect what users actually see and understand.

## What we changed

We made SCITT a concrete provider type. A provider classified as a SCITT remains a SCITT even if it loses accreditation.

We updated the provider type filter to include 'School-centred initial teacher training (SCITT)' as an option. This matches the provider type label shown in each provider summary card in the results list.

## Further considerations

Non-accredited SCITTs should not exist in practice. If a SCITT loses its accreditation, it should be manually archived or have its provider type updated. We will look at how to surface this situation in the service so the right people are made aware.

*[SCITT]: School-centred initial teacher training
