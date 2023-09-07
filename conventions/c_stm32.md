# Coding Conventions: C for STM32

1. Line length = `100`
    - Arbitrary, because I said so
        - Also, it is a good balance for readability
2. STM32CubeMX `GENERATE CODE` formatting using the `Toolchain / IDE` = `STM32CubeIDE` setting takes
   supremacy at all times unless specifically stated
    - Due to the time-consuming nature of initialization and HAL setup, we always want to ensure
      CubeMX compatability
    - This also includes the location of "user" code as specified by the generated code
3. [Clang-Tidy](https://clang.llvm.org/extra/clang-tidy/)
    - This is the default for CLion
4. User created variable names: `snake_case`
5. Modules: `snake_case`
6. Directories: single word all lowercase
