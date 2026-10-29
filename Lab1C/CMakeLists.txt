add_executable(Lab1C opz.cpp)
target_include_directories(Lab1C PUBLIC ../LibraryCPP)
target_link_libraries(Lab1C LibraryCPP)

# T1: A+B*C+D
add_test(NAME Test_File_1 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test1.txt)
set_tests_properties(Test_File_1 PROPERTIES PASS_REGULAR_EXPRESSION "ABC\\*\\+D\\+")

# Т2: A*B+C/D
add_test(NAME Test_File_2 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test2.txt)
set_tests_properties(Test_File_2 PROPERTIES PASS_REGULAR_EXPRESSION "AB\\*CD/+")

# Т3: A-B-C
add_test(NAME Test_File_3 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test3.txt)
set_tests_properties(Test_File_3 PROPERTIES PASS_REGULAR_EXPRESSION "AB-C-")

# Т4: A*(B+C)
add_test(NAME Test_File_4 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test4.txt)
set_tests_properties(Test_File_4 PROPERTIES PASS_REGULAR_EXPRESSION "ABC\\+\\*")

# Т5: (A+B)/(C-D)
add_test(NAME Test_File_5 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test5.txt)
set_tests_properties(Test_File_5 PROPERTIES PASS_REGULAR_EXPRESSION "AB\\+CD-\\/")

# Т6(Неверный ввод): A+(B*C
add_test(NAME Test_File_Error_1 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test6.txt)
set_tests_properties(Test_File_Error_1 PROPERTIES PASS_REGULAR_EXPRESSION "ERROR")

# Т7(Неверный ввод): A+2*B
add_test(NAME Test_File_Error_2 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test7.txt)
set_tests_properties(Test_File_Error_2 PROPERTIES PASS_REGULAR_EXPRESSION "ERROR")

# Т8(Неверный ввод): A+B)
add_test(NAME Test_File_Error_3 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test8.txt)
set_tests_properties(Test_File_Error_3 PROPERTIES PASS_REGULAR_EXPRESSION "ERROR")

# Т9(Неверный ввод): ()
add_test(NAME Test_File_Error_4 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test9.txt)
set_tests_properties(Test_File_Error_4 PROPERTIES PASS_REGULAR_EXPRESSION "ERROR")

# Т10(Неверный ввод): (A+B))
add_test(NAME Test_File_Error_5 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test10.txt)
set_tests_properties(Test_File_Error_5 PROPERTIES PASS_REGULAR_EXPRESSION "ERROR")

# Т11(Неверный ввод): ?
add_test(NAME Test_File_Error_6 COMMAND Lab1C ${CMAKE_CURRENT_SOURCE_DIR}/test11.txt)
set_tests_properties(Test_File_Error_6 PROPERTIES PASS_REGULAR_EXPRESSION "ERROR")