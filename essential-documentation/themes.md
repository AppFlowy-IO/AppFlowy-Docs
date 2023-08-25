# 🎨 Themes

## Uploading Custom Themes

AppFlowy allows uploading user-defined color schemes. AppFlowy's latest color scheme definition can be found in [`colorscheme.dart`](https://github.com/AppFlowy-IO/AppFlowy/blob/main/frontend/appflowy\_flutter/packages/flowy\_infra/lib/colorscheme/colorscheme.dart).

**Custom Theme Directory (Structure)**

To provide your own color scheme, you must create two JSON files, one called `<your_theme_name>.dark.json` and `<your_theme_name>.light.json` in a folder called `<your_theme_name>.flowy_plugin`. Here's an example for a theme called "Material"

<img src="../.gitbook/assets/image (1) (2) (1).png" alt="" data-size="original">

**Explanation**

AppFlowy can serialize or de-serialize any JSON file to provide colors for an application color scheme. A JSON file is simply a list of key, value pairs. When AppFlowy de-serializes your theme directory, it will use the values that you provided in your JSON as the values of the color scheme within your application.

**Providing Values**

After the directory and files have been created, use any text editor to provide the values for your custom theme. `<your_theme_name>.light.json` will be used if the appearance of the application is set to light, while `<your_theme_name>.dark.json` will be used if the appearance of the application is set to dark.

The JSON key in your theme file should correspond to a property in `colorscheme.dart`. Keys that you provide that are not properties in `colorscheme.dart` will be ignored. Properties that are present in `colorscheme.dart` but are not present as keys in the JSON file will default to transparent as their value.

> If you come from a non-technical background you don't have to bother understanding what any of that means. You can simply ask ChatGPT the following:\
> \
> _Could you generate me a JSON file where the keys are the properties of this class?_\
> _\`\`\`_\
> _\<paste the content of `colorscheme.dart` here>_\
> _\`\`\`_

Here's the most concrete example of what your JSON files might look like for `<your_theme_name>.light.json` and `<your_theme_name>.dark.json`:

```json
/// Example: Material.light.json 
{
  "surface": "0xff212121",
  "hover": "0xff2F2F2F",
  "selector": "0xff757575",
  "red": "0xffE53935",
  "yellow": "0xffFBC02D",
  "green": "0xff43A047",
  "shader1": "0xff212121",
  "shader2": "0xff2F2F2F",
  "shader3": "0xff757575",
  "shader4": "0xffE53935",
  "shader5": "0xffFBC02D",
  "shader6": "0xff43A047",
  "shader7": "0xff212121",
  "bg1": "0xff212121",
  "bg2": "0xff2F2F2F",
  "bg3": "0xff757575",
  "bg4": "0xffE53935",
  "tint1": "0xffFBC02D",
  "tint2": "0xff43A047",
  "tint3": "0xff212121",
  "tint4": "0xff2F2F2F",
  "tint5": "0xff757575",
  "tint6": "0xffE53935",
  "tint7": "0xffFBC02D",
  "tint8": "0xff43A047",
  "tint9": "0xff212121",
  "main1": "0xff2F2F2F",
  "main2": "0xff757575",
  "shadow": "0xffE53935",
  "sidebarBg": "0xff212121",
  "divider": "0xff757575",
  "topbarBg": "0xff2F2F2F",
  "icon": "0xffFBC02D",
  "text": "0xffF5F5F5",
  "input": "0xff2F2F2F",
  "hint": "0xff757575",
  "primary": "0xffE53935",
  "onPrimary": "0xffF5F5F5",
  "hoverBG1": "0xff2F2F2F",
  "hoverBG2": "0xff757575",
  "hoverBG3": "0xffE53935",
  "hoverFG": "0xffFBC02D",
  "questionBubbleBG": "0xff212121",
  "progressBarBGColor": "0xff757575",
  "toolbarColor": "0xff2F2F2F",
  "toggleButtonBGColor": "0xffFBC02D"
}
```

**Color Values Continued...**

The values in the JSON file should use the `0x` Hex Notation, followed by 2 characters denoting the brightness value, followed by the color code. The result should look like the following:

`0xFFABCDEF`

Where "`0x`" is the Hex Notation prefix, "`FF`" is the brightness value and "`ABCDEF`" is the color value.&#x20;

Most online color pickers will give you values with the following annotation:

`#ABCDEF`&#x20;

If you prefer to use these color pickers, you can simply replace `#` with `0xFF` so that the color code that you provided can be parsed by AppFlowy.

> _**Hack it with ChatGPT**_
>
> _Personally, I'm too lazy to pick all of the color values by hand, and I'd rather start with a template. Turns out that ChatGPT is not too shabby at creating a template for you to start with. You can use the following query to get something pretty good for one of the JSON files. Use this query and fill in the `<>`:_\
> \
> Given the following class, could you generate a JSON file where the keys are the properties of the following class and their values are filled with possible values for a `<SOME_THEME>` color scheme in hex notation prefixed with 0x and with brightness values?\
> \<paste the content of `colorscheme.dart` here>

**Uploading**

Before you upload, double check that your theme plugin has the correct format and that the keys and values provided in your JSON are accurate. After, open your AppFlowy settings tab and click on the folder icon.

![](<../.gitbook/assets/image (5) (3).png>)

The following pop up should appear.

![](<../.gitbook/assets/image (2) (2) (1).png>)

Click on upload and choose `<your_theme_name>.flowy_plugin` folder.

:fingers\_crossed: Fingers crossed.... hopefully your theme looks great! If not, please fill out the following form so that we can improve your user experience at [https://github.com/AppFlowy-IO/AppFlowy/issues/new?assignees=\&labels=\&projects=\&template=feature\_request.yaml\&title=%5BFR%5D+](https://github.com/AppFlowy-IO/AppFlowy/issues/new?assignees=\&labels=\&projects=\&template=feature\_request.yaml\&title=%5BFR%5D+)
