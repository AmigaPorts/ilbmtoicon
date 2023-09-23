cmake_minimum_required(VERSION 3.14.0)
project(ilbmtoicon VERSION 1.0.0)

# Additional CMake modules
include(cmake/common/setup_amiga_common.cmake)

# Set up information for Aminet
add_project_info(
	"ilbmtoicon"
	"AROS"
	"util/cli"
	"m68k-amigaos"
)

get_verstring(VERSTRING)
add_compile_definitions(PRIVATE VERSION_STRING="${VERSTRING}")

find_package(PNG REQUIRED)
find_package(ZLIB REQUIRED)

# ilbmtoicon
add_executable(ilbmtoicon
    ilbmtoicon.c
)

install(TARGETS ilbmtoicon DESTINATION bin)


target_link_libraries(ilbmtoicon PRIVATE ${PNG_LIBRARY} ${ZLIB_LIBRARY})

set_target_properties(ilbmtoicon PROPERTIES LINKER_LANGUAGE C)

# infoinfo
add_executable(infoinfo
    infoinfo.c
)
install(TARGETS infoinfo DESTINATION bin)

set_target_properties(infoinfo PROPERTIES LINKER_LANGUAGE C)

add_aminet_readme_generator(ilbmtoicon "ilbmtoicon.readme")