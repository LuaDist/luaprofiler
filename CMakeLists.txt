# Copyright (C) 2007-2009 LuaDist.
# Created by Peter Kapec
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

PROJECT(luaprofiler C)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
INCLUDE(dist.cmake)

# LuaProfiler modules
SET (LUAPROFILER_SRC src/clocks.c src/core_profiler.c src/function_meter.c src/stack.c src/lua50_profiler.c)

ADD_LUA_MODULE(profiler ${LUAPROFILER_SRC} src/profiler.def)

# Install LuaProfiler and analyzer
INSTALL (TARGETS profiler DESTINATION ${INSTALL_CMOD})
INSTALL (FILES src/analyzer/summary.lua DESTINATION ${INSTALL_BIN})

# Install documentation
INSTALL(FILES README DESTINATION ${INSTALL_DATA})
INSTALL(DIRECTORY doc DESTINATION ${INSTALL_DOC})
