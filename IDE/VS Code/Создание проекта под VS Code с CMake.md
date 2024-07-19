За основу можно взять проект LineCard_PC

[Образцовый проект на CMake по VS Code](D:\Projects\LineCard\LineCard_PC)

**Внимание!!!**
1. Должен быть установлен (на самой системе Windows/Linux) [CMake](https://github.com/Kitware/CMake/releases/download/v3.30.1/cmake-3.30.1-windows-x86_64.msi)
3. Можно (но не обязательно) установить [ninja](https://github.com/ninja-build/ninja/releases) (под Windows 11 он не ставится)
4. Если что-то не идёт можно удалить каталог **build**
5. Может потребоваться установить плагин CMake
6. Может потребоваться задать компилятор. Для этого:
	1. Зайти в плагин CMake
	2. Пункт **Настройка** -> Компилятор -> выбрать GCC или Visual Studio Build Tool (VCC)
![[Pasted image 20240731131023.png]]

Текст самого CMake.txt может иметь такой вид:
Строка **set (CMAKE_CXX_STANDARD 11)** означает, что нужно использовать C++ 2011 стандарт.

Получить список всех файлов (с путями) в текущем каталоге можно с помощью команды Linux **find** без всяких аргументов. Этот список с небольшой обработкой можно использовать в файле CMakeList.txt

```
cmake_minimum_required(VERSION 3.16.0)
set (CMAKE_CXX_STANDARD 11)
#enable_testing()
project(vscode-template)

add_executable(main
    main.cpp
    config.h
    
    Modules/CLI/CLI_process.hpp
    Modules/CLI/CLI.hpp
    Modules/CLI/CLI.cpp
    Modules/CLI/CLI_process.cpp

	Modules/CFP2/CFP2.cpp
    Modules/CFP2/CFP2.hpp

    Modules/Drivers/I2CInterface.hpp
    Modules/Drivers/I2CInterface.cpp

    Modules/QSFP/QSFP.cpp
    Modules/QSFP/Channel.hpp
    Modules/QSFP/MemoryMap/MemoryMapDefines.hpp
    Modules/QSFP/MemoryMap/Page1.hpp
    Modules/QSFP/MemoryMap/Page2.hpp
    Modules/QSFP/MemoryMap/MemoryMap.hpp
    Modules/QSFP/MemoryMap/Page3.hpp
    Modules/QSFP/MemoryMap/Page_Main.hpp
    Modules/QSFP/MemoryMap/Page0.hpp

	Modules/QSFP/ValueTables.hpp
    Modules/QSFP/FieldAccessor.hpp
    Modules/QSFP/FieldAccessor.cpp
    Modules/QSFP/Channel.cpp
    Modules/QSFP/ValueTables.cpp
    Modules/QSFP/QSFP.hpp
    
    Modules/Utils/Platforms.hpp
    Modules/Utils/Macroses.hpp
    Modules/Utils/Utils.cpp
    Modules/Utils/Utils.hpp

	Modules/AbstractDevice/FieldTypes/Field.hpp
    Modules/AbstractDevice/FieldTypes/Field.cpp
    Modules/AbstractDevice/FieldTypes/BitField.hpp
    Modules/AbstractDevice/FieldTypes/HiLowBytes.hpp
    Modules/AbstractDevice/FieldTypes/BitField.cpp
    Modules/AbstractDevice/FieldTypes/StringField.cpp
    Modules/AbstractDevice/FieldTypes/StringField.hpp
    Modules/AbstractDevice/HardwareInterface.hpp
    Modules/AbstractDevice/Mapper.cpp
    Modules/AbstractDevice/Mapper.hpp
    Modules/AbstractDevice/HardwareInterface.cpp
    Modules/AbstractDevice/ValueTableInterface.cpp
    Modules/AbstractDevice/FieldStorage.hpp
    Modules/AbstractDevice/FieldStorage.cpp
    Modules/AbstractDevice/AbstractDevice.cpp
    Modules/AbstractDevice/AbstractDevice.hpp
    Modules/AbstractDevice/FieldAccessInterface.hpp
    Modules/AbstractDevice/ValueTableInterface.hpp
    Modules/AbstractDevice/FieldAccessInterface.cpp
)

#add_subdirectory(test)
```