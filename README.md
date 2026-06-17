# libmath2
libmath2 - динамическая библиотека с математическими функциями: сложение, вычитание, умножение, деление и возведение в степень.

Сборка без CMake:

Генерируем объектный файл. В корневой директории репозитория с библиотекой выполним команду:
g++ -c -fPIC src/libmath.cpp -o libmath.o -I./include

Собираем объектные файлы в библиотеку с помощью следующей команды:
g++ -shared libmath.o -o libmath.so

Скопируем нашу библиотеку и заголовочный файл в системные директории:
sudo cp libmath.so /usr/local/lib/
sudo cp ./include/libmath.h /usr/local/include/

Обновим данные линковщика о доступных динамических библиотеках:
sudo ldconfig

Для сборки проекта:
g++ "исходники" -lmath -o "имя исполняемого модуля"


Сборка с CMake:

Команда на подготовку конфигурации для сборки нашего проекта: cmake -B build

Сборка проекта: cmake --build build (полный аналог командам: g++ -c -fPIC src/libmath.cpp -o libmath.o -I./include g++ -shared libmath.o -o libmath.so)

Установка проекта: sudo cmake --build build --target install (аналог командам: sudo cp libmath.so /usr/local/lib/ sudo cp ./include/libmath.h /usr/local/include/)
