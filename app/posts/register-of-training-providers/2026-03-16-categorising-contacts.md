---
title: Categorising contacts
description: We added a 'Role' field to the contact form so contacts can be categorised and used in the right context
date: 2026-03-16
tags:
  - contacts
  - providers
related:
  items:
    - text: Managing provider contacts
      href: /register-of-training-providers/managing-provider-contacts/
    - text: Making contact phone number optional
      href: /register-of-training-providers/making-contact-phone-number-optional/
screenshots:
  items:
    - text: Add contact form
      src: categorising-contacts--add-contact.png
    - text: Add contact form - with errors
      src: categorising-contacts--add-contact-with-error.png
    - text: Add contact form - with errors (other role)
      src: categorising-contacts--add-contact-with-error-other-role.png
    - text: Add contact - Check your answers
      src: categorising-contacts--add-contact-check-your-answers.png
    - text: Contacts list
      src: categorising-contacts--contacts-list.png
    - text: Edit contact form
      src: categorising-contacts--edit-contact.png
    - text: Edit contact form - with errors (other role)
      src: categorising-contacts--edit-contact-with-error-other-role.png
    - text: Edit contact - Check your answers
      src: categorising-contacts--edit-contact-check-your-answers.png
---

We added a 'Role' field to the contact form so contacts can be categorised.

## Why we did this

Provider contacts have little value if other services cannot identify which contact to use in a given context. Without categorisation, there is no way to distinguish between an admissions contact and a technical contact.

For example, Publish teacher training courses needs an admissions contact to display on course pages. Without a role, there is no way to know which contact to use.

## How it works

We added a 'Role' question to the end of the contact form.

The question has 3 default options:

- Accountable officer
- Admissions officer
- Technical contact

There is also an 'Another role' option. When a user selects it, we use a conditional reveal to show a text input where they can enter a custom role name.

If we see a common role being added through 'Another role', we will add it to the default list.

### Displaying the role

On the check your answers page and the contacts summary list, we label the field 'Role'.

If a user selects a default option, such as 'Accountable officer', we show that role name.

If a user selects 'Another role' and enters a custom role name, we show only the role name they entered. We do not show 'Another role - [role name]'. 'Another role' is a mechanism to enter a custom value, not a role name in itself.
