This page is a work-in-progress

## CMake options

stub

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

oal=$(brew list openal-soft --versions | cut -d' ' -f2)
vpx=$(brew list libvpx --versions | cut -d' ' -f2)

oal=/opt/homebrew/Cellar/openal-soft/$oal
vpx=/opt/homebrew/Cellar/libvpx/$vpx

cmake                                       \
  -DCMAKE_BUILD_TYPE=RelWithDebInfo         \
  -DCMAKE_EXPORT_COMPILE_COMMANDS=ON        \
  -DBUILD_SHARED_LIBS=OFF                   \
  -DOPENAL_INCLUDE_DIR=$oal/include/AL      \
  -DOPENAL_LIBRARY=$oal/lib/libopenal.dylib \
  -DVPX_INCLUDE_DIR=$vpx/include            \
  -DVPX_LIBRARIES=$vpx/lib/libvpx.a         \
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

Make sure you have Python3, [CMake](https://cmake.org/download/#latest) and [Microsoft Visual Studio Community](https://visualstudio.microsoft.com/vs/community/) installed (only 2019 and above are officially supported). Visual Studio will need the "Desktop development with C++" workflow enabled. If you wish to stay up-to-date with UZDoom development, you can use [Git](https://git-scm.com/install/windows) to clone the repo. Otherwise, you can download the source as a ZIP from the `Code` button on the Code tab (make sure to extract it if you do).

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

    - [soft_oal.dll](https://github.com/kcat/openal-soft/releases/1.23.1) specifically `openal-soft-1.23.1-bin/bin/Win64/soft_oal.dll`
    - [sndfile.dll](https://github.com/libsndfile/libsndfile/releases/1.2.2) specifically `libsndfile-1.2.2-win64/bin/sndfile.dll`

### CMake CLI Instructions

stub