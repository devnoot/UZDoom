This page is a work-in-progress

## CMake options

```c
// Build Abseil as a single shared library (always enabled for Windows)
ABSL_BUILD_MONOLITHIC_SHARED_LIBS:BOOL=OFF

// If ON, Abseil will build libraries that you can use to write tests against Abseil code. This option requires that Abseil is configured to use GoogleTest.
ABSL_BUILD_TEST_HELPERS:BOOL=OFF

// Enable install rule
ABSL_ENABLE_INSTALL:BOOL=OFF

// If set, download GoogleTest from this URL
ABSL_GOOGLETEST_DOWNLOAD_URL:STRING=

// If ABSL_USE_GOOGLETEST_HEAD is OFF and ABSL_GOOGLETEST_URL is not set, specifies the directory of a local GoogleTest checkout.
ABSL_LOCAL_GOOGLETEST_DIR:PATH=/usr/src/googletest

// Link static runtime libraries
ABSL_MSVC_STATIC_RUNTIME:BOOL=OFF

// Use CMake C++ standard meta features (e.g. cxx_std_17) that propagate to targets that link to Abseil
ABSL_PROPAGATE_CXX_STD:BOOL=ON

// If ON, Abseil will assume that the targets for GoogleTest are already provided by the including project. This makes sense when Abseil is used with add_subdirectory.
ABSL_USE_EXTERNAL_GOOGLETEST:BOOL=OFF

// If ON, abseil will download HEAD from GoogleTest at config time.
ABSL_USE_GOOGLETEST_HEAD:BOOL=OFF

// Silence warnings in Abseil headers by marking them as SYSTEM includes
ABSL_USE_SYSTEM_INCLUDES:BOOL=OFF

// Build exmaple
BUILD_EXAMPLE:BOOL=OFF

// Enable Flatpak-specific build options
BUILD_FLATPAK:BOOL=OFF

// Build non-free assets used by commercial games
BUILD_NONFREE:BOOL=ON

// Build the testing tree.
BUILD_TESTING:BOOL=ON

// Choose the type of build, options are: Debug Release RelWithDebInfo MinSizeRel.
CMAKE_BUILD_TYPE:STRING=Debug

// Install path prefix
CMAKE_INSTALL_PREFIX:PATH=/usr/local

// Build dap with address sanitizer
CPPDAP_ASAN:BOOL=OFF

// Build example applications
CPPDAP_BUILD_EXAMPLES:BOOL=OFF

// Build fuzzer
CPPDAP_BUILD_FUZZER:BOOL=OFF

// Build tests
CPPDAP_BUILD_TESTS:BOOL=OFF

// Build and install dap examples into vscode extensions directory
CPPDAP_INSTALL_VSCODE_EXAMPLES:BOOL=OFF

// Build dap with memory sanitizer
CPPDAP_MSAN:BOOL=OFF

// Build dap with thread sanitizer
CPPDAP_TSAN:BOOL=OFF

// Use googletest with find_package()
CPPDAP_USE_EXTERNAL_GTEST_PACKAGE:BOOL=OFF

// Use JsonCpp with find_package()
CPPDAP_USE_EXTERNAL_JSONCPP_PACKAGE:BOOL=OFF

// Use nlohmann_json with find_package() instead of building internal submodule
CPPDAP_USE_EXTERNAL_NLOHMANN_JSON_PACKAGE:BOOL=OFF

// Use RapidJSON with find_package()
CPPDAP_USE_EXTERNAL_RAPIDJSON_PACKAGE:BOOL=OFF

// Treat warnings as errors
CPPDAP_WARNINGS_AS_ERRORS:BOOL=OFF

// Load GTK+ at runtime instead of compile time
DYN_GTK:BOOL=ON

// Dynamically load libmpg123
DYN_MPG123:BOOL=ON

// Dynamically load OpenAL
DYN_OPENAL:BOOL=ON

// Dynamically load libsndfile
DYN_SNDFILE:BOOL=ON

// Enable Include-What-You-Use analysis
ENABLE_IWYU:BOOL=ON

// Path to a library.
EXECINFO_LIBRARY:FILEPATH=EXECINFO_LIBRARY-NOTFOUND

// Turn on cross compiling.
FORCE_CROSSCOMPILE:BOOL=OFF

// Use internal bzip2
FORCE_INTERNAL_BZIP2:BOOL=OFF

// Use internal cppdap
FORCE_INTERNAL_CPPDAP:BOOL=ON

// Turn off LTO even if it would be possible to use it.
FORCE_NO_LTO:BOOL=OFF

// Enable GLES2 support
HAVE_GLES2:BOOL=ON

// Enable Vulkan support
HAVE_VULKAN:BOOL=ON

// Directory where the zdoom documentation will be placed during install.
INSTALL_DOCS_PATH:STRING=share/doc/uzdoom

// Directory where the executable will be placed during install.
INSTALL_PATH:STRING=bin

// Directory where zdoom.pk3 will be placed during install.
INSTALL_PK3_PATH:STRING=share/games/uzdoom

// Directory where soundfonts and WOPL/WOPN banks will be placed during install.
INSTALL_SOUNDFONT_PATH:STRING=share/games/uzdoom

// Path to a program.
IWYU:FILEPATH=IWYU-NOTFOUND

// Set if the compiler will complain about implicit switch fallthrough
LIBGME_SWITCH_FALLTHROUGH:BOOL=1

// Path to a library.
LIBRT:FILEPATH=/usr/lib/librt.a

// Disable GTK+ dialogs (Not applicable to Windows)
NO_GTK:BOOL=OFF

// Disable OpenAL sound support
NO_OPENAL:BOOL=OFF

// Disable usage of OpenMP
NO_OPENMP:BOOL=OFF

// Disable SDL joystick support (Not applicable to Windows)
NO_SDL_JOYSTICK:BOOL=OFF

// Do not strip Release or MinSizeRel builds
NO_STRIP:BOOL=OFF

// Do not list files processed by zipdir
PK3_QUIET_ZIPDIR:BOOL=OFF

// Enable profiling with gprof for Debug and RelWithDebInfo build types.
PROFILE:BOOL=0

// Path to a library.
SDL2MAIN_LIBRARY:FILEPATH=/usr/lib/libSDL2main.a

// Path to a file.
SDL2_INCLUDE_DIR:PATH=/usr/include

// Where the SDL2 Library can be found
SDL2_LIBRARY:STRING=/usr/lib/libSDL2main.a;/usr/lib/libSDL2.so

// Enable sending of anonymous hardware statistics
SEND_ANON_STATS:BOOL=ON

// Set global progdir based on CMake Install Dir
SYSTEMINSTALL:BOOL=OFF

// Enable support for Spectrum ZX music emulation
USE_GME_AY:BOOL=1

// Enable support for Game Boy music emulation
USE_GME_GBS:BOOL=1

// Enable Sega MegaDrive/Genesis music emulation
USE_GME_GYM:BOOL=1

// Enable PC Engine/TurboGrafx-16 music emulation
USE_GME_HES:BOOL=1

// Enable MSX or other Z80 systems music emulation
USE_GME_KSS:BOOL=1

// Enable NES NSF music emulation
USE_GME_NSF:BOOL=1

// Enable NES NSFE and NSF music emulation
USE_GME_NSFE:BOOL=1

// Enable Atari SAP music emulation
USE_GME_SAP:BOOL=1

// Enable SNES SPC music emulation
USE_GME_SPC:BOOL=1

// Enable Sega VGM/VGZ music emulation
USE_GME_VGM:BOOL=1

// Use Vulkan Wayland WSI integration
VULKAN_USE_WAYLAND:BOOL=OFF

// Use Vulkan xlib (X11) WSI integration
VULKAN_USE_XLIB:BOOL=ON

// Enable the Address Sanitizer
WITH_ASAN:BOOL=0

// Enable the Undefined Behavior Sanitizer
WITH_UBSAN:BOOL=0

// Enable software renderer
ZDOOM_ENABLE_SWR:BOOL=ON

// Name of the executable to create
ZDOOM_EXE_NAME:FILEPATH=uzdoom

// Directory where zdoom.pk3 and the executable will be created.
ZDOOM_OUTPUT_DIR:PATH=/home/n/src/UZDoom/build
```

