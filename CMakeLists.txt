cmake_minimum_required(VERSION 3.15)

project(lua)

add_library(
        lua STATIC
        src/lapi.c      src/lctype.c  src/lfunc.c
        src/lmathlib.c src/loslib.c   src/ltable.c
        src/lundump.c src/lauxlib.c   src/ldblib.c
        src/lgc.c     src/lmem.c      src/lparser.c
        src/ltablib.c  src/lutf8lib.c src/lbaselib.c
        src/ldebug.c  src/linit.c   src/loadlib.c
        src/lstate.c   src/ltm.c      src/lvm.c
        src/lcode.c     src/ldo.c     src/liolib.c
        src/lobject.c   src/lstring.c  src/lzio.c
        src/lcorolib.c src/ldump.c     src/llex.c
        src/lopcodes.c  src/lstrlib.c

)
target_include_directories(lua PUBLIC include)

add_executable(lua-console src/lua.c)
target_link_libraries(lua-console PRIVATE lua)

add_executable(lua-compiler src/luac.c)
target_link_libraries(lua-compiler PRIVATE lua)