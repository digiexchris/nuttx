# ##########################################################################
# Common source files for RP2040 boards
# ##########################################################################

if(CONFIG_ARCH_BOARD_COMMON)
    set(SRCS
        rp2040_common_bringup.c
        rp2040_common_initialize.c
    )

    if(CONFIG_BOARDCTL_RESET)
        list(APPEND SRCS rp2040_reset.c)
    endif()

    if(CONFIG_SPI)
        list(APPEND SRCS rp2040_spi.c)
    endif()

    if(CONFIG_RP2040_I2C_DRIVER)
        list(APPEND SRCS rp2040_i2cdev.c)
    endif()

    if(CONFIG_RP2040_PWM)
        list(APPEND SRCS rp2040_pwmdev.c)
    endif()

    if(CONFIG_RP2040_SPI_DRIVER)
        list(APPEND SRCS rp2040_spidev.c)
    endif()

    if(CONFIG_RP2040_I2S)
        list(APPEND SRCS rp2040_i2sdev.c)
    endif()

    if(CONFIG_LCD_SSD1306)
        list(APPEND SRCS rp2040_ssd1306.c)
    endif()

    if(CONFIG_LCD_ST7789)
        list(APPEND SRCS rp2040_st7789.c)
    endif()

    if(CONFIG_LCD_ST7735)
        list(APPEND SRCS rp2040_st7735.c)
    endif()

    if(CONFIG_LCD_GC9A01)
        list(APPEND SRCS rp2040_gc9a01.c)
    endif()

    if(CONFIG_USBMSC)
        list(APPEND SRCS rp2040_usbmsc.c)
    endif()

    if(CONFIG_USBDEV_COMPOSITE)
        list(APPEND SRCS rp2040_composite.c)
    endif()

    if(CONFIG_RP2040_SPISD)
        list(APPEND SRCS rp2040_spisd.c)
    endif()

    if(CONFIG_SENSORS_BMP180)
        list(APPEND SRCS rp2040_bmp180.c)
    endif()

    if(CONFIG_SENSORS_BMP280)
        list(APPEND SRCS rp2040_bmp280.c)
    endif()

    if(CONFIG_SENSORS_INA219)
        list(APPEND SRCS rp2040_ina219.c)
    endif()

    if(CONFIG_ENC28J60)
        list(APPEND SRCS rp2040_enc28j60.c)
    endif()

    if(CONFIG_LCD_BACKPACK)
        list(APPEND SRCS rp2040_lcd_backpack.c)
    endif()

    if(CONFIG_BOARDCTL_UNIQUEID)
        list(APPEND SRCS rp2040_uniqueid.c)
    endif()

    if(CONFIG_NET_W5500)
        list(APPEND SRCS rp2040_w5500.c)
    endif()

    if(CONFIG_SENSORS_MAX6675)
        list(APPEND SRCS rp2040_max6675.c)
    endif()

    target_sources(board PRIVATE ${SRCS})

    target_link_libraries(board PRIVATE arch)
endif()
