---
title: "Зарезервированные слова | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
dev_langs:
- C++
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35f9a3e907b72b4b8cf8e673e771832ba3fc0527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="reserved-words"></a>Зарезервированные слова
Следующие слова зарезервированы компоновщиком. Эти имена могут использоваться как аргументы [операторов определения модуля](../../build/reference/module-definition-dot-def-files.md) только в том случае, если имя заключено в двойные кавычки (»»).  
  
||||  
|-|-|-|  
|**APPLOADER**1|**INITINSTANCE**2|**ПРЕДВАРИТЕЛЬНАЯ ЗАГРУЗКА**|  
|**BASE**|**IOPL**|**ЗАКРЫТЫЙ**|  
|**КОД**|**БИБЛИОТЕКА**1|**PROTMODE**2|  
|**СООТВЕТСТВУЮЩИЙ**|**LOADONCALL**1|**ЧИСТО**1|  
|**ДАННЫЕ**|**LONGNAMES**2|**ТОЛЬКО ДЛЯ ЧТЕНИЯ**|  
|**ОПИСАНИЕ**|**ПЕРЕМЕЩАЕМЫЙ**1|**READWRITE**|  
|**DEV386**|**MOVEABLE**1|**REALMODE**1|  
|**УДАЛЯЕМОЕ**|**НЕСКОЛЬКО**|**ВСТРОЕННЫЕ**|  
|**ДИНАМИЧЕСКИЕ**|**ИМЯ**|**RESIDENTNAME**1|  
|**ТОЛЬКО ДЛЯ ВЫПОЛНЕНИЯ**|**NEWFILES**2|**РАЗДЕЛЫ**|  
|**EXECUTEONLY**|**NODATA**1|**СЕГМЕНТЫ**|  
|**EXECUTEREAD**|**NOIOPL**1|**ОБЩИЕ**|  
|**EXETYPE**|**NONAME**|**ОДИН**|  
|**EXPORTS**|**НЕСООТВЕТСТВУЮЩИЕ**1|**STACKSIZE**|  
|**ФИКСИРОВАННЫЙ**1|**NONDISCARDABLE**|**STUB**|  
|**ФУНКЦИИ**2|**НЕТ**|**ВЕРСИЯ**|  
|**HEAPSIZE**|**НЕ ОБЩИЕ**|**WINDOWAPI**|  
|**ИМПОРТЫ**|**NOTWINDOWCOMPAT**1|**WINDOWCOMPAT**|  
|**НЕЧИСТЫХ**1|**ОБЪЕКТЫ**|**WINDOWS**|  
|**ВКЛЮЧИТЬ**2|**СТАРЫЙ**1||  
  
 1 Компоновщик выдает предупреждение («используется»), когда он встречает этот термин. Тем не менее слово по-прежнему остается зарезервированным.  
  
 2 компоновщик не обрабатывает это слово, но не выдает предупреждение.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)