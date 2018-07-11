# Learn-CMake

## CMakeLists.txt

* Read [official description][official_des]. Please bear in mind that order __DOES__ count.
	* Required CMake Version `cmake_minimum_required(2.8.3)`
	* Package Name `project(ur_proj_name)`
	* Find other CMake/ Catkin packages needed for build `find_package()`
	* Message/ Service/ Action Generators `add_message_files()` `add_service_files()` `add_action_files()`
	* Specify package build info export `catkin_package()`
	* Libraries/ Executables to build `add_library()` `add_executable()` `target_link_libraries()`
* By default, `CMAKE_PREFIX_PATH` searches in lib/ for libraries, include/ for headers, and bin/ for programs.
[official_des]:http://wiki.ros.org/catkin/CMakeLists.txt
