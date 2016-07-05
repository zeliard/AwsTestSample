cmake_minimum_required(VERSION 2.8)
project(ddb-sample)

#this will locate the aws sdk for c++ package so that we can use its targets
find_package(aws-sdk-cpp)

add_definitions(-DUSE_IMPORT_EXPORT)

add_executable(ddb-sample 
	main.cpp 
	LockFreeMemorySystem.cpp 
	LockFreeExecutor.cpp 
	ObjectPool.h 
	LockFreeMemorySystem.h 
	LockFreeExecutor.h
)
 
#since we called find_package(), this will resolve all dependencies, header files, and cflags necessary
#to build and link your executable. 
target_link_libraries(ddb-sample aws-cpp-sdk-dynamodb)
