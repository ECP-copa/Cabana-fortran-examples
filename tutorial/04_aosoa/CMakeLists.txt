  add_executable(ForArrayOfStructsOfArrays main.cpp aosoa_example.F90)
  target_link_libraries(ForArrayOfStructsOfArrays Cabana::cabanacore)
  add_test(NAME Fortran_tutorial_04 COMMAND ForArrayOfStructsOfArrays)
