---
title: "Определение библиотек DLL для распространения | Документы Microsoft"
ms.custom: 
ms.date: 09/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- redistributing DLLs
- DLLs [C++], redistributing
- dependencies [C++], application deployment and
- application deployment [C++], DLL redistribution
- deploying applications [C++], DLL redistribution
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a3cc7b80e16abeecc756e7fa480c7bfe71682382
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="determining-which-dlls-to-redistribute"></a>Определение библиотек DLL для распространения

При построении приложения, использующего библиотек DLL, предоставляемые Visual Studio пользователь приложения должен также иметь эти библиотеки DLL на своих компьютерах для запуска приложения. Поскольку у большинства пользователей, скорее всего, отсутствует Visual Studio, необходимо передать им эти файлы. Visual Studio создает эти библиотеки DLL как *распространяемые файлы* , которую можно включить в состав установщика приложения.

Чтобы упростить включать распространяемые библиотеки DLL с установщиком, они доступны в качестве автономного *распространяемые пакеты*. Это исполняемые файлы конкретной архитектуры, использующих центральное развертывание установки распространяемого пакета на компьютере пользователя. Например, vcredist\_x86.exe устанавливает 32-разрядной библиотеки для x86 компьютеров, vcredist\_x64.exe устанавливает 32-разрядных и 64-разрядные библиотеки для x64 компьютеров и vcredist\_ARM.exe устанавливает библиотеки для ARM на компьютерах. Рекомендуется центральное развертывание, так как корпорации Майкрософт могут использовать службы Центра обновления Windows для обновления этих библиотек независимо друг от друга. Помимо копирования в установку Visual Studio, текущий распространяемые пакеты доступны для загрузки на [VisualStudio.com/Downloads](https://www.visualstudio.com/downloads/) в разделе другие инструменты и платформы.

Основной номер версии развертываемого распространяемого пакета должна совпадать с версией набора инструментов Visual Studio для создания приложения. Visual Studio 2017 г. и Visual Studio 2015 содержат номеров версии совместимый набор инструментов, это означает, что 2017 г Visual Studio, может использовать приложения, разработанные с помощью набора инструментов 2015 распространяемые файлы. Хотя они могут быть совместимыми, мы не поддерживают использование 2015 распространяемые файлы в приложения, разработанные с помощью набора инструментов 2017 г. Поддерживается только с помощью распространяемого пакета, который является таким же, как или более поздней версии, чем версия набора инструментов. Ссылки на новейшие поддерживаемых распространяемые пакеты для более старых наборов инструментов см. в разделе [последнее поддерживается загружаемые файлы Visual C++](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads). Распространяемые пакеты конкретных более ранних версий может быть найден посредством поиска [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/p/?LinkId=158431) для «Распространяемые пакеты Visual C++».

Еще один способ включения распространяемых библиотек DLL с установщиком является использование *модули слияния*. Эти модули установщика Microsoft включаются в и установленные установщик приложения. Модули слияния для распространяемых библиотек DLL находятся в каталоге установки Visual Studio под \\VC\\Redist\MSVC\\*версии*\\MergeModules\\ . В более ранних версиях Visual Studio, эти файлы находятся в вашей \\Program Files или \\каталог Program Files (x86) в общие файлы\\подкаталог модулей слияния. Дополнительные сведения об использовании этих файлов см. в разделе [распространение компонентов с помощью модулей слияния](../ide/redistributing-components-by-using-merge-modules.md).

Отдельные распространяемых библиотек DLL также включаются в установку Visual Studio. По умолчанию они устанавливаются в каталог установки Visual Studio в \\VC\\Redist\\параметры MSVC\\*версии* папки. *Версии* чисел может представляют собой дополнительный номер сборки число один общий набор распространяемые файлы. Используйте последнюю версию библиотеки DLL-файл, распространяемый пакет или модуль слияния, в этих каталогах. Вы можете использовать эти библиотеки для локального развертывания, которые устанавливаются в том же каталоге, что и приложение. Мы не рекомендуем локальное развертывание, поскольку это делает вы ответственность за доставку обновлений развернутые приложения. Централизованное развертывание с помощью распространяемых пакетов является предпочтительным.

Чтобы определить, какие библиотеки DLL необходимо повторно распространить вместе с приложением, составьте список библиотек DLL, от которых зависит приложение. Обычно они перечислены как импортировать входные данные библиотек в компоновщик. Некоторые библиотеки, такие как vcruntime и универсальная C времени выполнения библиотеки (UCRT), включенные по умолчанию. Если ваше приложение или одна из ее зависимостей использует LoadLibrary для динамической загрузки библиотеки DLL, DLL, могут не отображаться в качестве входных данных компоновщика. Составить список библиотек DLL, динамически загружаемые будет запущена Dependency Walker (depends.exe) в приложении, как описано в [основные сведения о зависимостях приложения Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). К сожалению этот инструмент устарел и может сообщить, что не удается найти определенных библиотек DLL.

Составив список зависимостей, сравните его в список, связанный в файле Redist.txt, расположенного в каталоге установки Microsoft Visual Studio, или «списком REDIST» распространяемых библиотек DLL, упоминаемый в разделе «Распространяемый код файлов» Лицензионного соглашения программного обеспечения корпорации Майкрософт для вашей копии Visual Studio. Visual Studio 2017 г. в разделе [распространяемый код для Microsoft Visual Studio 2017 г. (включает служебные программы, расширяемости и файлы BuildServer)](http://go.microsoft.com/fwlink/p/?linkid=823098). Visual Studio 2015. в разделе [распространяемый код для Microsoft Visual Studio 2015 и Microsoft Visual Studio 2015 SDK (включает служебные программы и файлы BuildServer)](http://go.microsoft.com/fwlink/p/?linkid=799794). Для Visual Studio 2013 списке доступна в [распространяемый код для Microsoft Visual Studio 2013 и Microsoft Visual Studio 2013 SDK](http://go.microsoft.com/fwlink/p/?LinkId=313603).

В версиях Visual Studio до Visual Studio 2015, библиотеку времени выполнения C (CRT) был включен в качестве распространяемые библиотеки DLL, в параметры msvc*версии*DLL-файл. Начиная с Visual Studio 2015, функций в CRT были подвергнуты рефакторингу в vcruntime и UCRT. UCRT теперь является компонентом системы в Windows 10, управляемых центром обновления Windows. Он доступен во всех операционных системах Windows 10. Для развертывания приложения в более ранних операционных систем, необходимо повторно распространить также UCRT. Ранние версии UCRT включается в файлы распространяемого пакета Visual Studio, на которых устанавливается только на операционных систем более ранних, чем Windows 10, и только если установлена версия не UCRT. Устанавливаемую версию UCRT предыдущими версиями этой системы в качестве пакета обновления системы Майкрософт, в разделе [универсальная C среда выполнения Windows 10](https://www.microsoft.com/en-us/download/details.aspx?id=48234) в центре загрузки Майкрософт.

Невозможно повторно распространить все файлы, включенные в Visual Studio. Разрешается повторно распространить только файлы, указанные в файле Redist.txt или в "списке REDIST" в Интернете. Отладочные версии приложений и различные отладочные библиотеки DLL-файлов Visual C++ невозможно повторно распространить. Дополнительные сведения см. в разделе [Выбор метода развертывания](../ide/choosing-a-deployment-method.md).

В следующей таблице описываются некоторые библиотеки DLL Visual C++, от которых может зависеть ваше приложение.

|Библиотека Visual C++|Описание:|Применение|
|--------------------------|-----------------|----------------|
|vcruntime*версии*.dll|Библиотека времени выполнения для машинного кода.|Приложения, использующие обычный C и C++ языка запуска и завершения работы службы.|
|vccorlib*версии*.dll|Библиотека времени выполнения для управляемого кода.|Приложения, использующие службы языка C++ для управляемого кода.|
|msvcp*версии*.dll|Стандартная библиотека C++ для машинного кода.|Приложения, использующие [стандартной библиотеки C++](../standard-library/cpp-standard-library-reference.md).|
|concrt*версии*.dll|Библиотека времени выполнения с параллелизмом для машинного кода.|Приложения, использующие [среда выполнения с параллелизмом](../parallel/concrt/concurrency-runtime.md).|
|MFC*версии*.dll|Библиотека Microsoft Foundation Class (MFC).|Приложения, использующие [библиотеки MFC](../mfc/mfc-desktop-applications.md).|
|MFC*версии* *языка*.dll|Microsoft Foundation классы ресурсов библиотеки (MFC).|Приложения, использующие ресурсы для конкретного языка для MFC.|
|MFC*версии*u.dll|Библиотека MFC с поддержкой Юникода.|Приложения, использующие [библиотеки MFC](../mfc/mfc-desktop-applications.md) и требующие поддержки Юникода.|
|mfcmifc80.dll|Библиотека управляемых интерфейсов MFC.|Приложения, использующие [библиотеки MFC](../mfc/mfc-desktop-applications.md) с [элементов управления Windows Forms](/dotnet/framework/winforms/controls/index).|
|mfcm*версии*.dll|Управляемая библиотека MFC.|Приложения, использующие [библиотеки MFC](../mfc/mfc-desktop-applications.md) с [элементов управления Windows Forms](/dotnet/framework/winforms/controls/index).|
|mfcm*версии*u.dll|Управляемая библиотека MFC с поддержкой Юникода.|Приложения, использующие [библиотеки MFC](../mfc/mfc-desktop-applications.md) с [элементов управления Windows Forms](/dotnet/framework/winforms/controls/index) и требующие поддержки Юникода.|
|vcamp*версии*.dll|Библиотека управления Устройством для машинного кода.|Приложения, использующие [библиотеки C++ AMP](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md) кода.|
|vcomp*версии*.dll|Библиотеки OpenMP для машинного кода.|Приложения, использующие [библиотеки C++ OpenMP](../parallel/openmp/openmp-in-visual-cpp.md) кода.|

> [!NOTE]
> Библиотеку шаблонных классов ATL больше не требуется повторно распространять в качестве отдельного DLL-файла. Ее функции были переданы заголовкам и статической библиотеке.

Дополнительные сведения о повторном распространении этих библиотек DLL с приложением см. в разделе [распространение файлов Visual C++](../ide/redistributing-visual-cpp-files.md). Примеры см. в разделе [примеры развертывания](../ide/deployment-examples.md).

Как правило, повторное распространение системных DLL-файлов не требуются, поскольку они входят в состав операционной системы. Однако возможны исключения, например если приложение выполняется в нескольких версиях операционных систем Microsoft. В этом случае необходимо внимательно ознакомиться с соответствующими условиями лицензирования. Также попробуйте обновить системные библиотеки DLL с помощью центра обновления Windows, пакетов обновления или повторно распространяемых пакетов, предоставляемых Майкрософт.

## <a name="see-also"></a>См. также

[Выбор метода развертывания](../ide/choosing-a-deployment-method.md)

[Развертывание приложений для настольных систем](../ide/deploying-native-desktop-applications-visual-cpp.md)
