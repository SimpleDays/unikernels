cmake_minimum_required(VERSION 2.8.9)

# IncludeOS install location
if (NOT DEFINED ENV{INCLUDEOS_PREFIX})
  set(ENV{INCLUDEOS_PREFIX} /usr/local)
endif()
include($ENV{INCLUDEOS_PREFIX}/includeos/pre.service.cmake)
project (DNS)

# Human-readable name of your service
set(SERVICE_NAME "CETIC DNS Service")

# Name of your service binary
set(BINARY       "DNS")

# Source files to be linked with OS library parts to form bootable image
set(SOURCES
  service.cpp # ...add more here
  )

# To add your own include paths:
# set(LOCAL_INCLUDES ".")

# DRIVERS / PLUGINS:

set(DRIVERS
  virtionet     # Virtio networking
  # virtioblock # Virtio block device
  # ... Others from src/drivers
)

set(PLUGINS
  )

# include service build script
include($ENV{INCLUDEOS_PREFIX}/includeos/post.service.cmake)
