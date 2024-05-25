# Virtual Radar Server

A .NET Core application for Windows, Linux and macOS that can decode Mode-S and ADS-B
transmissions from aircraft transponders and plot their positions on a map.

This is in the very early stages of development. The mature version of VRS is here:

https://github.com/vradarserver/vrs

## Compilation

You will need the .NET 8 SDK, available here:

https://dotnet.microsoft.com/en-us/download/dotnet/8.0

Confirm that you have a .NET Core 8 SDK installed:

| Operating System | Command |
| ---              | --- |
| All              | `dotnet --list-sdks` |

If this is your first build then restore the NuGet packages:

| Operating System | Command |
| ---              | --- |
| Linux            | `./build.sh restore` |
| macOS            | `./build.sh restore` |
| Windows          | `build restore` |

Then to build everything:

| Operating System | Command |
| ---              | --- |
| Linux            | `./build.sh solution` |
| macOS            | `./build.sh solution` |
| Windows          | `build solution` |

## Third Party Libraries

### JSON Serialisation and Deserialisation

Newtonsoft (https://www.newtonsoft.com/json) is used for JSON serialisation. The
built-in JSON serialiser forces you to use its own attributes rather than the
serialiser agnostic `DataContract` and `DataMember`, it is off-limits.
