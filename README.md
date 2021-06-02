# Go-Chase-It Project

### Install Requirements
This project requires `gcc>=9` due to the use of `C++17`.
```sh
$ git clone https://github.com/daniel-m-campos/go-chase-it.git --recurse-submodules
$ cd go-chase-it
$ source install-ubuntu.sh
```

### Build the workspace
```sh
$ cd <path-to-repo-workspace>/go-chase-it/src
$ catkin_init_workspace
$ cd ..
$ catkin_make
```

### Running
#### Launch `my_robot`
```sh
$ cd <path-to-repo-workspace>/go-chase-it/
$ source devel/setup.bash
$ roslaunch my_robot world.launch 
```
#### Launch `ball_chaser`
Open another terminal:
```sh
$ cd <path-to-repo-workspace>/go-chase-it/
$ source devel/setup.bash
$ roslaunch ball_chaser ball_chaser.launch
```

### Source Structure
Note the addition of the `include` header directory in `ball_chaser`.
```sh
src
├── ball_chaser
│   ├── CMakeLists.txt
│   ├── include
│   │   └── ball_chaser
│   │       ├── drive_bot.h
│   │       └── process_image.h
│   ├── launch
│   │   └── ball_chaser.launch
│   ├── package.xml
│   ├── src
│   │   ├── drive_bot.cpp
│   │   └── process_image.cpp
│   └── srv
│       └── DriveToTarget.srv
├── CMakeLists.txt -> /opt/ros/melodic/share/catkin/cmake/toplevel.cmake
└── my_robot
    ├── CMakeLists.txt
    ├── launch
    │   ├── robot_description.launch
    │   └── world.launch
    ├── meshes
    │   └── hokuyo.dae
    ├── package.xml
    ├── urdf
    │   ├── my_robot.gazebo
    │   └── my_robot.xacro
    └── worlds
        └── HolidayCondo.world

```