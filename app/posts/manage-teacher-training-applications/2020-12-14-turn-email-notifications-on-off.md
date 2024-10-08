---
title: Let users turn email notifications on and off
description: Some users check the service regularly and do not need to receive an email every time an application’s status changes. We’re going to let those users turn off notifications.
date: 2020-12-14
screenshots:
  items:
    - text: ’Your account’ page with new section added
      src: account-page.png
    - text: New ‘email notifications’ page
      src: email-notifications-page.png
    - text: Success banner
      src: email-notifications-page--saved.png
---

The service sends out email notifications to users when an application is:

- submitted
- withdrawn (automatically or manually by the candidate)
- automatically rejected
- accepted
- declined

These are all changes which are not triggered by a provider, so the user may not be aware of them.

## What we did

Some users do not find the emails useful because they receive too many. We want to offer the ability to turn off notifications.

We’ve added a new section to ‘Your account’, called ‘Email notifications’. This is a page with a pair of radio buttons to turn email notifications on or off, with a green button to save the setting.

The hint text explains what emails are included, since the service will still send users system generated emails which are not related to applications.
