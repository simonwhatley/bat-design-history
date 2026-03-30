---
title: Adding placement subjects to search results
description: We added a subject filter and subject information to placement school search results, using data from Register trainee teachers
date: 2026-03-19
tags:
  - search
  - filters
  - subjects
related:
  items:
    - text: Adding an academic years filter to the search results
      href: /register-of-placement-schools/adding-an-academic-years-filter-to-search-results/
    - text: Finding placement schools by location
      href: /register-of-placement-schools/finding-placement-schools-by-location/
    - text: Finding placement schools by provider
      href: /register-of-placement-schools/finding-placement-schools-by-provider/
---

Users searching for placement schools often need to find schools that have accepted placements for a specific subject.

Without a way to filter by subject, users have to check each school individually to see whether it is relevant to them. We added a subject filter to the search results and show subject information on each result.

## Why we did this

Users need to know which schools have accepted placements for the subjects they are recruiting for. Without subject information, they cannot quickly identify relevant schools. This means they may approach schools that have not accepted placements in their subject, or miss schools that have.

## How it works

### The subject filter

The filter uses the checkbox filter pattern. This is consistent with the other filters on the search results pages, such as school type, education phase and academic year.

The filter lists all allocation subjects from Register trainee teachers (RTT):

- Ancient languages
- Art and design
- Biology
- Business studies
- Chemistry
- Classics
- Computing
- Design and technology
- Drama
- Economics
- English
- French
- General sciences
- Geography
- German
- History
- Mathematics
- Modern languages
- Music
- Physical education
- Physics
- Primary
- Primary with mathematics
- Religious education
- Spanish

Because there are more than 15 subjects, the filter includes an inline search. Users can type in the search box to find subjects, rather than having to scroll through the full list. If JavaScript is not available, the list is still shown but without the search box.

The scroll area shows 4 and a half subjects at a time. This helps users understand that more subjects are available in the list.

When a subject is selected, it appears as a tag under 'selected filters' at the top of the filter panel.

### Subject information on each result

We show the subjects a school has accepted placements for on each result card. Subjects are listed in alphabetical order.

If a school has more than 3 subjects, the remaining subjects are collapsed inside a details component. Users can expand it to see the full list.

If a user filters by one or more subjects, all matching subjects are shown in the visible list. Any remaining subjects the school has accepted placements for appear inside the details component.

We show subjects below the education phase and above the placement details. This order matches the order of filters in the filter panel.

### Subjects on the placement school details page

We show subjects on the summary list on the individual placement school details page. They appear in the same position as on the results list: below education phase and above placement details.

## Further considerations

The subject list is based on allocation subjects from RTT. This list does not yet include all subjects available on Publish teacher training courses. Subjects that are missing include:

- Science
- Citizenship
- Communication and media studies
- Dance
- Health and social care
- Italian
- Japanese
- Latin
- Mandarin
- Philosophy
- Russian
- Social sciences
- Ancient Greek and Ancient Hebrew (Publish lists these separately rather than as Ancient languages)

We will add missing subjects to the list in the future. We need to consider how to handle differences in subject naming between services, for example whether to keep Ancient languages as a single option or split it into separate languages.

We need to conduct user research to understand whether the subject filter meets the needs of users searching for placement schools, and whether the way we display subjects on results gives them the information they need.

*[RTT]: Register trainee teachers
