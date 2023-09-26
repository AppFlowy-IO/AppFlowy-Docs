---
description: >-
  DISCLAIMER: This page contains information about features that are
  work-in-progress (WIP).
---

# Calendar

## Definitions

* **Event**: An event in a calendar view is analogous to a row as define [here](./#database-definitions), with the added requirement of it must having at least one date field.

## Layout Settings

Several aspects of the calendar view UI can be customized in the settings menu. These settings are stored in the database's layout settings:

* Which layout to use: day, week or month.
* Whether to display weekends.
* Whether to display the week numbers.
* Which day is the first day of the week.
* Which date field should be used to arrange the events in the calendar.

The calendar layout settings are retrieved by [sending events](./#events-and-notifications) to the backend and then getting the resulting notification. The specific events and notifications of interest here are the `GetLayoutSetting` and `SetLayoutSetting` events, and the `DidUpdateLayoutSettings` and `DidSetNewLayoutField` notifications.

## Displaying Events

Events in the database are arranged in the calendar using the currently-specified date field. If the value of this date field for an event is empty, that event will not be displayed in the calendar, but rather in a list of other such events.

