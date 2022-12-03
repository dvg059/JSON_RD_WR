#howto: build.
#build/cmake ../src
# -  access this CMakelists.txt file to create a make file in build dir

#build/make	
# - executes the makefile created by cmake, creates the exe(json_rd_wr)
#-------------------------------------------- 
cmake_minimum_required(VERSION 3.10)
# add library (name_of_library_output link_type{:STATIC, SHARED etc} 
#	src_1
#	src_2
#	)
add_library(
	json_lib STATIC
	dv_json_rd_wr.cpp
    cjson_mngr.cpp
    ../json/jsoncpp.cpp
)


include_directories("../json")
include_directories("../include")


# set the project name
project(MyProject VERSION 1.0.0)

# json_rd_wr: add_executable(name_of_exe_output, src_file1 src_file2, ...) 
#This would work but we want to learn librarys
add_executable(json_rd_wr dv_json_rd_wr.cpp)

# needed for linking the libray (say-hello) that we created
# exe that needs library - json_rd_wr
# how to lingk it: PRIVATE (very important)
# library were linkging to: say-hello form add_library up above
# target_link_libraries(name_of_exe_exe, link_type, name_of_library)
target_link_libraries(json_rd_wr PRIVATE json_lib)