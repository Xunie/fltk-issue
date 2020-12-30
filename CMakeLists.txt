cmake_minimum_required( VERSION 3.0 )

project( problematicfltkproject
         LANGUAGES CXX )

add_subdirectory( git-submodules/fltk )

# At this point, pretty much all FLTK_* variables in CMake have completely messed values. But they DO exist!
# Go create a CMake build and run $ cmake -LA | egrep -i fltk
# .. and observe for yourself

message( "libraries: " ${FLTK_LIBRARIES} )
add_executable( main
    src/main.cpp
)

target_link_libraries( main
    PUBLIC
        ${FLTK_LIBRARIES}
)
