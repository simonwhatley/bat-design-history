---
title: Emailing support users when something has changed
description: We added a way for support users to set up email notifications so they are alerted when provider data changes in the service
date: 2026-03-26
tags:
  - email notifications
  - your account
  - users
related:
  items:
    - text: Viewing 'Your account'
      href: /register-of-training-providers/viewing-your-account/
    - text: Managing individual email notifications on Manage teacher training applications
      href: https://becoming-a-teacher.design-history.education.gov.uk/manage-teacher-training-applications/managing-individual-email-notifications/
    - text: Managing individual email notifications on Publish teacher training courses
      href: https://becoming-a-teacher.design-history.education.gov.uk/publish-teacher-training-courses/managing-individual-email-notifications/
screenshots:
  items:
    - text: Your account - empty
      src: your-account--empty.png
    - text: "Step 1: Frequency of changes"
      src: frequency-of-changes.png
    - text: "Step 1: Frequency of changes with errors"
      src: frequency-of-changes--error.png
    - text: "Step 2: Types of changes"
      src: types-of-changes.png
    - text: "Step 2: Types of changes with errors"
      src: types-of-changes--error.png
    - text: "Step 3: Check your answers"
      src: check-your-answers.png
    - text: "Step 3: Check your answers with no emails"
      src: check-your-answers--none.png
    - text: Your account - completed
      src: your-account--complete.png
---

Support users need to know when provider data changes in the register. Without notifications, they have to check the service manually or rely on colleagues to flag changes. This makes it harder to ensure changes are correct and meet policy guidelines.

We added a way for support users to set up email notifications for changes to provider data. This is the first piece of work on email notifications in the service. Subsequent work will cover the content of the emails themselves.

## How it works

Email notifications appear in the 'Your account' section of the service, below the user's personal details.

If a user has not set up email notifications, we show a link labelled 'Set up email notifications'.

Setting up email notifications is a 3-step process:

1. Frequency of changes
2. Types of changes
3. Check your answers

### Step 1: Frequency of changes

We ask: 'How often do you want to get emails?'

Users select one option from:

- Once a day
- Once a week
- Each time a provider is updated (you may get more than one email a day)
- I do not want to receive emails

We use radio buttons because users can only select one option.

If a user selects 'Once a day' or 'Once a week', we send a digest email that summarises the changes made during that period.

If a user selects 'I do not want to receive emails', they skip the next step and go straight to check your answers.

### Step 2: Types of changes

We ask: 'What changes do you want to be notified about?'

Users can select one or more options from:

- Provider details
- Provider accreditations
- Provider addresses
- Provider contacts
- Provider partnerships
- Provider users

We use checkboxes because users can select more than one option.

We do not offer more granular options at this stage, for example 'Legal name', 'UK provider reference number (UKPRN)' or 'Accountable officer'. We need to test with users and understand what level of detail they need before adding more specific options.

### Step 3: Check your answers

The final step shows a summary list with:

- How often do you want to get emails?
- What changes do you want to be notified about?

The selected notification types are shown as a list. If the user selected 'I do not want to receive emails' on step 1, we show 'None' for the types of changes.

Users can change either answer before confirming, or cancel and return to their account.

## Design decisions

### Starting with broad notification types

We chose broad categories rather than field-level options because we do not yet have enough evidence to know what granularity users need. Starting broad reduces the risk of building options that users do not find useful. We can add more specific options once we understand user needs better through research.

### Digest emails for daily and weekly frequency

Users who receive individual notifications for every change may receive a high volume of emails if multiple providers are updated in quick succession. A digest approach groups changes together and reduces that burden, while still keeping users informed.

## Further considerations

We will use GOV.UK Notify to send emails.

We need to design the content of the emails that will be sent to users.

We need to consider email fatigue and whether the frequency and volume of notifications will be manageable for users.

We need to determine whether email is the right mechanism for alerting users to changes, or whether other approaches, such as in-service notifications, would better meet their needs.

We need to decide whether to default notification settings to opt-in or opt-out. Defaulting to opt-out would mean users receive emails unless they actively turn them off. There are GDPR implications to this decision that we need to understand before implementing.

We will likely include an unsubscribe link in the emails we send. This would deep-link to a page in the service where users can update or remove their notification preferences.

If we open the register to providers, we will need to consider whether and how providers are kept informed of changes to their own details.

In the future, some changes may require an approval process before they take effect, for example changes to a provider's legal name. Email notifications could play a role in supporting that workflow.

*[UKPRN]: UK provider reference number
*[GDPR]: General Data Protection Regulation
*[ITT]: initial teacher training
