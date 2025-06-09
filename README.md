# CMake Template for C++ Projects

This is a template project that serves as a starting point for C++ projects using CMake as the build system.

## Prerequisites

- CMake (version 3.10 or higher)
- A C++ compiler (GCC, Clang, or MSVC)
- Make or Ninja (optional, for building)

## Project Structure

```
.
├── CMakeLists.txt          # Main CMake configuration file
├── src/                    # Source files directory
│   └── main.cpp           # Main source file
├── include/               # Header files directory
└── build/                 # Build directory (created during build)
```

## Building the Project

### Using CMake GUI

1. Open CMake GUI
2. Set the source directory to the project root
3. Set the build directory (e.g., `build/`)
4. Click "Configure" and select your compiler
5. Click "Generate"
6. Open the generated project in your IDE or build it using your build system

### Using Command Line

#### Windows (PowerShell)
```powershell
# Create and enter build directory
mkdir build
cd build

# Configure the project
cmake ..

# Build the project
cmake --build .
```

#### Linux/macOS
```bash
# Create and enter build directory
mkdir build && cd build

# Configure the project
cmake ..

# Build the project
make
```

## Running the Project

After building, you can run the executable:

### Windows
```powershell
.\build\Debug\cpp_cmake_template.exe
```

### Linux/macOS
```bash
./build/cpp_cmake_template
```

## Development

### Adding New Source Files

1. Add your source files to the `src/` directory
2. Add your header files to the `include/` directory
3. Update `CMakeLists.txt` if you add new source files

### Project Configuration

The main configuration is done in `CMakeLists.txt`. You can modify build options, add dependencies, and configure project settings there.

## License

[Add your license information here]

## Contributing

[Add contribution guidelines here]

## Contact

[Add your contact information here]