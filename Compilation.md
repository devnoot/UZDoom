This page is a work-in-progress

## CMake options

stub

## Linux

```shell
# dependencies

sudo apt-get install \
  build-essential    \
  libsdl2-dev        \
  libvpx-dev         \
  libgtk2.0-dev      \
  libwebp-dev        \
  waylandpp-dev      \
  ninja-build

# pull

git clone https://github.com/UZDoom/UZDoom.git

# prepare

mkdir -p UZDoom/build

cd UZDoom/build

cmake                                \
  -DCMAKE_BUILD_TYPE=Debug           \
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
  -DCMAKE_BUILD_TYPE=Debug                  \
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

stub