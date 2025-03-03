target_add_lib(meta core-app core-user core-service fdb meta-fbs mgmtd-client storage-client memory-common analytics)
target_add_bin(meta_main "meta.cpp" meta jemalloc "/usr/lib/llvm-14/lib/clang/14.0.0/lib/linux/libclang_rt.builtins-aarch64.a")
