project('libsx1302_hal', 'c', default_options: [
  'buildtype=minsize', 
  'c_std=c99', 
])

# internal incdirs and srcsfiles
libsx1302_incdirs = []
libsx1302_srcs    = []

# Add sx1302_hal file
libsx1302_incdirs += include_directories('inc/')

libsx1302_srcs += ['src/base64.c']
libsx1302_srcs += ['src/loragw_ad5338r.c']
libsx1302_srcs += ['src/loragw_aux.c']
libsx1302_srcs += ['src/loragw_cal.c']
libsx1302_srcs += ['src/loragw_com.c']
libsx1302_srcs += ['src/loragw_debug.c']
libsx1302_srcs += ['src/loragw_gps.c']
libsx1302_srcs += ['src/loragw_hal.c']
libsx1302_srcs += ['src/loragw_i2c.c']
libsx1302_srcs += ['src/loragw_lbt.c']
libsx1302_srcs += ['src/loragw_mcu.c']
libsx1302_srcs += ['src/loragw_reg.c']
libsx1302_srcs += ['src/loragw_spi.c']
libsx1302_srcs += ['src/loragw_stts751.c']
libsx1302_srcs += ['src/loragw_sx1250.c']
libsx1302_srcs += ['src/loragw_sx125x.c']
libsx1302_srcs += ['src/loragw_sx1261.c']
libsx1302_srcs += ['src/loragw_sx1302.c']
libsx1302_srcs += ['src/loragw_sx1302_rx.c']
libsx1302_srcs += ['src/loragw_sx1302_timestamp.c']
libsx1302_srcs += ['src/loragw_usb.c']
libsx1302_srcs += ['src/parson.c']
libsx1302_srcs += ['src/sx1250_com.c']
libsx1302_srcs += ['src/sx1250_spi.c']
libsx1302_srcs += ['src/sx1250_usb.c']
libsx1302_srcs += ['src/sx125x_com.c']
libsx1302_srcs += ['src/sx125x_spi.c']
libsx1302_srcs += ['src/sx1261_com.c']
libsx1302_srcs += ['src/sx1261_spi.c']
libsx1302_srcs += ['src/sx1261_usb.c']
libsx1302_srcs += ['src/tinymt32.c']

#=============================================================================#
libsx1302_srcs = files(libsx1302_srcs)

# needed defines for the HAL Driver
libsx1302_c_args = []

# Libc dependency
dependencies = meson.get_compiler('c').find_library('c', required: false)

libsx1302_drivers_lib = static_library('libsx1302',
  include_directories : libsx1302_incdirs,
  sources : libsx1302_srcs,
  c_args : libsx1302_c_args,
  dependencies : dependencies,
)

libsx1302_drivers_dep = declare_dependency(
  include_directories : libsx1302_incdirs,
  link_with : libsx1302_drivers_lib,
  compile_args : libsx1302_c_args,
  dependencies : dependencies,
)