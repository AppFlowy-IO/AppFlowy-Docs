---
description: Mihir Singh
---

# ⭐ Favorites

## Introduction

* Managing and organizing vast amounts of data can be a daunting task. Whether it's navigating through numerous files and folders or trying to locate specific information within a page, the process can often become overwhelming.
* As users of productivity tools like AppFlowy, we often find ourselves grappling with the challenge of efficiently accessing and prioritizing the content that matters most to us.
* A favorite mechanism can alleviate this problem of navigating through a vast database by offering users a simple and effective go-to mechanism.

## Goal

Goal of this project is to provide users with efficient mechanism for managing and accessing their most important and frequently used content by allowing users to mark views as favorites, the feature aims at advanced navigation, organization and productivity within the app.

## Scope

1. Favorite a Page: Users can easily mark a page as a favorite by navigating to the desired page and clicking a dedicated button at the top-right corner. This action signifies the user's preference for quick access to the selected page.
2. Favorites Section: A dedicated Favorites section will be introduced in the left sidebar of the AppFlowy interface. Once the user has favorited their first page, this section will automatically appear. It provides users with a centralized location to find their pinned pages and related subdirectories, ensuring easy access to their most important and frequently accessed content.
3. Remove from Favorites: Users have the flexibility to unpin or remove a page from their Favorites section, allowing them to update their prioritization and keep the Favorites section relevant to their current needs and preferences.

## Implementation Design

To implement the favorites feature in AppFlowy, a comprehensive approach involving changes in both AppFlowy's rust and flutter components is proposed. AppFlowy's persitence logic which was previously part of rust-lib in AppFlowy is now separated to a different repository AppFlowy-Collab, current plan is to introduce following changes:

1. Changes to Existing Persistence Structs (Rust):
   * Each item displayed in the left sidebar will be represented as a `View` struct. The concept of an 'App' is deprecated.
   * The `View` struct is defined in the `folder-collab` crate and exposed using the `ViewPB` struct.
   * A new variable named `is_favorites` will be introduced in the `View` and `ViewPB` structs. This variable will indicate whether a specific view is a favorite without the need to iterate through all favorited views.
2. Introduction of New Structs (Rust):
   * Two new structs, `FavoritesInfo` and `FavoritesArray`, will be introduced in the `collab` module.
   * `FavoritesInfo` will only hold the `view_id` of the favorited view. This will allow separate persistence of the favorite views.
   * `FavoritesArray` will utilize `ArrayRefWrapper` and `ViewsMap` as underlying constructs to persist all the favorite views.
3. Calculation of Favorite Views and Data Transfer (Rust):
   * The handlers in the Rust library (`rust-lib`) will handle requests from the frontend to calculate the views marked as favorites based on user interactions.
   * On every new launch of AppFlowy, a `FolderEvent` named `ReadFavorites` will be sent to `rust-lib`. This event will be handled by a `read_favorites_handler` function, which will retrieve all the favorite views from persistence, map them to `RepeatedViewPB` (a list of `ViewPB`), and return them to the frontend for display under the favorites section.
   * When a favorite is toggled for a view, a `FolderEvent` named `ToggleFavorite` will be triggered, carrying the `viewId` of the designated view. This event will be handled by the `toggle_favorites` function in `rust-lib`.
     * If the view is not currently marked as a favorite, it will be added and persisted to the list of favorites.
     * If the view is already marked as a favorite, it will be removed from the list of favorites, effectively unfavoriting it.
     * Furthermore, a `ViewPB` will be created and returned to the frontend. This `ViewPB` object will represent the updated view and can be appended to the visible list of views in the favorites section. This ensures that the UI accurately reflects the updated favorite status of the view.
4. Notification Handling (Rust):
   * A notification system will be implemented to handle updates to the favorite status of views.
   * When the favorite status of a view is updated, a notification named `DidUpdateView` under `FolderNotification` will be triggered to update the favorite status of the individual view.
   * A `FolderNotification` named `FavoritesUpdated` will be sent every time favorite status of a view is updated. This notification will carry a list of the updated favorite views, which will be displayed under the favorites section in Flutter.
5. Integration with UI (Flutter):
   * The Flutter component will incorporate a dedicated bloc and service to handle the favorites functionality.
   * This module will be responsible for sending events to `rust-lib` and processing the notifications received with those events to appropriately update the views in the UI.
6. Handling Edge Cases (Flutter):
   * Additional notifications will be handled when a view's data is updated in the menu. For example, if a view is renamed, deleted, or its icon is updated, these changes will be propagated to the associated view under the favorites section.

## Expected Schedule

By July 6th (Estimated)

* [x] Update the view struct in AppFlowy-Collab to deal with persistence of favorites.
* [x] Create appropriate notifiers, events and handlers to map events and notifications.
* [x] Expose a new method that calculates the views marked as favorite
* [x] Expose a new method to toggle favorites for the views

By 12th July (Estimated)

* [x] Introduce favorite service which sends event to retrieve all favorite views in appropriate structure which can be displayed under favorites section
* [x] Favorite service will be capable of sending events to toggle favorites.
* [x] Favorites BLoC will be introduced to handle state updates for favorite changes.

By 20th July (Estimated)

* [ ] Add unit / integration tests in flutter
* [ ] Add tests in collab and rust-lib
* [ ] Handle edge cases for other possible events
* [ ] Code cleanup and optimization in rust-lib and collab.
