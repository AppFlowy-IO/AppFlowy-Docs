# Brand

WIP

## Appflowy.io User Interface Design Guidelines

These are the guiding principles behind the interface of Appflowy.io. You can find the Figma primitives in our [Figma Community File](https://www.figma.com/community/file/1053741086081877521/Appflowy.io).

If you have any questions or feedback, please contact [@BranHillsDesign](https://twitter.com/branhillsdesign) on twitter or here on [GitHub](https://github.com/branhillsdesign).

### Table of Contents

* Typography
* Color

## Typography

Guidelines to ensure that font choices across all screens are consistent while being able to develop quickly while using typographic best practices.

### Font Stack

Appflowy uses two typefaces by default. Poppins, which can be found on Google Fonts, and SF Mono for code snippets.

![](https://github.com/AppFlowy-IO/appflowy/raw/main/doc/imgs/Typography%20Styles.svg)

#### [Poppins](https://fonts.google.com/specimen/Poppins#about)

Can be found at Google Fonts.

**Headings**

| Variable | Weight   | Size | Line Height | Tracking |
| -------- | -------- | ---- | ----------- | -------- |
| `h1`     | Bold     | 44   | 52px        | 0.3%     |
| `h2`     | Semibold | 32   | 42px        | 0.5%     |
| `h3`     | Semibold | 24   | 34px        | 0.5%     |
| `h4`     | Semibold | 20   | 28px        | 0.5%     |

**System Fonts**

| Variable           | Weight   | Size | Line Height | Tracking |
| ------------------ | -------- | ---- | ----------- | -------- |
| `title`            | Semibold | 18   | Auto        | 0.5%     |
| `subheading`       | Semibold | 16   | Auto        | 0.5%     |
| `subtitle`         | Semibold | 12   | Auto        | 0.5%     |
| `callout`          | Medium   | 11   | Auto        | 0.5%     |
| `caption`          | Regular  | 11   | Auto        | 0.5%     |
| `headline-bold`    | Bold     | 14   | Auto        | 0.5%     |
| `headline-regular` | Regular  | 14   | Auto        | 0.5%     |
| `body-regular`     | Medium   | 12   | Auto        | 0.5%     |

#### [SF Mono](https://developer.apple.com/fonts/)

Can be found at Apple's website. If you're on Windows or Linux, you can find the download for the San Francisco font family on [GitHub.](https://github.com/AppleDesignResources/SanFranciscoFont) at Apple's Design Resources repository.

| Variable    | Weight   | Size | Line Height | Tracking |
| ----------- | -------- | ---- | ----------- | -------- |
| `codeblock` | Semibold | 12   | Auto        | 0.5%     |

## Color

Color helps create a usable and accessible interface that is a consistent experience through all interactions of our product. Appflowy.io's color system includes two color modes by default, light and dark. Colors are named within a theme for the functions performed within the product. They are easily editable and allows for a solid foundation of accessibility for anyone trying to create their own unique color theme for Appflowy.io

![](https://github.com/AppFlowy-IO/appflowy/raw/main/doc/imgs/darkmode%20-%20lightmode.svg)

### Specifications

Colors have been named with a functional naming schema that makes it easy to figure out where the color is supposed to be used. RGB and HSL color values are provided.

#### Example Syntax

| Variable | Function | Explanation                                  |
| -------- | -------- | -------------------------------------------- |
| `bg-`    | `-menu`  | Menu backgrounds.                            |
| `text-`  | `-vivid` | Used for vivid, high contrast, text.         |
| `tag-`   | `-aqua`  | Tag color used for color coding organization |

#### Explanation of Variables and Functions

| Variable        | Function                                                       |
| --------------- | -------------------------------------------------------------- |
| `primary`       | Primary Brand Color                                            |
| `secondary`     | Secondary Brand Color                                          |
| `hover-menu`    | Menu hover interaction                                         |
| `selector-menu` | Menu selector interaction                                      |
| `bg-menu`       | Menu system background color                                   |
| `bg-surface`    | Non menu background color.                                     |
| `alert`         | System alerts in red, yellow, or green.                        |
| `tag`           | Color coding organization functions                            |
| `grey`          | Static grey system colors used across all themes as a default. |

| Color    | Use Case                                      |
| -------- | --------------------------------------------- |
| `-vivid` | The fully saturated version of the color.     |
| `-dim`   | Decreased black value from the `-vivid` color |

### Light Mode Theme Example

In order to create a new theme, replaced the color codes for each variable.

```dart
factory AppTheme.fromType(ThemeType t) {
	switch (t) {
	 case ThemeType.light:
		 return AppTheme(isDark: false)
			 ..primary-vivid = Color(0xFF00bfc0)
			 ..primary-dim = Color(0xFF009cc7)
			 ..secondary-vivid = Color(0xFFb061ff)
			 ..secondary-dim = Color(0xFF9327ff)
			 ..text-vivid = Color(0xff333333)
			 ..text-dim = Color(0xff6e6e6e)
			 ..hover-menu = Color(0xff1f1f1f)
			 ..selector-menu = Color(0xfff5f5f5)
			 ..bg-menu = Color(0xfff7f8fc)
			 ..bg-surface = Color(0xffffffff)
			 ..alert-red-vivid = Color(0xfffb006d)
			 ..alert-red-dim = Color(0xffe00061)
			 ..alert-yellow-vivid = Color(0xffffd667)
			 ..alert-yellow-dim = Color(0xff66cf80)
			 ..alert-green-vivid = Color(0xff50a365)
			 ..tag-purple = Color(0xffc3adff)
			 ..tag-pink = Color(0xffffadf9)
			 ..tag-red = Color(0xffffadad)
			 ..tag-orange = Color(0xffffcfad)
			 ..tag-yellow = Color(0xfffffead)
			 ..tag-lime = Color(0xffbcffad)
			 ..tag-green = Color(0xffadf9ad)
			 ..tag-aqua = Color(0xffadffe2)
			 ..tag-blue = Color(0xffade4ff)
			 ..black-00 = Color(0xff000000)
			 ..black-10 = Color(0xff1a1a1a)
			 ..black-20 = Color(0xff333333)
			 ..black-30 = Color(0xff4d4d4d)
			 ..black-40 = Color(0xff666666)
			 ..black-50 = Color(0xff808080)
			 ..black-60 = Color(0xff999999)
			 ..black-70 = Color(0xffb2b2b2)
			 ..black-80 = Color(0xffcccccc)
			 ..black-90 = Color(0xffe5e5e5)
			 ..white-100 = Color(0xffffffff);
}
```
