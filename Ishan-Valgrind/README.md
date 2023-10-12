# Valgrind Exercise

## Standard install via command-line
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
```



## What happens when the executable is linked statically?  Does Valgrind still detect those same bugs? Why and why not?

-- In a statically linked executable, all the dependencies and libraries are bundled within the executable itself, instead of being linked dynamically. Despite being statically linked, Valgrind is still capable of finding some bugs in statically linked executables, particularly memory leaks, invalid memory accesses, and data races. A program can be inspected using Valgrind regardless of whether it is dynamically or statically linked because it operates at the process level, monitoring memory and system calls while the program is running.

