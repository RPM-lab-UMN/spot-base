# spot-base

Base container environment for spot robot development. Provides a ROS noetic environment with the Spot SDK and ROS driver included.

## Working with the container
TODO

## Building/Running the container manually

> [!NOTE]
> These images are automatically built, and can be pulled from docker hub as `ryroche/spot-base:nogpu` and `ryroche/spot-base:nvidia` respectively. The scripts for manually building and running the images are meant for testing purposes, and should only be used if the images on Docker Hub don't work for some reason

> [!WARNING]
> The `spot-base` image is meant to be used as a **base** for your project. Do not put your project code in this repository. Instead, make a new docker container for your project that uses `spot-base` as its base image.

1. Clone the repository

2. In the root of the repository, run

    ```bash
    ./build.sh
    ```

    The script will give you the option to build the NVIDIA GPU-enabled image, or the non-GPU image.

3. Then, run

    ```bash
    ./run.sh
    ```

