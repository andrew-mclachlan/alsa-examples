# alsa-examples

## Reference

https://www.linuxjournal.com/article/6735

### Required Software ###

#### Apache Ant ####

1. `sudo apt install ant`
2. Alternatively, download and extract Apache Ant https://ant.apache.org.
    * Ensure that Apache Ant is in your PATH.
3. Install Apache Contrib (https://sourceforge.net/projects/ant-contrib/files/ant-contrib/1.0b3/ant-contrib-1.0b3-bin.zip/download)
    * Download, unzip and copy ant-contrib*.jar to your Apache Ant installation's lib directory.

#### CMake ####

1. `sudo apt install cmake`

### ALSA library support

1. `sudo apt install libasound2-dev`

## Build sample application

1. `ant`

## Run sample application

1. `./Artifacts/alsa-examples < ../sounds/windchimes.wav`

