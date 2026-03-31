---
title: Exploring giving providers access to the register
description: We explored what a provider-facing view of the service might look like, so providers can update their own details rather than communicating changes to DfE
date: 2026-03-30
tags:
  - providers
  - navigation
  - users
  - permissions
  - email notifications
related:
  items:
    - text: Adding a way for support to manage provider users
      href: /register-of-training-providers/adding-a-way-for-support-to-manage-provider-users/
    - text: Emailing support users when something has changed
      href: /register-of-training-providers/emailing-support-users-when-something-has-changed/
    - text: Managing support users
      href: /register-of-training-providers/managing-support-users/
    - text: Why we need a register of training providers
      href: /register-of-training-providers/why-we-need-a-register-of-training-providers/
    - text: Reorganising the layout of the provider pages
      href: /register-of-training-providers/reorganising-the-layout-of-the-provider-pages/
---

One of the key benefits of the register is that it maintains standardised, up-to-date data about training providers across the Becoming a teacher (BAT) service line.

Currently, only DfE support users can update provider data. This means providers must communicate any changes to their details to DfE, who then update the register on their behalf. This creates an administrative burden for DfE teams, delays updates reaching the services that consume the register's data, and relies on providers actively notifying DfE when things change.

We explored what a provider-facing view of the service might look like. The goal is to allow providers to check and update their own details directly, reducing DfE's administrative burden and helping ensure the register stays accurate and current.

This work is exploratory. We have built a prototype to investigate the approach but have not yet implemented it in the live service.

## Why we did this

When providers need to update their details, the current process requires them to contact DfE and ask support users to make changes on their behalf. This introduces several risks:

- updates can be delayed if the request is not acted on promptly
- details may change without providers realising they need to notify anyone
- support teams carry the ongoing burden of processing routine changes

If providers could update their own details directly, changes could be made quickly and accurately. This benefits not only the register itself, but the wider ecosystem of services that rely on the register's application programming interface (API) for up-to-date provider data.

## How it works

### Navigation

In the support section of the service, each provider has a secondary navigation that allows support users to move between different parts of a provider's record. The secondary navigation includes:

- provider details
- accreditations
- addresses
- contacts
- partnerships
- users
- activity log

For the provider-facing view, we promoted this secondary navigation to become the primary service navigation. Provider users would see the same sections, but with one change:

- 'Provider details' becomes 'Home', reflecting that this is the starting point for a provider's own view of the service

We also decided that only provider admins need to see the 'Users' and 'Activity log' sections. Removing these items for standard users reduces the number of navigation items and keeps the interface focused on the tasks most users need to complete.

### User roles and permissions

The provider-facing view introduces two roles: admin and user.

An admin can:

- view and change provider details, such as the legal name, UK provider reference number (UKPRN) and unique reference number (URN)
- manage accreditations
- manage addresses
- manage contacts
- manage partnerships
- view and manage users
- view the activity log

A standard user can:

- view provider details
- manage addresses
- manage contacts
- view partnerships and accreditations

We have kept the roles simple for now. Restricting edit access to sensitive provider details, such as the legal name and UKPRN, to admins reduces the risk of accidental or unauthorised changes to information that has downstream effects on other services. Changes to addresses and contacts are lower risk and can reasonably be managed by any user.

### Provider switcher

Some users belong to more than one training provider organisation. For example, a person might administer two or more providers.

To support this, we added a provider switcher. This sits below the GOV.UK header and above the service navigation. It shows the name of the provider the user is currently viewing, alongside a link to a page listing all the providers the user belongs to. From that page, the user can switch to a different provider.

The provider switcher means the entire service is scoped to the provider currently selected. Users do not need to specify which provider they are acting on during individual tasks, such as adding an address or managing a contact. This reduces the risk of users inadvertently making changes to the wrong provider.

## Design decisions

### Reusing the existing navigation structure

The secondary navigation that support users see when viewing a single provider already represents the logical structure of a provider's record. Rather than designing a new information architecture for the provider-facing view, we promoted this existing structure to become the primary service navigation.

This approach has several advantages. The sections are already well-defined and familiar to the team. Reusing this structure means provider users and support users share the same underlying model for how provider data is organised, which should make the service easier to maintain and explain.

### Showing fewer navigation items to standard users

We considered showing all navigation items to all users and using the interface itself to communicate what each user can and cannot do. However, showing sections that a user has limited access to could be confusing, particularly if standard users see 'Users' and 'Activity log' items they cannot interact with meaningfully.

Restricting these items to admins removes the clutter and keeps the navigation focused. Admins who manage users and monitor activity have a clear path to those sections.

## Further considerations

### Approval process

Some changes to provider data may need approval before they take effect. For example, a change to a provider's legal name has implications for other services and may require a support user to verify the change is correct.

We have not yet designed an approval process. We need to explore:

- which types of changes should require approval
- who approves changes and by what mechanism
- what happens to a provider's record while a change is pending
- how to communicate the outcome of an approval decision to the provider

### Email notifications

We recently designed a way for support users to receive email notifications when provider data changes. We need to consider whether provider users should also receive notifications when changes are made to their provider's record, including changes made by other users within the same provider.

Expanding notifications to provider users would help providers stay aware of changes and catch errors quickly. This supports the goal of a self-maintaining service where providers take an active role in keeping their data accurate.

### Access control and authentication

We need to decide how provider users will access the service. This includes choosing an authentication mechanism, managing how users are invited and onboarded, and handling edge cases such as users who have left an organisation or providers with no active users.

We recently added the ability for support users to create and manage provider user accounts, which is a precursor to opening the service to providers.

*[API]: application programming interface
*[BAT]: Becoming a teacher
*[DfE]: Department for Education
*[UKPRN]: UK provider reference number
*[URN]: unique reference number
