Linux:

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