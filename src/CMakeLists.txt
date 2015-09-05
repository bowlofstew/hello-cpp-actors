externalproject_add (
        actor-framework
        GIT_REPOSITORY https://github.com/actor-framework/actor-framework.git
        GIT_TAG 7ede7f2af53a0a1b0f4d148f8197e4d92a2e92b5
        SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/../thirdparty/actor-framework
        CONFIGURE_COMMAND ./configure --prefix=${CMAKE_INSTALL_PREFIX}
        BUILD_COMMAND make
        BUILD_IN_SOURCE 1
        INSTALL_COMMAND make install
)
set(SOURCES main.cpp)
add_executable(hello-actors ${SOURCES})
add_dependencies(hello-actors actor-framework)