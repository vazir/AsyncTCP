set(requires
    "arduino-esp32"
)

set(sources
    "src/AsyncTCP.cpp"
)

# register_component() is now deprecated and will be removed in IDF v.5
# See: https://docs.espressif.com/projects/esp-idf/en/stable/esp32/api-guides/build-system.html#no-longer-available-in-cmake
idf_component_register(
    SRCS "${sources}"
    INCLUDE_DIRS "src"
    REQUIRES "${requires}"
)

target_compile_options(${COMPONENT_TARGET} PRIVATE -fno-rtti)
