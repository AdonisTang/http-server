
include_directories(
    ${CMAKE_SOURCE_DIR}/
    ${CMAKE_SOURCE_DIR}/common/
    ${CMAKE_SOURCE_DIR}/src/
)

link_directories(
    ${CMAKE_SOURCE_DIR}/
    ${CMAKE_SOURCE_DIR}/common/
    ${CMAKE_SOURCE_DIR}/src/
)

link_directories(/opt/soft/libevent/libevent_install/lib)

set(SERVER_SRC
    main.cpp
    server.cpp
    worker.cpp
    handlers.cpp
)

ADD_EXECUTABLE(http-server ${SERVER_SRC})

target_include_directories(
        http-server
        PRIVATE
        /opt/soft/libevent/libevent_install/include/
)
target_link_libraries(http-server
    event
    pthread
)

