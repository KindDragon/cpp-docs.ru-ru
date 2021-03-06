---
title: "Откройте папки проектов в Visual C++ | Документы Microsoft"
ms.custom: 
ms.date: 08/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 721dd39cf8cda6277eb129f259b7ede2d9f0da28
ms.sourcegitcommit: ef2a263e193410782c6dfe47d00764263439537c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="open-folder-projects-in-visual-c"></a>Откройте папки проектов в Visual C++
2017 г. Visual Studio предоставляет функцию «Открыть папку», которая позволяет открыть папку исходных файлов и немедленно начать кодирование с поддержкой технологии IntelliSense, просмотр, оптимизации кода, отладка и так далее. Загружаются файлы не .sln или VCXPROJ-файл; При необходимости можно указать пользовательские задачи так, как построить и запустить параметров через файлы .json простой. На платформе открыть папку, Visual C++ теперь поддерживает не только свободные коллекции файлов, но также практически любой построения системы, включая CMake, ниндзя, QMake (для проектов Qt), gyp, SCons, Gradle, бак, создание и более. 

Чтобы использовать открыть папку, в главном меню выберите *файл | Откройте | Папка* или нажмите клавишу *Ctrl + Shift + Alt + O*. Обозреватель решений сразу отображает все файлы в папке. Можно щелкнуть любой файл, чтобы приступить к редактированию. В фоновом режиме Visual Studio запускает индексирование файлов, чтобы включить технологию IntelliSense, навигации и функций рефакторинга. Как изменять, создавать и удалять файлы Visual Studio автоматически отслеживает изменения и постоянно обновляет его индекс IntelliSense. 
  
