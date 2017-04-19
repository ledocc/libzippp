set(target zippp)


set(${target}_HEADER
    libzippp.h
    )

set(${target}_SRC
    libzippp.cpp
    )

add_library(${target}
    ${${target}_HEADER}
    ${${target}_SRC}
    )

target_link_libraries(${target}
    ZLIB::ZLIB
    LIBZIP::LIBZIP
    )


install(TARGETS ${target}
    RUNTIME DESTINATION "bin"
    ARCHIVE DESTINATION "lib"
    LIBRARY DESTINATION "lib"
    INCLUDES DESTINATION "include"
    )

install(FILES libzippp.h DESTINATION include)
