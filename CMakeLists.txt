CMAKE_MINIMUM_REQUIRED(VERSION 3.7)
PROJECT(StoryLidChagodaChagodoscha2015 NONE)
FIND_PACKAGE(LATEX)
INCLUDE(UseLATEX.cmake)
SET(parts
    introduce.tex
    annotation.tex
    chapter1.tex
    chapter2.tex
    chapter3.tex
    chapter4.tex
    chapter5.tex
    chapter6.tex
    chapter7.tex
    chapter8.tex
    chapter9.tex
    chapter10.tex
    chapter11.tex
    chapter12.tex
    chapter13.tex
    chapter14.tex
    chapter15.tex
)
ADD_LATEX_DOCUMENT(main.tex
#    INPUTS ${parts}    
)
#add_custom_command(
#        TARGET main
#        COMMAND ${CMAKE_COMMAND} -E copy
#                ${CMAKE_CURRENT_SOURCE_DIR}/build/main.pdf
#                ${CMAKE_CURRENT_SOURCE_DIR}/output/Повесть_о_сплаве_на_байдарке_Лидь_2015_Соболев_А_А.pdf)
