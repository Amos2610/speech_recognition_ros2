# speech recognition pkgs

## How to Clone

```bash
git clone --recursive https://github.com/yuzoo0226/speech_recognition_ros2.git
```

## Environments

- Ubuntu22.04
- Humble

## How to install dependencies

```bash
sudo apt-get install update
sudo apt-get install -y portaudio19-dev python3-pyaudio 

## How to launch audio publisher/capture node

```bash
cd <your_workspace>
colcon build --cmake-args -DCMAKE_BUILD_TYPE=Release --packages-up-to audio_common
source install/setup.bash
# ros2 run audio_common audio_captuer_node
# nishidalab speaker microphone
ros2 run audio_common audio_capturer_node \
  --ros-args -p rate:=16000 -p channels:=1 -p chunk:=512
```


## How to launch Speech recognition server node

```bash
cd <your_workspace>
colcon build
ros2 run speech_recognition_node speech_recognition_node
```

## Try Speech recognition client node

```bash
cd <your_workspace>
colcon build
ros2 run speech_recognition_node utils
```