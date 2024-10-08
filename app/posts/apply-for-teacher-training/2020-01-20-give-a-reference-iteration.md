---
title: Give a teacher training reference (iteration)
description: Simplifying the previous design.
date: 2020-01-20
tags:
  - references
screenshots:
  items:
    - text: Email sent
      src: 00-email-sent.png
    - text: Reference form
      src: 01-reference-form.png
    - text: Reference submitted
      src: 02-reference-submitted.png
    - text: Consent given for research
      src: 03-consent-given-for-research.png
    - text: No consent for research
      src: 04-no-consent-for-research.png
    - text: Decline to give reference
      src: 05-decline-to-give-reference.png
related:
  items:
    - text: Provider needs research playback
      href: https://docs.google.com/presentation/d/1CXI74doFP19PZ3gfWKOWNbcodeYa5q16DmEDGBmHBP4/
---

An [iteration on the initial design](/apply-for-teacher-training/give-a-reference), removing some of the unnecessary fields.

## User needs

{% from "user-need/macro.njk" import appUserNeed %}
{{ appUserNeed({
  description: "As a referee
I need to provide a useful reference
So that I can help the candidate with their application and get back to my day as quickly as possible"
}) }}

{{ appUserNeed({
  description: "As a candidate
I need to know that my referee does not want to give a reference
So that I can get another referee as quickly as possible to progress my application"
}) }}

## Hypotheses

### Avoid asking referees to confirm they’ll give a reference

The [previous iteration](/apply-for-teacher-training/give-a-reference) asks referees whether to confirm they want to give a reference after  they just clicked a link in the email to give a reference which prolongs the process.

If we let users confirm via the email
Then it’ll shorten the process for referees

### Avoid asking referees to confirm their relationship with candidate

The [previous iteration](/apply-for-teacher-training/give-a-reference#start-page) asks referees to confirm their relationship with the candidate. But this prolongs the process and is beyond MVP.

If we remove this question
Then it’ll speed up the process for referees

### Actively refusing to give a reference

Some referees may not want to, or be able to give a reference. This slows down the candidate’s application process.

If we let users tell us that they will not give a reference
Then we’ll be able to notify the candidate and get another referee quickly
We‘ll know this works when referees click the refuse link in the email and confirm their refusal

### One big text box for the reference

We do not have any evidence that referees and providers need anything more sophisticated or bespoke than a single text box. So for now, we’re just keeping parity with UCAS—albeit with a smaller box and lower word count.

We’re wary about asking explicitly if the candidate is safe to work with children. Providers liked this, but we need to be careful how we ask the question. The absence of the flag might be seen as reason alone to reject a candidate when really the referee did not know either way.

We also do not have enough confidence in the 1 to 10 scales, which providers described as ‘subjective’. A single box is the lowest risk.

If we let users enter everything into 1 big text box
Then we’ll be able to see what problems arise with referees and providers
We’ll know this works when providers successfully use the references given to make decisions

## Findings from providers

Providers use references to build an overall picture of candidates, validate application information and to comply with safeguarding requirements.

90% of providers rated the guidance we give to referees as ‘good’ or ‘excellent’,

> Very clear and concise and helps with decision on suitability for teaching

> Think it is a great guide. Nearly all the prompts that I would be looking for are there.

Providers need referees to clarify that candidates are safe to work with children to comply with safeguarding requirements. This was a noted omission.

Providers need references to be personalised and tailored to teacher training context to determine a candidate’s suitability to train to teach.

Providers need to validate that references are coming from an official source and so they do not have to follow up with the candidate or referee.
