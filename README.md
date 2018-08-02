# Android Code Style

Code formatting rules for Android Studio

## Features
- Based on googles java code style (https://git.io/v5XuB)
- [No star imports](https://github.com/grandcentrix/AndroidCodeStyle/issues/5) except for testing libraries
- Increase the line length to 140
- `android:id` after `xmlns` declaration in XML layouts
- [Keep lifecycle methods together](https://github.com/grandcentrix/AndroidCodeStyle/issues/3)
- [Keep getters and setters together](https://github.com/grandcentrix/AndroidCodeStyle/issues/7)
- Advanced code Arrangement rules for Java (Sort methods alphabetically (a-z) and by visibility (`public`-`private`))
  - Inner classes (classes, interfaces, enums)
  - Fields (grouped by visibility, a-z)
  - [public static methods](https://github.com/grandcentrix/AndroidCodeStyle/issues/8) (a-z)
  - Constructors
  - [Android Lifecycle methods](https://github.com/grandcentrix/AndroidCodeStyle/issues/3) in correct order
  - Methods ([grouped by visibility, a-z](https://github.com/grandcentrix/AndroidCodeStyle/issues/6))
  - static methods (grouped by visibility (except public), a-z)

## Installation on your local machine

### Automatically (the easiest way)
Just run the [`install`](install.sh) script.
It will automatically copy the latest Code Style to each existing `AndroidStudio` and `AndroidStudioPreview` version you have installed.

### Manually (the hard way)
1. Copy the [`codestyle.xml`](styles/codestyle.xml) into (MacOS) ``~/Library/Preferences/AndroidStudio{VERSION}/codestyles/`` or (Linux) ``~/.AndroidStudio{VERSION}/config/codestyles/``
2. Restart AndroidStudio
3. Select the codestyle scheme via `Preferences --> Editor --> Code Style`.

The codestyle will be enabled/used for **all projects** that are used with AndroidStudio!

## Enabling project specific code styles for a project
If the codestyle is added to the git repository and IntelliJ is configured accordingly each project can have it's own style.

1. Install the [`codestyle.xml`](styles/codestyle.xml) locally (see above)
2. Restart AndroidStudio
3. In AndroidStudio, go to `Preferences --> Code style`
4. Open the scheme manager by clicking on `Manage...`
5. Select the code style and click `Copy to project`
6. In the scheme drop down select `Project`

Finally add the code style to the git repository:
```
git add -f .idea/codeStyleSettings.xml
```

## Contributing
To contribute just change the code style locally to your needs.
Then you can create a PR to this repository.

The PR should always contain:
* Some information what have changed.
* A updated [`codestyle.xml`](styles/codestyle.xml).

## Pro tip: Reformat on save
[Taken from passy's excellent blog post which you can find here](https://android.jlelse.eu/7-reasons-this-android-code-style-improves-your-productivity-65d196fa55f)

With 3 simple steps you can reorder and reformat your code automatically with ⌘ + S. That shortcut you are used to press constantly although you know Android Studio automatically saves all files for you. Give ⌘ + S a different meaning:

Make sure a Java source file has focus (or you can’t record all steps)
- Select Edit > Macros > Start Macro Recording
- Select Code > Optimize Imports
- Select Code > Reformat Code
- Select Code > Rearrange Code
- Select File > Save All
- Select Edit > Macros > Stop Macro Recording and give it a name (mine is OptimizeImportsReformatRearrangeSave)

Go to Preferences > Keymap
- Find the Macro section
- Add ⌘ + S shortcut for the new macro

Alternatively you can reformat code with ⌥+⌘+L . When you select parts of your code, only those get reformatted. This doesn’t reorder your code or changes imports. It's best to use when touching code which doesn’t have a code style.

## License
[CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/legalcode)
