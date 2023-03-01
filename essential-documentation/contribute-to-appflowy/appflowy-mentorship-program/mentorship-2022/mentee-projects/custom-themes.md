---
description: Chirag Bargoojar
---

# Custom Themes

## Introduction

## Goal

## Design Architecture

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

