# UxPlay

Fork of [UxPlay](https://github.com/antimof/UxPlay)

## Features
1. Based on Gstreamer.
1. Video and audio are supported out of the box.
3. Gstreamer decoding is plugin agnostic. Uses accelerated decoders if availible. VAAPI is preferable.
4. Automatic screen orientation.

## Building
```bash
sudo apt-get install cmake
sudo apt-get install libssl-dev libavahi-compat-libdnssd-dev \
                     libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev \
                     gstreamer1.0-libav gstreamer1.0-plugins-bad

sudo apt-get install gstreamer1.0-vaapi # For Intel graphics
# (UxPlay crashes if you dont have Intel graphics, but installed it)

mkdir build
cd build
cmake ..
# Alternatively (for higher optimization level and/or installation):
# cmake .. -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=path/to/install/dir
make
```

## Start
```bash
AVAHI_COMPAT_NOWARN=1 ./uxplay
```

As a work around for sharing the uxplay window from a browser you can manually set the title using `xdotool selectwindow set_window --name "ux"` (and selecting the window by clicking).

