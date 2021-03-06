---
title: "UNIX | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unix
dev_langs:
- C++
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f5155791f4bf12f15fa0c2c53d27fbe515e5af3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="unix"></a>UNIX
Если планируется переносить программы в среду UNIX, придерживайтесь следующих правил:  
  
-   Не удаляйте файлы заголовков из подкаталога SYS. Файлы заголовков SYS можно размещать в другом месте только в том случае, если не планируется переносить программы в UNIX.  
  
-   Используйте UNIX-совместимый разделитель пути в подпрограммах, принимающие в качестве аргументов строки, представляющие пути и имена файлов. UNIX для этих целей поддерживает только косую черту (/), тогда как операционные системы Win32 поддерживают и обратную косую черту (\\), и косую черту (/). Таким образом, в данной документации (например, в операторах `#include`) в качестве разделителей пути используются UNIX-совместимые косые черты. (Однако командная оболочка операционной системы Windows, CMD.EXE, не поддерживает косую черту в командах, вводимых в командной строке.)  
  
-   Используйте пути и имена файлов, правильно работающие в UNIX, где в них учитывается регистр. Файловая система FAT в операционных системах Win32 не учитывает регистр; файловая система NTFS сохраняет регистр для списков каталогов, но не учитывает регистр при поиске файлов и в других системных операциях.  
  
    > [!NOTE]
    >  В этой версии Visual C++ информация о совместимости с UNIX была удалена из описаний функций.  
  
## <a name="see-also"></a>См. также  
 [Совместимость](../c-runtime-library/compatibility.md)