## <a name="cmake-projects"></a>Проекты CMake
CMake интегрирован в Интегрированной среде разработки Visual Studio как CMake средства для Visual C++, компонент C++ рабочего стола рабочей нагрузки. Дополнительные сведения см. в разделе [Инструменты CMake для Visual C++](cmake-tools-for-visual-cpp.md).
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>QMake проекты, предназначенные для framework Qt
Можно использовать средства CMake для Visual C++ Qt целевой объект для построения проектов Qt, или можно использовать расширение Qt Visual Studio. Примечание: Начиная с августа 2017 г [расширение Visual Studio Qt поддержка Visual Studio 2017 г](https://download.qt.io/development_releases/vsaddin/) доступен в виде бета-версии.

## <a name="gyp-cons-scons-buck-etc"></a>gyp недостатков, SCons, бак, и т.д.
Можно использовать любую другую систему сборки в Visual C++ и по-прежнему пользоваться преимуществами интегрированной среды разработки Visual C++ и отладчик. При открытии в корневую папку проекта Visual C++ использует эвристику для индексации исходные файлы для поддержки технологии IntelliSense и обзора. Существует возможность создания подсказок о структуре кода путем редактирования файла CppProperties.json. Аналогичным образом можно настроить, изменив файл launch.vs.json построения программы. 

## <a name="configuring-open-folder-projects"></a>Настройка проектов открыть папку
Открыть папку проекта можно настроить через три файла JSON:
|||
|-|-|
|CppProperties.json|Укажите сведения о настраиваемой конфигурации для просмотра. Этот файл создается в том случае, если необходимо, в корневой папке проекта.|
|launch.vs.json|Укажите аргументы командной строки. Доступ к которым осуществляется через **обозревателе решений** пункт контекстного меню **отладки и параметры запуска**.|
|Tasks.VS.JSON|Укажите настраиваемого построения команд и параметров компилятора. Доступ к которым осуществляется через **обозревателе решений** пункт контекстного меню **задачи настройки**.|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>Настройка IntelliSense с CppProperties.json
IntelliSense и просмотра поведение частично зависит от активной конфигурации построения, который определяет #include пути, параметры компилятора и другие параметры. По умолчанию Visual Studio предоставляет отладочной и окончательной конфигурации. Для некоторых проектов необходимо создать пользовательскую конфигурацию в порядке для IntelliSense и обзора компонентов, чтобы полностью вникнуть в коде. Чтобы определить новую конфигурацию, создайте файл с именем CppProperties.json в корневой папке. Пример:

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
Конфигурация может иметь любой из следующих свойств:

|||  
|-|-| 
|`name`|Имя конфигурации, который отображается в раскрывающемся списке конфигурации C++|
|`includePath`|Список папок, которые должны быть указаны в пути включения (большинство компиляторов сопоставляется с/i)|
|`defines`|список макросов, которые должны быть определены (большинство компиляторов сопоставляется с /D)|
|`compilerSwitches`|один или несколько дополнительных параметров, которые могут повлиять на поведение IntelliSense|
|`forcedInclude`|Заголовок автоматически включается в каждом блоке компиляции (сопоставляет /FI для параметры MSVC или - включают для clang)|
|`undefines`|в списке макросов быть неопределенным (сопоставляется /U для параметры MSVC)|
|`intelliSenseMode`|Подсистема IntelliSense для использования. Параметры MSVC, gcc и Clang, можно указать определенные варианты архитектуры:
- Параметры Msvc x86 (по умолчанию)
- msvc-x64
- Параметры Msvc arm
- windows-clang-x86
- windows-clang-x64
- Windows-clang-arm
- Linux-x64
- Linux-x86
- Linux arm
- gccarm

#### <a name="environment-variables"></a>Переменные среды
CppProperties.json поддерживает системы расширение переменных среды для включения пути и значения других свойств. Синтаксис `${env.FOODIR}` разверните переменную среды `%FOODIR%`. Также поддерживаются следующие системные переменные:

|Имя переменной|Описание:|  
|-----------|-----------------|
|vsdev|Среда Visual Studio по умолчанию|
|msvc_x86|Компиляция с помощью x86 x86 средства|
|msvc_arm|Компилировать для архитектуры ARM с помощью x86 средств|
|msvc_arm64|Компилировать для ARM64 x86 с помощью средства|
|msvc_x86_x64|Компилировать для AMD64 x86 с помощью средства|
|msvc_x64_x64|Компилировать для AMD64, с помощью средств 64-разрядная версия|
|msvc_arm_x64|Компиляция с помощью 64-разрядные средства ARM|
|msvc_arm64_x64|Компилировать для ARM64 с помощью средств 64-разрядная версия|

При установке Linux рабочей нагрузки для удаленного выбора Linux и WSL доступны следующих средах:

|Имя переменной|Описание:|  
|-----------|-----------------|
|linux_x86|Целевой x86 Linux удаленно|
|linux_x64|Целевой x64 Linux удаленно|
|linux_arm|Удаленно целевой ARM Linux|

Можно определить пользовательские переменные в CppProperties.json либо глобально или для каждой конфигурации. В следующем примере показано, как по умолчанию и пользовательские переменные могут быть объявлены и использованы. Глобальный **среды** свойство объявляется переменная с именем **INCLUDE** , может использоваться любой конфигурации:

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
    }
  ],
 
  "configurations": [
    {
      "inheritEnvironments": [
        // Inherit the MSVC 32-bit environment and toolchain.
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x86"
    },
    {
      "inheritEnvironments": [
        // Inherit the MSVC 64-bit environment and toolchain.
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```
Можно также определить **среды** свойство в конфигурации, так что он применяется только к этой конфигурации и переопределяет все глобальные переменные, с тем же именем. В следующем примере x64 конфигурации определяет локальный **INCLUDE** переменную, которая переопределяет глобальное значение:

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
    }
  ],
 
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined in the global environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x86"
    },
    {
      "environments": [
        {
          // Append 64-bit specific include path to env.INCLUDE.
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\\src\\includes64"
        }
      ],
 
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined in the local environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```

Все пользовательские и переменные среды по умолчанию также доступны в tasks.vs.json и launch.vs.json.

#### <a name="macros"></a>Макросы
Доступны следующие встроенные макросы внутри CppProperties.json:
|||
|-|-|
|`${workspaceRoot}`| Полный путь к папке рабочей области|
|`${projectRoot}`| Полный путь к папке, куда помещается CppProperties.json|
|`${vsInstallDir}`| Полный путь к папке, установленным запущенный экземпляр VS 2017 г.|

Например если проект имеет папку include и также включает windows.h и другие общие заголовки из пакета SDK Windows, можно обновить ваш CppProperties.json включает файл конфигурации со следующими:

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\ucrt",
        "${env.NETFXSDKDir}\\include\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\shared",
        "${env.VCToolsInstallDir}include"
      ]
    }
  ]
}
```

**Примечание:** `%WindowsSdkDir%` и `%VCToolsInstallDir%` не установлены, как глобальные переменные окружения поэтому убедитесь, что запущен devenv.exe из «Командная строка разработчика для VS 2017 г.», определяющая эти переменные.

Устранение неполадок IntelliSense ошибки, вызванные отсутствует включают пути, откройте **список ошибок** и фильтровать выходные данные в «IntelliSense», и код ошибки E1696 «не удается открыть исходный файл...». 

Можно создать любое количество конфигураций в CppProperties.json. Они будут отображены в раскрывающемся списке конфигурации:

```json
{
  "configurations": [
    {
      "name": "Windows",
      ...
    },
    {
      "name": "with EXTERNAL_CODECS",
      ...
    }
  ]
}
```
### <a name="define-tasks-with-tasksvsjson"></a>Определение задач с tasks.vs.json
Можно автоматизировать скрипты сборки или других внешних операций с файлами, имеющиеся в вашей текущей рабочей области, запустив их как задачи непосредственно в Интегрированной среде разработки. Можно настроить новую задачу, щелкните правой кнопкой мыши на файл или папку и выбрав **задачи настройки**. 

![Открыть папку Настройка задач](media/open-folder-config-tasks.png)

Создает (или открывает) `tasks.vs.json` файл в папке удаляйте, который Visual Studio создает в корневой папке проекта. Можно определить любой произвольный задачи в этом файле и затем вызвать его из **обозревателе решений** контекстного меню. В следующем примере tasks.vs.json файл, который определяет одну задачу. `taskName`Определяет имя, которое отображается в контекстном меню. `appliesTo`Определяет, какие файлы, можно выполнить команду на. `command` Свойство ссылается на переменную среды COMSPEC определяет путь для консоли (cmd.exe в Windows). Также ссылаться на переменные среды, которые объявлены в CppProperties.json или CMakeSettings.json. `args` Свойство определяет командную строку для вызова. `${file}` Макрос извлекает выбранный файл в **обозревателе решений**. Следующий пример отображает имя файла текущего выбранного CPP-файл.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```
После сохранения tasks.vs.json, щелкните правой кнопкой мыши любой CPP-файл в папке, выберите **Echo filename** из контекстного меню и имя файла отображаются в окне вывода см.



