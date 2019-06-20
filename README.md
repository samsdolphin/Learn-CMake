# Learn-CMake

## CMakeLists.txt

* Read [official description](http://wiki.ros.org/catkin/CMakeLists.txt "ROS Documentation"). Please bear in mind that order __DOES__ count.
	* Required CMake Version `cmake_minimum_required(2.8.3)`
	* Package Name `project(HelloWorld)`
	* Find other CMake/ Catkin packages needed for build `find_package()`
	* Message/ Service/ Action Generators `add_message_files()` `add_service_files()` `add_action_files()`
	* Specify package build info export `catkin_package()`
	* Libraries/ Executables to build `add_library()` `add_executable()` `target_link_libraries()`
* By default, `CMAKE_PREFIX_PATH` searches in ___lib/___ for libraries, ___include/___ for headers, and ___bin/___ for programs.
* `include_directories(include)` adds ___.h___ headers in ___include/___ and `link_directories(lib)` adds ___.so___ libraries in ___lib/___ into compilation.
* `find_package(OpenCV REQUIRED)` searches corresponding ___.so___ in `/usr/local/lib` or `/usr/lib`. If found, variable `OpenCV_LIBS` is valid.
* `file(GLOB SOURCES "src/*.cpp")` find all ___src/___ files ended with ___.cpp___ and handle this list with the variable `SOURCES`.
* The named `target` in `target_link_libraries()` must have been created in the current directory by a command such as `add_executable()` or `add_library()`.
*

## Common Issues

* __Undefined reference to__
	* Forget to include or link libraries. Try to use `add_library()` or solution [above](##cmakelists.txt).
* __Class has no member named__
	* Include or link an old library, use `rospack list-names` to check if ROS duplicated.

## catkin_make

* Build one package only: `catkin_make -DCATKIN_WHITELIST_PACKAGES="foo;bar"`, please separate your individual package with `;`.
