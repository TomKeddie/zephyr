# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.20.0)

find_package(Zephyr HINTS $ENV{ZEPHYR_BASE})
project(app)

target_sources(app PRIVATE
  testlib/bs_main.c
  testlib/adv.c
  testlib/connect.c
  testlib/scan.c
  testlib/security.c
  testlib/att_read.c
  testlib/att_write.c
  testlib/bs_sync.c
  testlib/conn_wait.c
  main.c
)

zephyr_include_directories(
  ${BSIM_COMPONENTS_PATH}/libPhyComv1/src/
  ${BSIM_COMPONENTS_PATH}/libUtilv1/src/
)
