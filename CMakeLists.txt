# The MIT License (MIT)
#
# Copyright (c) 2018 Mateusz Pusz
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

cmake_minimum_required(VERSION 3.16)
project(stamp)

# set path to custom cmake modules
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake-scripts/cmake")

# include common tools and workarounds
include(scripts)

# use Conan configuration if available
conan_init(cmake)

set(CMAKE_CXX_STANDARD 17)
add_compile_options(-g -O3 -Wall -Wextra)

# this is not nice, but needed to add gv to includes in compiler_database for .hpp files which drives clangd highlighting
# include_directories(include include/toolbelt include/ryu /usr/include/graphviz)

# find_package(libmongocxx REQUIRED)
# add_executable(translupe apps/translupe.cpp)
# target_link_libraries(translupe PUBLIC ${LIBMONGOCXX_LIBRARIES} cgraph gvc)
# target_include_directories(translupe PUBLIC ${LIBMONGOCXX_INCLUDE_DIRS} /usr/include/graphviz)
