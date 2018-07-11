# Learn-CMake

## CMakeLists.txt

* Read [official description](http://wiki.ros.org/catkin/CMakeLists.txt "ROS Documentation"). Please bear in mind that order __DOES__ count.
	* Required CMake Version `cmake_minimum_required(2.8.3)`
	* Package Name `project(HelloWorld)`
	* Find other CMake/ Catkin packages needed for build `find_package()`
	* Message/ Service/ Action Generators `add_message_files()` `add_service_files()` `add_action_files()`
	* Specify package build info export `catkin_package()`
	* Libraries/ Executables to build `add_library()` `add_executable()` `target_link_libraries()`
* By default, `CMAKE_PREFIX_PATH` searches in _lib/_ for libraries, _include/_ for headers, and _bin/_ for programs.
* `include_directories(include)` adds _.h_ headers in _include/_ and `link_directories(lib)` adds _.so_ libraries in _lib/_ into compilation.
* `find_package(OpenCV REQUIRED)` searches corresponding _.so_ in `/usr/local/lib` or `/usr/lib`. If found, variable `OpenCV_LIBS` is valid.
* `file(GLOB SOURCES "src/*.cpp")` find all _src/_ files ended with _.cpp_ and handle this list with the variable `SOURCES`.
* The named `target` in `target_link_libraries()` must have been created in the current directory by a command such as `add_executable()` or `add_library()`.