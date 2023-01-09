CMAKE_MINIMUM_REQUIRED(VERSION 3.7)
PROJECT(StoryVepsianChronicle NONE)
FIND_PACKAGE(LATEX)
SET(PDFLATEX_COMPILER xelatex)
SET(LATEX_DEFAULT_BUILD pdf)
INCLUDE(UseLATEX.cmake)
SET(parts
    coordsvalues.tex
    titlepage.tex
    thankyou.tex
    typograph.tex
    annotation.tex
    #
    prolog.tex
    epilog.tex
    #
    лидь2015/часть1.tex
    лидь2015/аннотация.tex
    лидь2015/введение.tex
    лидь2015/несколько_слов_о_сплавах.tex
    лидь2015/байдарка.tex 
    лидь2015/маршрут_и_сборы.tex 
    лидь2015/отъезд.tex
    лидь2015/заброска.tex
    лидь2015/катастрофа.tex
    лидь2015/фонтан.tex
    лидь2015/первая_дневка.tex
    лидь2015/дозаправка_в_чагоде.tex
    лидь2015/долгий_переход.tex
    лидь2015/кабаны_и_удача.tex
    лидь2015/вторая_дневка.tex
    лидь2015/досрочный_антистапель.tex
    лидь2015/возвращение.tex
    лидь2015/заключение.tex
    #
    горюн2016/часть2.tex
    горюн2016/аннотация.tex
    горюн2016/введение.tex
    горюн2016/снова_на_реку.tex 
    горюн2016/команда.tex 
    горюн2016/приготовления.tex 
    горюн2016/заброска_микроавтобусом.tex 
    горюн2016/стапель.tex 
    горюн2016/проходим_устье_лиди.tex 
    горюн2016/в_чагоде_год_спустя.tex 
    горюн2016/в_ожидании_дневки.tex 
    горюн2016/пятый_дневной_переход.tex
    горюн2016/поиски_дневки.tex
    горюн2016/урочище_лукобор.tex
    горюн2016/целый_день_дождь.tex
    горюн2016/выброска.tex
    горюн2016/заключение.tex
    #
    лидь2017/часть3.tex
    лидь2017/аннотация.tex
    лидь2017/введение.tex
    лидь2017/а_не_пошло_бы_все.tex
    лидь2017/авантюра.tex
    лидь2017/автозаброска.tex
    лидь2017/радогощь.tex
    лидь2017/гэс.tex
    лидь2017/село_лидь.tex
    лидь2017/дозаправка.tex
    лидь2017/забелье.tex
    лидь2017/тургощь.tex
    лидь2017/третий_раз.tex
    лидь2017/антистапель.tex
    лидь2017/автовыброска.tex
    лидь2017/заключение.tex
    #
    песь2018/часть4.tex
    песь2018/аннотация.tex
    песь2018/раскрась_это_черным.tex
    #
    чагодоща2019/часть5.tex
    чагодоща2019/аннотация.tex
    чагодоща2019/cold_as_ice.tex
    #
    воспоминания_о_школе/профессура.tex
    воспоминания_о_школе/джомолунгма.tex
    воспоминания_о_школе/митрич_и_циркуль.tex
    #
    lastpage.tex
    coordinates.tex
)
ADD_LATEX_DOCUMENT(
	main.tex
	BIBFILES bibliography.bib
	IMAGE_DIRS pictures
    INPUTS ${parts}    
)
# Команда копирует результирующий файл main.pdf в директорию /output с переименованием
add_custom_command(
        TARGET main
        COMMAND ${CMAKE_COMMAND} -E copy
                ${CMAKE_CURRENT_SOURCE_DIR}/build/main.pdf
                ${CMAKE_CURRENT_SOURCE_DIR}/output/StoryVepsianChronicle_Sobolev.pdf)
