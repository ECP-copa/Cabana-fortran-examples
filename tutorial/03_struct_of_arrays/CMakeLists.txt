add_executable(ForStructOfArrays main.cpp soa_example.F90)
target_link_libraries(ForStructOfArrays Cabana::cabanacore)
add_test(NAME Fortran_Tutorial_03_SoA COMMAND ForStructOfArrays)
