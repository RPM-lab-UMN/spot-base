FROM ryroche/robobase:nogpu

# Install Spot SDK using pip
RUN pip3 install bosdyn-client bosdyn-mission bosdyn-api bosdyn-core

# Create ROS workspace for user project
RUN mkdir -p ~/spot_ws/src
WORKDIR /root/spot_ws/

# Download Spot Driver code
WORKDIR /root/spot_ws/src/
RUN git clone https://github.com/heuristicus/spot_ros.git .
WORKDIR /root/spot_ws/src/
# Change .gitmodules to use HTTPS instead of SSH
RUN sed -i 's/git@github.com:/https:\/\/github.com\//' .gitmodules
RUN git submodule init
RUN git submodule update

# Install and build spot driver code
RUN pip3 install -e spot_wrapper
RUN . /opt/ros/noetic/setup.sh && catkin build spot_driver spot_viz

# Have subsequent bash sessions start in the ROS workspace
RUN echo cd ~/spot_ws/ >> ~/.bashrc
RUN echo source devel/setup.bash >> ~/.bashrc
