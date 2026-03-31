---
title: Adding a way for support to manage provider users
description: We added a users section within each provider so support users can add and manage people who will access the register to administer provider details
date: 2026-03-23
tags:
  - users
  - providers
  - activity log
related:
  items:
    - text: Managing support users
      href: /register-of-training-providers/managing-support-users/
    - text: Managing API and support user accounts
      href: /register-of-training-providers/managing-api-and-support-user-accounts/
    - text: Emailing support users when something has changed
      href: /register-of-training-providers/emailing-support-users-when-something-has-changed/
screenshots:
  items:
    - text: Provider users list
      src: provider-users-list--empty.png
    - text: Add provider user - details
      src: add-provider-user--details.png
    - text: Add provider user - details with errors
      src: add-provider-user--details-with-errors.png
    - text: Add provider user - check your answers
      src: add-provider-user--check.png
    - text: Add provider user - check your answers (user already exists)
      src: add-provider-user--check-exists.png
    - text: Add provider user - success
      src: add-provider-user--success.png
    - text: View provider user (never signed in)
      src: view-provider-user.png
    - text: Change provider user - details
      src: change-provider-user--details.png
    - text: Change provider user - details with errors
      src: change-provider-user--details-with-errors.png
    - text: Change provider user - check your answers
      src: change-provider-user--check.png
    - text: Change provider user - success
      src: change-provider-user--success.png
    - text: View provider user (signed in)
      src: view-provider-user--signed-in.png
    - text: Change provider user - details
      src: change-provider-user--signed-in-details.png
    - text: Change provider user - check your answers
      src: change-provider-user--signed-in-check.png
    - text: Change provider user - success
      src: change-provider-user--signed-in-success.png
    - text: View provider user - related providers
      src: view-provider-user--related-providers.png
    - text: Delete provider user
      src: delete-provider-user.png
    - text: Delete provider user - success
      src: delete-provider-user--success.png
---

As a precursor to providers accessing the register to manage their own details, we added a way for support users to add and manage provider users within each provider.

## Why we did this

Provider users will eventually be able to sign in to the register to check and update their provider's details. Before we can open the register to providers, support users need a way to set up those accounts.

## Design decisions

We considered two options for where to manage provider users:

1. Extending the existing users section
2. Adding a users section within providers

**Option 1: Extend the existing 'Users' section**

The first option was to adapt the existing users section to accommodate all user types, including support users, API users and provider users.

The advantage of this approach is that all users would be managed in one place.

However, it had significant drawbacks:

We would need to adapt the interface depending on the type of user being added, and for provider users, add a way of assigning them to a specific provider. This would make the flow unnecessarily complex.

We would need to add a gate question asking for the type of user being added (provider, support or API). This would define the appropriate user flow and validation rules for each type. Support and API users must have a DfE email address. Provider users can have any valid email address because we do not know which domains providers use.

**Option 2: Add a users section within each provider**

The second option was to add a 'Users' section within each provider's pages.

This approach:

- simplifies adding a provider user. The support user navigates to the relevant provider and adds the user there
- allows us to add provider-specific attributes, such as a user role
- allows us to apply different validation rules. For example, provider users can have any valid email address, not just a DfE email address

The only drawback is that support users cannot see all provider users across the register in one place.

We chose option 2. This follows the approach taken by other services, such as Publish teacher training courses and Manage teacher training applications.

## How it works

### Adding a provider user

Adding a provider user is a 2-step flow.

#### Step 1: User details

The form includes:

- first name
- last name
- email address
- role

Role is currently limited to 2 options, shown as radio buttons:

- User
- Admin

We have kept the role options simple for now. We need to do user research to understand what different roles are needed and what permissions each role should have.

We validate all fields. If a field is left empty, we show the following error messages:

- 'Enter first name'
- 'Enter last name'
- 'Enter email address'
- 'Select role'

For incorrectly formatted email addresses, we follow the [GOV.UK Design System guidance on email address error messages](https://design-system.service.gov.uk/patterns/email-addresses/#error-messages).

Unlike the main users section, the provider users section accepts any valid email address format, including addresses from services such as Gmail or Hotmail. We may need to consider whether to restrict this further.

We prevent the same email address from being added to the same provider more than once.

#### Step 2: Check your answers

We show a summary list with:

- first name
- last name
- email address
- role

If the email address belongs to a user who already exists in the register, we show a message above the summary list:

> This user already exists and will be linked to this provider.

We show a warning message below the summary list:

> The user will receive an email letting them know you've added them to [provider name].

Users can change any of their answers or cancel before confirming.

### Users list

The users list page shows a table with the following columns:

- full name (linked to the user's details page)
- email address
- role
- status (displayed as a tag: teal if active, grey if inactive)

If there are no users, we show:

> There are no users for [provider name].

If there are more than 25 users, we show pagination.

### Viewing a user

The user details page includes a summary list with:

- first name
- last name
- email address
- role
- is the account active?

We show when the user last signed in, or if they have never signed in:

> User has never signed in.

Support users can:

- change a user's details if the user has never signed in. Once they sign in, their account is linked to DfE Sign-in and we can no longer update their name or email address
- change a user's role at any time
- deactivate a user's account
- delete a user's account

#### Related providers

We include a list of all related providers a user belongs to below the user's details. Support users can use this list to navigate between providers.

### Activity log

All changes to provider users are recorded in the activity log.

We show a summary card for each event. The summary card title is the user's full name, linked to their details page. If the user has been deleted, the link is not shown.

The summary card includes:

- first name
- last name
- email address
- role
- is the account active?

We show who made the change and when, for example:

> By Colin Chapman on 25 March 2026 at 3:45pm

In the global activity log, the summary card title links to the provider user. In the provider-level activity log, no summary card title is shown, following the same pattern used for other provider activity.

## Further considerations

### Inactivity and account deactivation

We are considering deactivating provider user accounts after 13 to 15 months of inactivity. The window is longer than for other user types because provider users may only sign in once a year. They do this to check that their details and partnerships are up to date. A shorter inactivity window could cause their accounts to be deactivated during normal use. We need to consider the security implications of this approach.

### Provider contacts and provider users

We considered whether to make provider contacts into provider users automatically. We decided against this because we want to keep a clear separation between two things: provider contact information and access to the register.

Provider contact information is used to communicate with providers. Access to the register is for people who administer provider data. Merging these concepts would complicate both, and contact details may belong to people who should not have administrative access.

### Notification settings for provider users

If we implement email notifications for provider users, we need to decide whether support users can manage those settings on behalf of a provider user. This could be useful if a provider user asks for help. However, it also raises questions about consent and transparency. We need to explore this further.