## Linux

### Tools/Dependencies

<!-- If changing requirements or distro-specific package lists, please update the date for that section -->
<!-- Requirements updated 2025/11/20 -->

For tooling, you need:

* a modern c++ compiler
* python3
* cmake
* git
* ninja

For libraries, you need the development headers of:

* bzip2
* OpenMP
* OpenAL
* SDL2
* libvpx
* libwebp
* wayland++

Below are a list of packages for a number of distros:

<details><summary>Debian</summary>
<!-- Packages updated 2025/11/20 -->

```shell
# tools

sudo apt-get install \
  build-essential    \
  git                \
  cmake              \
  ninja-build

# dependencies

sudo apt-get install \
  libbz2-dev         \
  libomp-dev         \
  libopenal-dev      \
  libsdl2-dev        \
  libvpx-dev         \
  libwebp-dev        \
  waylandpp-dev
```

</details>

<details><summary>Fedora</summary>
<!-- Packages updated 2025/11/20 -->

```shell
# tools

# TODO

# dependencies

# TODO
```

</details>

<details><summary>Arch</summary>
<!-- Packages updated 2025/11/20 -->

```shell
# tools

pacman -S    \
  base-devel \
  git        \
  cmake      \
  ninja

# dependencies

pacman -S     \
  bzip2       \
  openmp      \
  openal      \
  sdl2-compat \
  libvpx      \
  libwebp     \
  waylandpp
```

