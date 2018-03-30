# XClean

Simple tool to clean some of the stuff created by XCode.<br>
Looks at next locations and tries to remove some of the stuff located here:
```
~/Library/Developer/Xcode/DerivedData
~/Library/Developer/Xcode/Archives
~/Library/Developer/Xcode/iOS DeviceSupport
~/Library/Developer/Xcode/watchOS DeviceSupport
~/Library/Developer/CoreSimulator/Devices
/Library/Developer/CoreSimulator
```

## Installation

```brew install deszip/tools/xclean```

## Usage

```
usage: xclean [-l] <TARGET> [-r] <TARGET> [-t] <TIMEOUT>

-l <TARGET>    Lists files that could be relatively safely removed.
               Pass target name to list only it. Available targets: DerivedData, Archives, DeviceSupport, CoreSimulator.
               If no value passed - uses all targets.
-r <TARGET>    Removes files listed by -l
-t <TIMEOUT>   Sets interval for assuming file is old.
               -r and -l will process only files with last access date older than timeout
-v             Print the version of the application
```

Some examples:<br>
- List all targets showing info on how much space could be freed<br>`xclean -l`
- Same as above but only for derived data<br>`xclean -l DerivedData`
- Removes all derived data older than an hour<br>`xclean -r DerivedData -t 3600`

## Contacts
If you have improvements or concerns, feel free to post [an issue](https://github.com/deszip/xclean/issues) and write details.
