cmake_minimum_required(VERSION 3.13)
project(plumber)

# 設定 IrrKlang 版本和下載連結
set(IRRKLANG_VERSION 1.6.0)
include(FetchContent)
FetchContent_Declare(
    irrKlang
    URL https://www.ambiera.at/downloads/irrKlang-64bit-${IRRKLANG_VERSION}.zip
    DOWNLOAD_EXTRACT_TIMESTAMP TRUE
)
FetchContent_MakeAvailable(irrKlang)

# 設定 IrrKlang 的路徑為 irrKlang_SOURCE_DIR
set(IRRKLANG_ROOT "build/_deps/irrklang-src")

# 創建可執行文件
add_executable(plumber Algorithm.h Direction.h Game.h Maze.h Pipe.h Source.cpp)

# 連結 IrrKlang 庫
target_include_directories(plumber PRIVATE ${IRRKLANG_ROOT}/include)
target_link_directories(plumber PRIVATE ${IRRKLANG_ROOT}/lib/Winx64-visualStudio)
target_link_libraries(plumber PRIVATE irrKlang)

# 複製音效文件夾道建構目錄
file(COPY ${CMAKE_SOURCE_DIR}/soundEffect DESTINATION ${CMAKE_BINARY_DIR}/soundEffect)

add_custom_command(TARGET plumber POST_BUILD 
    COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_SOURCE_DIR}/${IRRKLANG_ROOT}/bin/winx64-visualStudio/irrKlang.dll ${CMAKE_BINARY_DIR}/Debug/irrKlang.dll
)

# 確保音效資源也能被複製過去
foreach(CONFIGURATION_TYPE IN LISTS CMAKE_CONFIGURATION_TYPES)
    add_custom_command(
        TARGET plumber POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_directory
                ${CMAKE_SOURCE_DIR}/soundEffect
                ${CMAKE_BINARY_DIR}/${CONFIGURATION_TYPE}/soundEffect
        COMMAND ${CMAKE_COMMAND} -E copy
                ${CMAKE_SOURCE_DIR}/board.txt
                ${CMAKE_BINARY_DIR}/${CONFIGURATION_TYPE}/board.txt
    )
endforeach()