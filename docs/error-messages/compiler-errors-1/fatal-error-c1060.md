---
title: "Неустранимая ошибка C1060 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1060
dev_langs:
- C++
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c551ed3a6befbf646394929a6bcc6406ea93b19f
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="fatal-error-c1060"></a>Неустранимая ошибка C1060
компилятору не хватает размера кучи  
  
 Операционная система или библиотека времени выполнения не могут выполнить запрос на предоставление памяти.  
  
### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Чтобы устранить эту проблему, попробуйте следующие возможные решения  
  
1.  Если возникают ошибки компилятора [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) и [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md), используйте [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) параметр компилятора, чтобы снизить предел выделения памяти. Если уменьшить распределение оставшейся памяти, в куче останется больше места для вашего приложения.  
  
     Если [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) он уже установлен, попробуйте удалить ее. Место в куче может быть исчерпано из-за того, что предел распределения памяти, заданный с помощью этого параметра, слишком велик. Компилятор использует ограничение по умолчанию, если удалить [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) параметр.  
  
2.  Если компиляция происходит на 64-разрядной платформе, используйте 64-разрядный набор средств компиляции. Сведения см. в разделе [как: включить 64-разрядных инструментов Visual C++ в командной строке](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  На 32-разрядной версии Windows, попробуйте использовать [/3 GB](http://go.microsoft.com/fwlink/p/?linkid=177831) переключатель в файле boot.ini.  
  
4.  Увеличьте размер файла подкачки Windows.  
  
5.  Закройте все запущенные программы.  
  
6.  Удалите неиспользуемые включенные файлы.  
  
7.  Удалите ненужные глобальные переменные, например, путем динамического распределения памяти вместо объявления крупного массива.  
  
8.  Удалите неиспользуемые объявления.  
  
9. Разделите данный файл на меньшие файлы.