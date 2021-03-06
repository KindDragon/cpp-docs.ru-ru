---
title: "Импорт и экспорт | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c0727002e264f3b0cfe39b763c29fd70725b982
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="importing-and-exporting"></a>Импортирование и экспортирование
Можно импортировать открытые символы в приложение или экспортировать функции из библиотеки DLL с помощью двух методов:  
  
-   Использование файла определения модуля (DEF) при создании библиотеки DLL  
  
-   Используйте ключевые слова **__declspec(dllimport)** или **__declspec(dllexport)** в определении функции в основное приложение  
  
## <a name="using-a-def-file"></a>С помощью DEF-файла  
 Файл определения модуля (DEF) является текстовый файл, содержащий один или несколько операторов модуля, описывающих различные атрибуты библиотеки DLL. Если вы не используете **__declspec(dllimport)** или **__declspec(dllexport)** DEF-файла для экспорта функций библиотеки DLL, необходимой библиотеке DLL.  
  
 Можно использовать DEF-файлы для [импорта в приложение](../build/importing-using-def-files.md) или [Экспорт из библиотеки DLL](../build/exporting-from-a-dll-using-def-files.md).  
  
## <a name="using-declspec"></a>С помощью __declspec  
 Visual C++ использует **__declspec(dllimport)** и **__declspec(dllexport)** заменить **__export** ключевое слово ранее в 16-разрядных версиях Visual C++.  
  
 Необходимо использовать **__declspec(dllimport)** для кода для компиляции правильно, но это позволяет компилятору создавать качество кода. Компилятор не может создать качество кода, так как он может определить наличие функции в библиотеке DLL или нет, что позволяет компилятору создать код, который пропускает уровень косвенности, присутствует в вызове функции, в библиотеке. Тем не менее, необходимо использовать **__declspec(dllimport)** для импортирования переменных, используемых в библиотеке DLL.  
  
 С разделе EXPORTS файл .def правильную **__declspec(dllexport)** не является обязательным. **__declspec(dllexport)** был добавлен для облегчения экспорта функций из файла .exe или .dll без использования DEF-файла.  
  
 Формат переносимого исполняемого файла Win32 разработан для минимизации количества страниц, предназначенных для отладки импортов. Чтобы сделать это, она помещает Импорт адресов по любой программе, в одном месте, таблица адресов импорта. Это позволяет загрузчику модифицировать только одну или несколько страниц при доступе к эти операции импорта.  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Импорт в приложение](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)  
  
## <a name="see-also"></a>См. также  
 [DLL в Visual C++](../build/dlls-in-visual-cpp.md)