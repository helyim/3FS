if(CMAKE_SYSTEM_PROCESSOR MATCHES "aarch64|arm64")
    set(LIB_ARCH "aarch64")
else()
    set(LIB_ARCH "x86_64")
endif()

link_directories(/usr/local/lib/${LIB_ARCH}-linux-gnu)

target_add_lib(hf3fs_fuse common core-app meta-client storage-client fuse3 client-lib-common)
target_add_bin(hf3fs_fuse_main hf3fs_fuse.cpp hf3fs_fuse)

if (ENABLE_FUSE_APPLICATION)
target_compile_definitions(hf3fs_fuse PUBLIC -DENABLE_FUSE_APPLICATION)
endif()
