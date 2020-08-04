add_executable(ForTuple main.cpp tuple_example.f90)
target_link_libraries(ForTuple Cabana::cabanacore)
add_test(NAME Fortran_Tutorial_02_Tuple COMMAND ForTuple)
