# OpenGL MinGW Boilerplate

This repository provides a boilerplate for OpenGL project with GLFW, GLAD and GLM on Windows with MinGW. It also provides a
`.vscode/c_cpp_properties.json` file for VSCode.

## Structure

This is the structure of the boilerplate.

```
.
├─.vscode
├─lib
│  ├─glad
│  │  ├─include
│  │  │  ├─glad
│  │  │  └─KHR
│  │  └─src
│  ├─glfw
│  │  ├─include
│  │  │  └─GLFW
│  │  └─lib
│  └─glm
│      └─glm
│          ├─detail
│          ├─ext
│          ├─gtc
│          ├─gtx
│          └─simd
└─src
```

### Libraries

We will need `GLAD`, `GLFW` and `GLM` for our project. We have already placed `GLFW` (version 3.3.2), `GLAD` (verison 4.6) and `GLM` (version 0.9.9.8) files under the `lib` folder.

You can go [here](http://www.glfw.org/download.html) to download the pre-compiled binaries of GLFW, go [here](https://glad.dav1d.de/) to generate GLAD source of your preferred version, and go [here](https://github.com/g-truc/glm/releases) to download GLM.

### Sources

You will need to place your own source files under the `src` folder. We have placed a simple file which will create a window.

## Developing

We suggest using VSCode with [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) and [CMake Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools) extension so that you can build or debug simply by just clicking buttons in the status bar after proper configuration.

Of course you can also run:

```bash
# create build directory and move to it
mkdir build
cd build

# configure project
cmake -G"MSYS Makefiles" ../  # or "MinGW Makefiles" depending on your type of `make`

# build executables
make  # or `cmake --build ./`
```

The generated executable will be placed at `build/bin` .
