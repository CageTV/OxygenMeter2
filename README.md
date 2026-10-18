# Oxygen Meter

SKSE plugin that repurposes the enchantment charge meter for an oxygen meter when underwater

## Requirements
* [CMake](https://cmake.org/)
	* Add this to your `PATH`
* [PowerShell](https://github.com/PowerShell/PowerShell/releases/latest)
* [Vcpkg](https://github.com/microsoft/vcpkg)
	* Add the environment variable `VCPKG_ROOT` with the value as the path to the folder containing vcpkg
* [Visual Studio Community 2019](https://visualstudio.microsoft.com/)
	* Desktop development with C++
* [CommonLibSSE](https://github.com/powerof3/CommonLibSSE/tree/dev)
	* You need to build from the powerof3/dev branch
	* Add this as as an environment variable `CommonLibSSEPath`

## Register Visual Studio as a Generator
* Open `x64 Native Tools Command Prompt`
* Run `cmake`
* Close the cmd window

## Building
```
git clone https://github.com/Osmosis-Wrench/OxygenMeter2.git
cd OxygenMeter2
cmake -B build -S .
```
## License
[MIT](LICENSE)

## Fork: Skyrim 1.7.x

The source already targets Skyrim 1.7.x through its CommonLibSSE submodule. This fork only moves the vcpkg baseline in `vcpkg.json` to a current vcpkg: the submodule's `commonlib-shared` port asks for newer dependency versions than the old baseline knows about, so the old baseline no longer configures.

Build with `cmake --preset vs2026-ae` and `cmake --build --preset vs2026-ae`, with `VCPKG_ROOT` pointing at a vcpkg checkout from October 2026 or later. The DLL declares compatibility with Skyrim 1.7.104 only; older game versions keep using the earlier release. The release zip contains only the DLL: install Oxygen Meter 2 from Nexus first and let the DLL overwrite its own.
