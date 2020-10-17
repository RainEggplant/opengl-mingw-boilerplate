# OpenGL MinGW Boilerplate

This repository provides a boilerplate for OpenGL project with [GLFW](https://www.glfw.org/), [GLAD](https://glad.dav1d.de/), [GLM](https://glm.g-truc.net/), [SOIL](https://www.lonesock.net/soil.html) and [FreeType](https://www.freetype.org/) on Windows with MinGW. It also provides a
`.vscode/c_cpp_properties.json` file for VSCode.

## Structure

This is the structure of the boilerplate.

```
.
├─.vscode
├─lib
│  ├─freetype
│  │  ├─include
│  │  └─lib
│  ├─glad
│  │  ├─include
│  │  └─src
│  ├─glfw
│  │  ├─include
│  │  └─lib
│  ├─glm
│  │  └─glm
│  └─soil
│      ├─include
│      └─lib
└─src
```

### Libraries

We will need `GLAD`, `GLFW`, `GLM`, `SOIL` and `FreeType` for our project. We have already placed `GLFW` (version 3.3.2), `GLAD` (verison 4.3) and `GLM` (version 0.9.9.8) files under the `lib` folder. We have also re-compiled SOIL (version July 7, 2008) and compiled FreeType (version 2.10.2) using MinGW to fit our environment, and placed their files likewise.

If you want libraries of certain versions, you can still keep the structure of this project, and go [here](http://www.glfw.org/download.html) to download the pre-compiled binaries of GLFW, go [here](https://glad.dav1d.de/) to generate GLAD source of your preferred version, go [here](https://github.com/g-truc/glm/releases) to download GLM, and go [here](http://www.lonesock.net/soil.html) to download GLM.

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
