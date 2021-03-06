---
title: "Понятие вспомогательной функции | Документы Microsoft"
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
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3a013cf584c37f84331a5ab5dfe74eaa213c851
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-the-helper-function"></a>Понятие вспомогательной функции
Вспомогательная функция для отложенной загрузки, поддерживаемой компоновщика является загружает библиотеку DLL, во время выполнения. Вы можете изменить вспомогательную функцию, чтобы настроить ее поведение, создав собственную функцию и связывания его в программу вместо использования предоставленного вспомогательной функции в библиотекой Delayimp.lib. Одна вспомогательная функция обслуживает все отложенные загрузки библиотек DLL.  
  
 Можно предоставить собственную версию вспомогательной функции, если нужно выполнить специальную обработку на основе имен библиотеки DLL или импорта.  
  
 Вспомогательная функция выполняет следующие действия:  
  
-   Сопоставление хранимого дескриптора в библиотеку, чтобы увидеть, если он уже загружен  
  
-   Вызовы **LoadLibrary** предпринимается попытка загрузки библиотеки DLL  
  
-   Вызовы **GetProcAddress** попыток получение адреса процедуры  
  
-   Возвращает для импорта задержки загрузки преобразователя для вызова точки входа загрузить сейчас  
  
 Вспомогательная функция может выполнять обратный вызов перехватчика уведомлений в программе после выполнения каждой из следующих действий:  
  
-   При запуске вспомогательной функции  
  
-   Непосредственно перед **LoadLibrary** вызывается вспомогательной функции  
  
-   Непосредственно перед **GetProcAddress** вызывается вспомогательной функции  
  
-   Если вызов **LoadLibrary** вспомогательной функции не удалось  
  
-   Если вызов **GetProcAddress** вспомогательной функции не удалось  
  
-   После того как вспомогательная функция завершила обработку  
  
 Каждый из этих точек перехвата может возвращать значение, которое будет изменения обычной обработки вспомогательная подпрограмма каким-либо способом, кроме возвращения в преобразователь задержки импорта загрузки.  
  
 По умолчанию вспомогательный код можно найти в Delayhlp.cpp и файл Delayimp.h (в vc\include) и компилируется в библиотекой Delayimp.lib (в vc\lib). Необходимо будет включить эту библиотеку в компиляциях Если написать собственную вспомогательную функцию.  
  
 В следующих разделах описываются вспомогательной функции:  
  
-   [Изменения во вспомогательной функции отложенной загрузки библиотеки DLL по сравнению с Visual C++ версии 6.0](../../build/reference/changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)  
  
-   [Соглашения о вызовах, параметры и тип возвращаемого значения](../../build/reference/calling-conventions-parameters-and-return-type.md)  
  
-   [Определения структур и констант](../../build/reference/structure-and-constant-definitions.md)  
  
-   [Вычисление необходимых значений](../../build/reference/calculating-necessary-values.md)  
  
-   [Выгрузка библиотеки DLL с отложенной загрузкой](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
## <a name="see-also"></a>См. также  
 [Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)