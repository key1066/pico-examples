add_executable(mpu9250_spi
        mpu9250_spi.c
        )

# Pull in our pico_stdlib which aggregates commonly used features
target_link_libraries(mpu9250_spi pico_stdlib)

# enable usb output, disable uart output
pico_enable_stdio_usb(mpu9250_spi 1)
pico_enable_stdio_uart(mpu9250_spi 0)

# Pull in our (to be renamed) simple get you started dependencies
target_link_libraries(mpu9250_spi pico_stdlib hardware_spi)

# create map/bin/hex file etc.
pico_add_extra_outputs(mpu9250_spi)

# add url via pico_set_program_url
example_auto_set_url(mpu9250_spi)
