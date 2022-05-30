# This is an auto generated Dockerfile for ros:desktop-full
# generated from docker_images/create_ros_image.Dockerfile.em
FROM osrf/ros:noetic-desktop-full-focal

# Install perception packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    ros-noetic-perception=1.5.0-1* \
    && rm -rf /var/lib/apt/lists/*

# install common packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    wget curl git python3-catkin-tools python3-osrf-pycommon \
    && rm -rf /var/lib/apt/lists/*

# Install zsh and OMzsh
RUN apt-get update -y
RUN apt-get install -yq zsh 
RUN rm -rf /var/lib/apt/lists/*
RUN chsh -s $(which zsh)
RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.2/zsh-in-docker.sh)" -- \
    -p git \
    -p https://github.com/zsh-users/zsh-autosuggestions \
    -p https://github.com/zsh-users/zsh-syntax-highlighting\
    -t tjkirch

# Overwrite the entry point to zsh
COPY ./ros_entrypoint.zsh /
ENTRYPOINT ["/ros_entrypoint.zsh"]
CMD ["zsh"]