#### <a name="appliesto"></a>appliesTo
Задачи для любого файла или папки можно создать, указав его имя в `appliesTo` поля, например `"appliesTo" : "hello.cpp"`. Следующие маски файлов можно использовать в качестве значения:
|||
|-|-|
|`"*"`| она доступна для всех файлов и папок в рабочей области|
|`"*/"`| она доступна для всех папок в рабочей области|
|`"*.cpp"`| она доступна для всех файлов с расширением .cpp в рабочей области|
|`"/*.cpp"`| она доступна для всех файлов с .cpp расширения в корне рабочей области|
|`"src/*/"`| она доступна для всех вложенных папках папки «src»|
|`"makefile"`| она доступна для всех файлов makefile в рабочей области|
|`"/makefile"`| задача доступна только для файла makefile, в корне рабочей области|

#### <a name="output"></a>output
Используйте `output` свойство, чтобы указать исполняемый объект, который будет запущен при нажатии клавиши **F5**. Пример:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>Макросы для tasks.vs.json

|||
|-|-|
|`${env.<VARIABLE>}`| Указывает любых переменных (например, ${env. ПУТЬ} ${env.COMSPEC} и т. д), заданным для командной строки разработчика. Дополнительные сведения см. в разделе [Командная строка разработчика для Visual Studio](/dotnet/framework/tools/developer-command-prompt-for-vs).|
|`${workspaceRoot}`| Полный путь к папке рабочей области (например, «C:\sources\hello»)|
|`${file}`| Полный путь к файлу или папке, выбранной для выполнения этой задачи по (например, «C:\sources\hello\src\hello.cpp»)|
|`${relativeFile}`| относительный путь к файлу или папке (например, «src\hello.cpp»)|
|`${fileBasename}`| Имя файла без пути или расширения (например, «hello»)|
|`${fileDirname}`| Полный путь к файлу, за исключением имени файла (например, «C:\sources\hello\src»)|
|`${fileExtname}`| расширение выбранного файла (например, «.cpp»)|

#### <a name="custom-macros"></a>Пользовательские макросы
Чтобы определить пользовательский макрос в tasks.vs.json, добавьте пару имя-значение до блоков задачи. В следующем примере определяется макрос с именем `outDir` которого используется в `args` свойство:

```json
{
"version": "0.2.1",
  "outDir": "${workspaceRoot}\\bin",
  "tasks": [
    {
      "taskName": "List outputs",
      "*",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": [
        "dir ${outDir}"
      ]
    }
  ]
```

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Настройка параметров отладки с launch.vs.json
Чтобы настроить аргументы командной строки программы, щелкните правой кнопкой мыши исполняемый файл в **обозревателе решений** и выберите **отладки и параметры запуска**. После этого откроется существующего `launch.vs.json` файл, или если она не существует, он создаст новый файл заполнены данными сведения о программе выбора. 

Чтобы указать дополнительные аргументы, просто добавьте их в `args` массив JSON, как показано в следующем примере:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CPP\\7zip\\Bundles\\Alone\\O\\7za.exe",
      "name": "7za.exe list content of helloworld.zip",
      "args": [ "l", "d:\\sources\\helloworld.zip" ]
    }
  ]
}
```

При сохранении этого файла, новая конфигурация отображается в раскрывающемся списке целевой объект отладки, и можно выбрать его для запуска отладчика. Можно создать как многие конфигурации отладки, сколько потребуется для любого количества исполняемых объектов. Если нажать клавишу **F5** теперь отладчик запустится и точки останова любого возможно уже задано. Теперь доступны все окна отладчика и их функциях.

## <a name="see-also"></a>См. также
[Интегрированная среда разработки и средства разработки Visual C++](ide-and-tools-for-visual-cpp-development.md)

