# ☎ Translate AppFlowy

You can help Appflowy in supporting various languages by contributing. Follow the steps below sequentially to contribute translations.

## Steps to modify an existing translation

Translation files are located in : `frontend/app_flowy/assets/translations/`

### Modify in the no-code editor (inlang)

1. Open the [inlang-editor](https://inlang.com/editor/github.com/AppFlowy-IO/AppFlowy)
2. Edit translations (filter & search can help)
4. Run `flutter pub run easy_localization:generate -S assets/translations/`
5. Run `flutter pub run easy_localization:generate -f keys -o locale_keys.g.dart -S assets/translations`
6. Verify that the translation has changed appropriately by compiling and running the app.

### Modify in code

1. Modify the specific translation file.
2. Run `flutter pub run easy_localization:generate -S assets/translations/`
3. Run `flutter pub run easy_localization:generate -f keys -o locale_keys.g.dart -S assets/translations`
4. Verify that the translation has changed appropriately by compiling and running the app.

## Steps to add new language

### 1. Add the language resource

The language resource is a `json` file that needs to be added per language. You can do that via the inlang editor or in code.

**->Via inlang editor.**

1. Open the [inlang-editor](https://inlang.com/editor/github.com/AppFlowy-IO/AppFlowy)
2. Press `add language`
3. Enter `language code`
4. (You can start translating)

**->Via code**

Add language key-value json file to `frontend/app_flowy/assets/translations/`. Refer `en.json` for format and keys.

**NOTE: Translation files SHOULD be** `json` **files named in the format** `<lang_code>-<country_code>.json` **or just** `<lang_code>.json`**. eg:**`en.json`**,** `en-UK.json`


### 2. Add the language to the i18n sdk

1. Run `flutter pub run easy_localization:generate -S assets/translations/`
2. Run `flutter pub run easy_localization:generate -f keys -o locale_keys.g.dart -S assets/translations`
3. Open the `frontend/app_flowy/lib/startup/tasks/app_widget.dart` file.
4. In the `InitAppWidgetTask` class, add the locale of the language you just created (eg: `Locale('en', 'IN')`, `Locale('en')`) to the `supportedLocales` List :

    ```dart
    runApp(
      EasyLocalization(
        supportedLocales: const [Locale('en'), Locale('zh', 'CN')],  // <---- Add locale to this list
        path: 'assets/translations',
        fallbackLocale: const Locale('en'),
        child: app),
    );    
    ```
5. Add the name of your language, in your native tongue, to the list of language names in `AppFlowy/frontend/app_flowy/packages/flowy_infra/lib/language.dart`
    ```dart
    String languageFromLocale(Locale locale) {
      switch (locale.languageCode) {
        // Most often used
        case "en":
          return "English";
        case "zh":
          return "简体中文";

        // Then in alphabetical order
        case "de":
          return "Deutsch";
        case "es":
          return "Español";
        case "fr":
          return "Français";

                               // <- add your language here.

        // If not found then the language code will be displayed
        default:
          return locale.languageCode;
      }
    }
    ```


## How to test your changes

Once your language is added to the language picker, you can simply choose it.
