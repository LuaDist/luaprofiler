# Copyright (C) 2007-2011 LuaDist.
# Created by Peter Kapec
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

PROJECT(luaprofiler C)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
INCLUDE(dist.cmake)

# LuaProfiler modules
SET (LUAPROFILER_SRC src/clocks.c src/core_profiler.c src/function_meter.c src/stack.c src/lua50_profiler.c)
INSTALL_LUA_MODULE(profiler ${LUAPROFILER_SRC} src/profiler.def)

# Install analyzer
INSTALL_LUA_EXECUTABLE(summary src/analyzer/summary.lua )

# Install documentation
INSTALL_DATA(README)
INSTALL_DOC(doc/)
