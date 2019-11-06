# Ray Tracing in One Weekend (C++)

This is my C++ implementation of the ray tracer described in the book [Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html) by Peter Shirley.

The project follows the structure outlined in the book [Modern CMake](https://cliutils.gitlab.io/modern-cmake/) by Henry Schreiner.

## Setup

Make sure you have a recent version of CMake installed, and do the following:

```
git clone https://github.com/unindented/ray-tracing-in-one-weekend-cpp.git
cd ray-tracing-in-one-weekend-cpp
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ..
cd ..
```

## Build

```
cd build
make
```

## Test

```
cd build
make test
```

## Run

```
build/apps/rtiowapp
```

## Meta

- Code: `git clone https://github.com/unindented/ray-tracing-in-one-weekend-cpp.git`
- Home: <https://unindented.org/>

## Contributors

Daniel Perez Alvarez ([unindented@gmail.com](mailto:unindented@gmail.com))

## License

Copyright (c) 2020 Daniel Perez Alvarez ([unindented.org](https://unindented.org/)). This is free software, and may be redistributed under the terms specified in the `LICENSE.txt` file.
