FROM mcr.microsoft.com/devcontainers/python:3.12-bullseye

RUN apt-get update && apt-get install -y \
    xz-utils \
    ffmpeg \
    pipewire \
    alsa-utils \
    python3-pyqt5 \
    python3-pyqt5.qtwebengine \
    python3-pyqt5.qtwebchannel \
    libqt5webkit5-dev

RUN mkdir -p /etc/alsa/conf.d

RUN echo "\
pcm.!default {\n\
    type pipewire\n\
    playback_node \"-1\"\n\
    capture_node \"-1\"\n\
    hint {\n\
        show on\n\
        description \"Default ALSA Output (currently PipeWire Media Server)\"\n\
    }\n\
}\n\
\n\
ctl.!default {\n\
    type pipewire\n\
}" >> /etc/alsa/conf.d/99-pipewire-default.conf
