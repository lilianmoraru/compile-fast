# Planned explanations(notes)
- Explanation how to install(Ubuntu 16.04): CMake, gcc/g++, make(build-essential), ninja, ccache(compile), 
vmtouch(compile), libeatmydata
- CMake module examples for: ccache(`CMAKE_<LANG>_COMPILER_LAUNCHER`, CMake => 3.4) and the GNU gold linker(`execute_process()`)
- Full compilation without stopping at preprocessing(`-E`)
- `zsh-autoenv` for environment related setup
- `mkdir -p /dev/shm/.ccache; export CCACHE_DIR=/dev/shm/.ccache`?(would help only the first time...)
- `/code` - partition
- `store="$(mount | grep "on /code " | cut -d '(' -f 2 | cut -d ')' -f 1)"; mount 
-o remount[whatever was there(ex: realtime) replaced by noatime]`(restored through `zsh-autoenv`)
- `test -z "${LD_PRELOAD}" && export LD_PRELOAD=...libeatmydata`(store-restore)
- `sysctl -n vm.dirty_...` into `/var/cache/...` file(restored with the help of `zsh-autoenv`)
- `sysctl -w vm.dirt_...`, `sysctl -p`
- `swapoff -a`
- `vmtouch` ... `cc -print-search-dirs` include paths and binaries(ex: compiler) + project