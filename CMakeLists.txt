cmake_minimum_required(VERSION 3.8)

PROJECT(dmnbt-cpp)

LIST(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
INCLUDE(cmake/ModuleImport.cmake)
INCLUDE(cmake/ModuleCompileOptions.cmake)
ModuleSetCompileOptions()
ModuleSetWinCompilerFlags()

LibImport("dmnbt-cpp" "src/nbt")
ExeImport("tools" "dmnbt-cpp")

if (PROJECT_IS_TOP_LEVEL)
    ExeImport("test" "dmnbt-cpp")
endif(PROJECT_IS_TOP_LEVEL)
