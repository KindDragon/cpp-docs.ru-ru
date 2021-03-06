---
title: "Ошибка средств компоновщика LNK1561 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1561
dev_langs:
- C++
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cbd0ca9e932bdb2845ada2f47b569391e943cb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1561"></a>Ошибка средств компоновщика LNK1561
точка входа должен быть определен  
  
Не удалось найти компоновщик *точки входа*, начальной функции, вызываемой в исполняемый файл. По умолчанию компоновщик будет искать `main` или `wmain` функции для консольного приложения, `WinMain` или `wWinMain` функции для приложения Windows, или `DllMain` для DLL-Библиотеки, требующий инициализации. Можно указать другой функции с помощью [/Entry](../../build/reference/entry-entry-point-symbol.md) компоновщика.  
  
Эта ошибка может иметь несколько причин:  
-   Возможно, не включен файл, который определяет точку входа в список файлов для связывания. Проверьте, связанного файла, содержащего функцию точки входа в приложение.  
-   Определенные точки входа, с помощью подписи неправильной функции; Например вы может опечатка или используемого неправильного регистра в имени функции или неправильно указан тип возвращаемого значения или типы параметров.  
-   Не указан [/DLL](../../build/reference/dll-build-a-dll.md) параметр при создании библиотеки DLL.  
-   Вы может неверно указанного имени функции точки входа при использовании [/Entry](../../build/reference/entry-entry-point-symbol.md) компоновщика.  
-   Если вы используете [LIB](../../build/reference/lib-reference.md) инструмент для создания библиотеки DLL, указанный DEF-файла. В этом случае удалите DEF-файл из сборки.    
  
При построении приложения, компоновщик будет искать функцию точки входа для вызова для запуска кода. Это функция, которая вызывается после загрузки приложения и инициализации среды выполнения. Необходимо указать функцию точки входа для приложения, или не удается запустить приложение. Точкой входа является необязательным для библиотеки DLL. По умолчанию компоновщик будет искать функцию точки входа, который имеет один из нескольких конкретные имена и подписи, такие как `int main(int, char**)`. Можно указать другое имя функции в качестве записи точки с помощью параметра компоновщика/ENTRY.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки LNK1561:  
  
```cpp  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```