cmake_minimum_required( VERSION 3.19.1 )

include(FetchContent)

FetchContent_Declare(json
  GIT_REPOSITORY https://github.com/ArthurSonzogni/nlohmann_json_cmake_fetchcontent
  GIT_TAG v3.7.3
)

FetchContent_GetProperties( json )
if (NOT json_POPULATED)
    message( STATUS "no json")
    FetchContent_Populate( json )
    add_subdirectory(${json_SOURCE_DIR} ${json_BINARY_DIR} EXCLUDE_FROM_ALL)
endif()

add_subdirectory(src)


