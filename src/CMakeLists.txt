externalproject_add (
        actor-framework
        GIT_REPOSITORY https://github.com/actor-framework/actor-framework.git
        GIT_TAG d9e99842449752ec777beca1c21aff1c45a5008b
        SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/../thirdparty/actor-framework
        CONFIGURE_COMMAND ./configure --prefix=${CMAKE_INSTALL_PREFIX}
        BUILD_COMMAND make
        BUILD_IN_SOURCE 1
        INSTALL_COMMAND make install
)
set(SOURCES main.cpp)
add_executable(hello-actors ${SOURCES})
add_dependencies(hello-actors actor-framework)