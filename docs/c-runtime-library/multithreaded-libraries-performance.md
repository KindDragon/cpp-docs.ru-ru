---
title: "Производительность многопотоковых библиотек | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "библиотеки, многопоточные"
  - "многопоточные библиотеки"
  - "производительность, многопоточность"
  - "работа с потоками [C++], производительность"
ms.assetid: faa5d808-087c-463d-8f0d-8c478d137296
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Производительность многопотоковых библиотек
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Однопоточные CRT более не доступны.  В этом разделе описано, как получить максимальную производительность при использовании многопоточных библиотек.  
  
## Максимальное увеличение производительности  
 Производительность многопоточных библиотек была улучшена и близка к производительности исключенных теперь однопоточных библиотек.  Есть несколько новых функций для ситуаций, когда нужна еще более высокая производительность.  
  
-   Независимая блокировка потоков позволяет блокировать поток и затем использовать [Функции \_nolock](../c-runtime-library/nolock-functions.md), которые получают доступ к потоку напрямую.  Это позволяет использовать блокировки вне критических циклов.  
  
-   Языковой стандарт по потокам снижает стоимость доступа языкового стандарта для многопоточного сценариев \(см. [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)\).  
  
-   Функции, зависящие от языкового стандарта, \(с оканчивающимися на \_l именами\) принимают в качестве параметра языковой стандарт, удаляя существенную часть затрат \(например, [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\).  
  
-   Оптимизации для общих кодовых страниц снижают стоимость множества простых операций.  
  
-   Определение [\_CRT\_DISABLE\_PERFCRIT\_LOCKS](../c-runtime-library/crt-disable-perfcrit-locks.md) заставляет все операции ввода\-вывода принять модель однопоточного ввода\-вывода и использовать \_nolock версии функций.  Это позволяет однопоточным приложениям, основанным в основном на вводе\-выводе, получить более высокую производительность.  
  
-   Предоставление дескриптора кучи CRT позволяет включить кучу низкой фрагментации Windows \(LFH\) для кучи CRT, что может значительно повысить производительность в легко масштабируемых сценариях.  
  
## См. также  
 [Особенности библиотеки CRT](../c-runtime-library/crt-library-features.md)