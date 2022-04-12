# This is an auto generated Dockerfile for ros:robot
# generated from docker_images/create_ros_image.Dockerfile.em
FROM mpirun_ros1_base_torch:1.8.2

# install ros packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    ros-noetic-robot=1.5.0-1* \
    && rm -rf /var/lib/apt/lists/*

