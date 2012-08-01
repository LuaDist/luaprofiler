# Copyright (C) 2007-2012 LuaDist.
# Created by Peter Kapec
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( luaprofiler C )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )
include ( lua )

# LuaProfiler modules
set ( LUAPROFILER_SRC src/clocks.c src/core_profiler.c src/function_meter.c src/stack.c 
  src/lua50_profiler.c )
install_lua_module ( profiler ${LUAPROFILER_SRC} src/profiler.def )

# Install analyzer
install_lua_executable ( summary src/analyzer/summary.lua )

# Install documentation
install_data ( README )
install_doc ( doc/ )
