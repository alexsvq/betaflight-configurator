# Betaflight Configurator

![Betaflight](http://static.rcgroups.net/forums/attachments/6/1/0/3/7/6/a9088900-228-bf_logo.jpg)

Betaflight Configurator is a crossplatform configuration tool for the Betaflight flight control system.

It runs as an app within Google Chrome and allows you to configure the Betaflight software running on any [supported Betaflight target](https://github.com/betaflight/betaflight/tree/master/src/main/target).

Various types of aircraft are supported by the tool and by Betaflight, e.g. quadcopters, hexacopters, octocopters and fixed-wing aircraft.

## Authors

Betaflight Configurator is a [fork](#credits) of the Cleanflight Configurator with support for Betaflight instead of Cleanflight.

This configurator is the only configurator with support for Betaflight specific features. It will likely require that you run the latest firmware on the flight controller.
If you are experiencing any problems please make sure you are running the [latest firmware version](https://github.com/betaflight/betaflight/releases/).

## Installation

### Via chrome webstore

[![available in the Chrome web store](https://developer.chrome.com/webstore/images/ChromeWebStore_Badge_v2_206x58.png)](https://chrome.google.com/webstore/detail/betaflight-configurator/kdaghagfopacdngbohiknlhcocjccjao)

1. Visit [Chrome web store](https://chrome.google.com/webstore/detail/betaflight-configurator/kdaghagfopacdngbohiknlhcocjccjao)
2. Click **+ Add to Chrome**

Please note - the application will automatically update itself when new versions are released.  Please ensure you maintain configuration backups as described in the Betaflight documentation.

### Alternative way

1. Clone the repo to any local directory or download it as zip.
2. Extract to a folder and not the folder.
3. Start Google Chrome.
4. Click the 3-dots on the far right of the URL bar.
5. Select "More Tools"
6. Select "Extensions"
7. Check the Developer Mode checkbox.
8. Click on load unpacked extension.
9. Point it to the folder you extracted the zip to.

## How to use

You can find the Betaflight Configurator icon in your application tab "Apps"

## Native app build via NW.js

Linux build is disabled currently because of unmet dependecies with some distros, it can be enabled in the `gulpfile.js`.

### Development

1. Install node.js
2. Change to project folder and run `npm install`.
3. Run `npm start`.

### App build and release

The tasks are defined in `gulpfile.js` and can be run either via `gulp <task-name>` (if the command is in PATH or via `../node_modules/gulp/bin/gulp.js <task-name>`:

1. Optional, install gulp `npm install --global gulp-cli`.
2. Run `gulp <taskname> [[platform] [platform] ...]`.

List of possible values of `<task-name>`:
* **dist** copies all the JS and CSS files in the `./dist` folder.
* **apps** builds the apps in the `./apps` folder [1].
* **debug** builds debug version of the apps in the `./debug` folder [1].
* **release** zips up the apps into individual archives in the `./release` folder [1]. 

[1] Running this task on macOS or Linux requires Wine, since it's needed to set the icon for the Windows app (build for specific platform to avoid errors).

#### Build or release app for one specific platform
To build or release only for one specific platform you can append the plaform after the `task-name`.
If no platform is provided, all the platforms will be done in sequence.

* **MacOS** use `gulp <task-name> --osx64`
* **Linux** use `gulp <task-name> --linux64`
* **Windows** use `gulp <task-name> --win32`

You can also use multiple platforms e.g. `gulp <taskname> --osx64 --linux64`.

## Notes

### WebGL

Make sure Settings -> System -> "User hardware acceleration when available" is checked to achieve the best performance

### Linux users

Dont forget to add your user into dialout group "sudo usermod -aG dialout YOUR_USERNAME" for serial access

### Linux / MacOSX users

If you have 3D model animation problems, enable "Override software rendering list" in Chrome flags chrome://flags/#ignore-gpu-blacklist

## Support

If you need help please reach out on the [betaflightgroup](https://betaflightgroup.slack.com) slack channel before raising issues on github. Register and [request slack access here](http://www.betaflight.tk).

### Issue trackers

For Betaflight configurator issues raise them here

https://github.com/betaflight/betaflight-configurator/issues

For Betaflight firmware issues raise them here

https://github.com/betaflight/betaflight/issues

## Technical details

The configurator is based on chrome.serial API running on Google Chrome/Chromium core.

## Developers

We accept clean and reasonable patches, submit them!

## Credits

ctn - primary author and maintainer of Baseflight Configurator from which Cleanflight Configurator project was forked.

Hydra -  author and maintainer of Cleanflight Configurator from which this project was forked.
