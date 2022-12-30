---
description: Richard Shiue
---

# Calendar View for AppFlowy Database

## Introduction

AppFlowy's database is an extremely powerful feature that allows users to store data in a structured manner. Each database can be customized to contain multiple fields, each of a different type, such as text, date and single-selection tags. For more information about the terminology used in AppFlowy's database, please check out [grid.md](../../../architecture/frontend/grid.md "mention"). While the most common way to view the database is in the table-view, alternative views can present the data better depending on the use case. For example, the kanban board groups entries into columns according to a status tag, and is a popular choice for project progress tracking. It also allows for new ways to interact with the entries, such as dragging a card from one column to another in kanban.

## Goal

The goal of this project is to introduce a calendar view so that users can grasp upcoming (or past) scheduled events at a glance. Users will be able easily identify the duration of an event, if and when events overlap, or how much spacing is between two events. This feature will be especially useful for task scheduling and event planning.

### Scope

By the completion of this project, users will be able to:

* Create a calendar page from the left sidebar
* See events laid out in a calendar view
* Switch between one month to the next
* Jump to current day
* Jump to a particular month or year
* Add a new event by clicking on a day
* Click an `add` button to create a new event on a specific day
* Edit a particular event a popup window triggered by clicking on the event in the calendar view (actions include changing its title and adding/removing/modifying other fields)
* Specify which additional properties are shown in each entry in the calendar view.
* Reschedule an event without changing its duration by dragging it from one day to another
* See a list of events that have not been yet scheduled from a menu or popup. They can be scheduled (and thereby viewed on the calendar) by editing the event in a popup window as described above, dragged from the menu onto a day, or middle-clicked to schedule to today
* Increase or decrease the duration of an event by dragging the event's edges&#x20;
* Delete an event
* Group events together by specifying an extra single-select field. Events belonging to the same group are characterized by a common background color and will also be customizable by the user
* If there are more than one date fields in the entries, allow the user to specify which date field will be used to arrange the events in the calendar view
* Filter visible events according to the entry's group or another field
* Show alternative views that are more time-oriented (week, work week, 3 day, day)
* Set up recurring events and choose when editing one to either edit all the events set up in the same way or just that specific one

## Prep Work

WIP

## Design Architecture

WIP
