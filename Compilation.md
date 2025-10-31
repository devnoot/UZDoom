This page is a work-in-progress

## CMake options

stub

## Linux

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

# pull

git clone https://github.com/UZDoom/UZDoom.git

# prepare

mkdir -p UZDoom/build

cd UZDoom/build

cmake                                \
  -DCMAKE_BUILD_TYPE=RelWithDebInfo  \
  -DCMAKE_EXPORT_COMPILE_COMMANDS=ON \
  -DBUILD_SHARED_LIBS=OFF            \
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

Make sure you have [CMake](https://cmake.org/download/#latest) and Microsoft Visual Studio Community installed (only 2019 and above are officially supported). Visual Studio will need the "Desktop development with C++" workflow enabled. If you wish to stay up-to-date with UZDoom development, you can use [Git](https://git-scm.com/install/windows) to clone the repo. Otherwise, you can download the source as a ZIP from the `Code` button on the Code tab (make sure to extract it if you do).

### CMake GUI Instructions

1. Open CMake GUI and, for the source code option, select the folder containing the source. For the build destination option, select the same folder and add `/build` to the end of it.

2. Press the Configure button. When asked if you'd like to create the `build` folder, select yes. You will then be prompted which version of Visual Studio you'd like to use. Select the one you have downloaded and press Finish. If configured correctly, you should see no error messages at the bottom of the console.

3. Click Generate. You will now have the solution available inside your folder containing the source.

4. Go into the `build` folder CMake created and open the Visual Studio solution (UZDoom.sln). By default it will have the Debug build ready to compile. In the top, select the drop down where it says Debug and change this to RelWithDebInfo.

5. Under the Build menu, select Build Solution. If compiled correctly, there should be no errors at the bottom of the console.

6. Within your `build` folder should now be a RelWithDebInfo folder (or whichever version you decided to compile). This will contain the executable and engine data needed to start UZDoom.

7. Make sure you have `openal32.dll` and `libsndfile-1.dll` included in the folder with your executable for full audio support. By default these do not come with the project but can be copied from any existing UZDoom release (currently GZDoom 4.14.2 is the latest).

### CMake CLI Instructions

stub