cmake_minimum_required(VERSION 3.12)

# rest of your project
add_executable(usb_analog_mic
    main.c
    usb_descriptors.c
    usb_microphone.c
)

# I'm not sure which of these usb_microphone instances should be changed to usb_analog_mic
target_include_directories(usb_analog_mic PRIVATE ${CMAKE_CURRENT_LIST_DIR})

target_link_libraries(usb_analog_mic PRIVATE tinyusb_device tinyusb_board pico_analog_microphone)

# create map/bin/hex/uf2 file in addition to ELF.
pico_add_extra_outputs(usb_analog_mic)
