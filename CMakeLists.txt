cmake_minimum_required(VERSION 3.20)

project(AutoTrack LANGUAGES CXX)

# Находим необходимые модули OpenCV.
find_package(OpenCV REQUIRED COMPONENTS core videoio highgui)

# Создаём исполняемый файл из нашего исходника.
add_executable(auto_track src/main.cpp)

# Используем стандарт C++20.
target_compile_features(auto_track PRIVATE cxx_std_20)
set_target_properties(auto_track PROPERTIES CXX_EXTENSIONS OFF)

# Указываем, где искать заголовки OpenCV.
target_include_directories(auto_track PRIVATE ${OpenCV_INCLUDE_DIRS})

# Подключаем библиотеки OpenCV.
target_link_libraries(auto_track PRIVATE ${OpenCV_LIBS})