</details>

<details><summary>SUSE</summary>
<!-- Packages updated 2025/11/20 -->

```shell
# tools

# TODO

# dependencies

# TODO
```

</details>

### Compilation

```shell
# pull

git clone https://github.com/UZDoom/UZDoom.git

# prepare

mkdir -p UZDoom/build

cd UZDoom/build

cmake                                \
  -DCMAKE_BUILD_TYPE=RelWithDebInfo  \
  -DCMAKE_EXPORT_COMPILE_COMMANDS=ON \
  -G Ninja                           \
  ..

# build

cmake --build .
```

## MacOS

[Homebrew](https://brew.sh/) and [Xcode](https://developer.apple.com/xcode/) required.

```shell
# dependencies

brew install  \
  cmake       \
  fluid-synth \
  libvpx      \
  molten-vk   \
  ninja       \
  openal-soft \
  pkgconf     \
  sdl2        \
  vulkan-volk

# pull

git clone https://github.com/UZDoom/UZDoom.git

# prepare

mkdir -p UZDoom/build

cd UZDoom/build

cmake                                       \
  -DCMAKE_BUILD_TYPE=RelWithDebInfo         \
  -DCMAKE_EXPORT_COMPILE_COMMANDS=ON        \
  -DBUILD_SHARED_LIBS=OFF                   \
  -DOPENAL_INCLUDE_DIR=$(brew --prefix openal-soft)/include/AL       \
  -DOPENAL_LIBRARY=$(brew --prefix openal-soft)/lib/libopenal.dylib  \
  -DVPX_INCLUDE_DIR=$(brew --prefix libvpx)/include                  \
  -DVPX_LIBRARIES=$(brew --prefix libvpx)/lib/libvpx.a               \
  -DDYN_OPENAL=OFF                          \
  -DHAVE_VULKAN=ON                          \
  -DHAVE_GLES2=OFF                          \
  -G Ninja                                  \
  ..

# build

cmake --build .
```

## Windows

These instructions will be for compiling with CMake as this is considered the simplest and most well-supported way to compile on Windows. 32-bit versions of UZDoom are not supported.

Make sure you have [Python3](https://www.python.org/downloads/), [CMake](https://cmake.org/download/#latest) and [Microsoft Visual Studio Community](https://visualstudio.microsoft.com/vs/community/) installed (only 2019 and above are officially supported). Visual Studio will need the "Desktop development with C++" workflow enabled. If you wish to stay up-to-date with UZDoom development, you can use [Git](https://git-scm.com/install/windows) to clone the repo. Otherwise, you can download the source as a ZIP from the `Code` button on the Code tab (make sure to extract it if you do).

You can install python by running in a terminal `winget install python3`

### CMake GUI Instructions

1. Open CMake GUI and, for the source code option, select the folder containing the source. For the build destination option, select the same folder and add `/build` to the end of it.
2. Press the Configure button. When asked if you'd like to create the `build` folder, select yes. You will then be prompted which version of Visual Studio you'd like to use. Select the one you have downloaded and press Finish. If configured correctly, you should see no error messages at the bottom of the console.
3. Click Generate. You will now have the solution available inside your folder containing the source.
4. Go into the `build` folder CMake created and open the Visual Studio solution (UZDoom.sln). By default it will have the Debug build ready to compile. In the top, select the drop down where it says Debug and change this to RelWithDebInfo.
5. Under the Build menu, select Build Solution. If compiled correctly, there should be no errors at the bottom of the console.
6. Within your `build` folder should now be a RelWithDebInfo folder (or whichever version you decided to compile). This will contain the executable and engine data needed to start UZDoom.

7. Make sure you have `soft_oal.dll` and `sndfile.dll` included in the folder with your executable for full audio support. By default these do not come with the project but can be copied from the latest [UZDoom release](https://github.com/UZDoom/UZDoom/releases).

   Alternatively, you can collect the required dlls from their respective project's github releases:

    * [soft_oal.dll](https://github.com/kcat/openal-soft/releases/1.23.1) specifically `openal-soft-1.23.1-bin/bin/Win64/soft_oal.dll`
    * [sndfile.dll](https://github.com/libsndfile/libsndfile/releases/1.2.2) specifically `libsndfile-1.2.2-win64/bin/sndfile.dll`

### CMake CLI Instructions

stub

