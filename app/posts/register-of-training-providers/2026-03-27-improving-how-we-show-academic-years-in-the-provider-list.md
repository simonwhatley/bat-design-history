---
title: Improving how we show academic years in the provider list
description: We updated the academic years shown on each provider result to use the same display pattern as other multi-value fields in the service
date: 2026-03-27
tags:
  - providers
  - academic years
  - provider list
related:
  items:
    - text: Adding academic year information to the provider list
      href: /register-of-training-providers/adding-academic-year-information-to-the-provider-list/
    - text: Adding academic years to the provider details page
      href: /register-of-training-providers/adding-academic-years-to-the-provider-details-page/
screenshots:
  items:
    - text: Providers list
      src: providers-list.png
    - text: Providers list - filtered
      src: providers-list--filtered.png
---

We updated how we show academic years on each provider result in the provider list.

## What we changed

Academic years are shown in reverse chronological order, so the most recent year appears first.

If a provider has more than 3 academic years, the remaining years are collapsed inside a details component. Users can expand it to see the full list.

If a user filters by one or more academic years, all matching years are shown in the visible list. Any remaining academic years the provider belongs to appear inside the details component.

Academic years appear at the end of the result summary list. This order matches the order of the filters in the filter panel.

## Design decisions

### Collapsing long lists

Some providers span many academic years. Showing all years by default would make result cards significantly longer and harder to scan. Collapsing years beyond the first 3 keeps cards compact while still allowing users to access the full list when they need it.

### Showing filtered years first

When a user filters by academic year, we show the matching years in the visible part of the list before collapsing the rest. This confirms to users that the filter has worked and surfaces the information most relevant to their search.
