---
description: Chirag Bargoojar
---

# Custom Themes

## Introduction

* As Appflowy's user base increases, users want more control over the app.&#x20;
* Adding custom themes to Appflowy can significantly enhance the user experience and productivity. Allowing users to personalize the app's appearance can help them create a more comfortable and visually appealing work environment.
* Custom themes can also provide a sense of ownership and control for users, which can increase their motivation and engagement with the app.&#x20;
* Users may also be able to reduce eye strain and fatigue by choosing themes that are optimized for their specific lighting conditions and visual preferences. Moreover, custom themes can help users to maintain a consistent aesthetic across different apps and tools they use, which can improve their overall workflow and productivity.

## Goal

* The goal is to implement a feature where users are able to create their own set of themes and also able to change themes from predefined themes.
* Predefined Themes: These kinds of themes will already be present in the app, the user just needs to change the theme just by clicking on it.
* Custom Themes: This functionality is provided in the app to day-to-day users where they can create their own themes. They can set the color and style of any elements i.e. Color of links, fonts, sizes, etc, to their individual needs.
* Overall, this feature can help to create a more enjoyable and efficient user experience, providing a more engaging and personalized interface that aligns with individual preferences and workflow.

## Design Architecture

TBD

### How to add a new theme (Developer Specific)

1. Go to app\_flowy\packages\flowy\_infra\lib\colorscheme.
2. Start by creating a file and naming it with your theme name.&#x20;
3. Then create a class and give your theme name followed by ColorScheme (to follow the code pattern) Eg. If your theme name is Aqua give your class name AquaColorScheme.
4. Extend your ColorScheme with FlowyColorScheme to override all the item colors needed to change your theme.
5. Here you need to define 2 kinds of themes:\
   \- Light: How your custom theme will look in light mode.\
   \- Dark: How your custom theme will look in dark mode.
6. Follow the default\_colorscheme.dart file to take reference.
7. Now go to app\_flowy\packages\flowy\_infra\lib\theme.dart and inside BuiltInTheme create a string variable with your theme name. Example: static const String aqua = “aqua”;
8.  Now go to app\_flowy\packages\flowy\_infra\lib\colorscheme\colorscheme.dart and inside the themeMap variable add your theme config like this\


    {% code title="colorscheme.dart" overflow="wrap" lineNumbers="true" %}
    ```dart
    ‌BuiltInTheme.aqua: [
        AquaColorScheme.light(),
        AquaColorScheme.dark(),
    ],
    ```
    {% endcode %}
9.  Now at last go to app\_flowy\lib\workspace\presentation\settings\widgets\settings\_appearance\_view.dart inside ThemeSetting class and inside popupBuilder add your theme to the popup which will show in settings like this&#x20;

    {% code title="settings_appearance_view.dart " overflow="wrap" lineNumbers="true" %}
    ```dart
    ‌BuiltInTheme.aqua: [
        AquaColorScheme.light(),
        AquaColorScheme.dark(),
    ],
    ```
    {% endcode %}
10. Now run the app and go to Settings to see your new custom theme.

## References

