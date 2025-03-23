cmake_minimum_required(VERSION 3.0)
project(Blackb0x)

set(OBJC_SRC main.m Source/IPSW.h Source/IPSW.h Source/IPSW.mm)

set(GNUSTEP_CONFIG "gnustep-config")

execute_process(COMMAND ${GNUSTEP_CONFIG} --debug-flags
        OUTPUT_VARIABLE OBJECTIVEC_COMPILE_FLAGS
        OUTPUT_STRIP_TRAILING_WHITESPACE)

execute_process(COMMAND ${GNUSTEP_CONFIG} --base-libs
        OUTPUT_VARIABLE OBJECTIVEC_LINK_OPTIONS
        OUTPUT_STRIP_TRAILING_WHITESPACE)

set(OBJECTIVEC_COMPILE_FLAGS "${OBJECTIVEC_COMPILE_FLAGS} -fblocks -fobjc-arc -fobjc-nonfragile-abi")

# add CoreFoundation and libdispatch
set(OBJECTIVEC_LINK_OPTIONS "${OBJECTIVEC_LINK_OPTIONS} -lgnustep-corebase -ldispatch")

set_property(SOURCE ${OBJC_SRC} APPEND_STRING PROPERTY COMPILE_FLAGS ${OBJECTIVEC_COMPILE_FLAGS})
add_executable(Blackb0xGUI ${OBJC_SRC})

target_include_directories(Blackb0xGUI PRIVATE Libraries)
separate_arguments(OBJECTIVEC_LINK_OPTIONS)
target_link_options(Blackb0xGUI PRIVATE ${OBJECTIVEC_LINK_OPTIONS})
