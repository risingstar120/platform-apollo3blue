# platform-apollo3blue
This is an experimental platform to allow the use of [SparkFun's Arduino framework](https://github.com/sparkfun/Arduino_Apollo3) in PlatformIO.

# How To Use This
As this is experimental, it requires a manual install.

# Supported Frameworks and Tools

Platform-apollo3blue now supports the following: 

1. Frameworks:
    * Arduino - [sparkfun/Arduino_Apollo3](https://github.com/sparkfun/Arduino_Apollo3)
        * [Core V1](https://github.com/sparkfun/Arduino_Apollo3/tree/v1)
        * [Core V2](https://github.com/sparkfun/Arduino_Apollo3)
    * Ambiq Suit SDK - [sparkfun/AmbiqSuiteSDK](https://github.com/sparkfun/AmbiqSuiteSDK.git)
2. Tools:
    * Segger [JLink](https://www.segger.com/products/debug-probes/j-link/) with [platformio](https://docs.platformio.org/en/latest/plus/debug-tools/jlink.html)
        * [Upload protocol](docs/platform-apollo3blue/UsingSeggerJLink.md#upload-firmware) 
        * [Debugger](docs/platform-apollo3blue/UsingSeggerJLink.md#debug-firmware)

To specify which framework and version to use, see [below](#specifying-the-version-of-sparkfunarduino_apollo3) or a more detailed [example](docs/platform-apollo3blue/UsingMultipleVersionsOfArduino_Apollo3.md).
    
# Quick Start
Here we document the quickest way to get started using `platform-apollo3blue`. 

## 1. Install `platform-apollo3blue`
````
$ pio platform install git+https://github.com/nigelb/platform-apollo3blue
````

## 2. Select and Install a version of Arduino_Apollo3
The quickest and easiest way to install Arduino_Apollo3 is to create a project and specify the version as a git repo.

```
$ mkdir new_project
$ cd new_project
```

And then either:
### Core V2
```
$ pio init -b SparkFun_RedBoard_Artemis_ATP -O"platform_packages=framework-arduinoapollo3@https://github.com/sparkfun/Arduino_Apollo3#v2.2.0"
```

or:
### Core V1
Until the version number is bumped for the core v1 branch, I am maintaining a fork of it [here](https://github.com/nigelb/Arduino_Apollo3) with the required updates.
```
$ pio init -b SparkFun_RedBoard_Artemis_ATP -O"platform_packages=framework-arduinoapollo3@https://github.com/nigelb/Arduino_Apollo3#v1.2.1_pio"
```

# Manual install of sparkfun/Arduino_Apollo3
If you don't want to use my forked repo, or you want to be able to have concurrent projects that use `core v1` and `core v2`
without having platformio reinstall Arduino_Apollo each time, you can manually install both version
of the cores.

See the [Manual Installation](docs/platform-apollo3blue/Install/Manual.md) and [Using Multiple Versions of Arduino_Apollo3](docs/platform-apollo3blue/UsingMultipleVersionsOfArduino_Apollo3.md).

# More Information

1. [Verify Installation](docs/platform-apollo3blue/Install/Verify.md)
2. [Manually Create a project](docs/platform-apollo3blue/Install/Create%20a%20project.md)
3. [Upload over USB](docs/platform-apollo3blue/Install/Upload.md)
4. [`platformio.ini` customization options](docs/platform-apollo3blue/PlatformIO_ini_Options.md)
5. [Using a Segger JLink](docs/platform-apollo3blue/UsingSeggerJLink.md)
6. [Debugging](docs/platform-apollo3blue/Debug/Debugging.md)