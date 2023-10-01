This Application requires a .vscode/tasks.json file, like the following example, which works for MacOS:

{
    "version": "2.0.0",
    "tasks": [
     {
      "type": "cppbuild",
      "label": "C/C++: clang++ build active file",
      "command": "/usr/bin/clang++",
      "args": [
       "-std=c++17",
       "-fdiagnostics-color=always",
       "-Wall",
       "-g",
       "-I${workspaceFolder}/include",
       "${workspaceFolder}/lib/libglfw.3.3.dylib",
       "${workspaceFolder}/src/*.cpp",
       "${workspaceFolder}/src/glad.c",
       "-o",
       "${workspaceFolder}/app",
       "-framework",
       "OpenGL",
       "-framework",
       "Cocoa",
       "-framework",
       "IOKit",
       "-framework",
       "CoreVideo",
       "-framework",
       "CoreFoundation",
       "-Wno-deprecated"
      ],
      "options": {
       "cwd": "${fileDirname}"
      },
      "problemMatcher": ["$gcc"],
      "group": {
       "kind": "build",
       "isDefault": true
      },
      "detail": "compiler: /usr/bin/clang++"
     }
    ]
}

A slightly different `tasks.json` is required for other operating systems.
To build on VSCode simply run `Ctrl + Shift + B``
and then start the compiled app by running `./app` on the terminal

