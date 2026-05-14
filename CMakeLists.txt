cmake_minimum_required(VERSION 3.13)

# Название проекта из задания
project(Forest)

# Настройка стандарта C++
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Поиск SFML (нам нужны графика, окна и системный модуль)
find_package(SFML COMPONENTS graphics window system REQUIRED)

# Команда add_executable: сюда записываем ВСЕ .cpp файлы, которые ты видишь в ls.
# Заголовочные файлы (.h) сюда писать не обязательно, CMake найдет их сам,
# если они лежат в этой же папке.

add_executable(Forest
    main.cpp
    Animal.cpp
    Cat.cpp
    Creature.cpp
    Flower.cpp
    Herbivore.cpp
    Mushroom.cpp
    Plant.cpp
    Carnivore.cpp
    Cow.cpp
    Fish.cpp
    Forest.cpp
    Lion.cpp
    Penguin.cpp
    Sundew.cpp
    Sparrow.cpp
)

# Линкуем SFML к нашему исполняемому файлу.
# Используем те имена, которые требует линкер (из подсказки в лабе)
target_link_libraries(Forest PRIVATE 
    sfml-graphics 
    sfml-window 
    sfml-system
)

# Указываем, что хедеры лежат прямо здесь (в текущей папке)
target_include_directories(Forest PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
