add_executable(ForHelloWorld main.cpp hello_world.f90)
target_link_libraries(ForHelloWorld Cabana::cabanacore)
add_test(NAME Fortran_Tutorial_01_HelloWorld COMMAND ForHelloWorld)
