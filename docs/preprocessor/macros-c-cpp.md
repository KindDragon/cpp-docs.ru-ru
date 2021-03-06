---
title: "Макросы (C/C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- preprocessor, macros
- Visual C++, preprocessor macros
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a230abc768b23afd74d1af8a9c178d39d453536a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="macros-cc"></a>Макросы (C/C++)
Предварительная обработка разворачивает макросы во всех строках, которые не являются директивами препроцессора (строки, которые не имеют  **#**  первым символом пустого пространства) и в части некоторые директивы, которые не пропускаются в ходе Условная компиляция. Директивы условной компиляции позволяют подавлять компиляцию частей исходного файла путем проверки константного выражения или идентификатора для определения того, какие блоки текста передаются в компилятор, а какие блоки текста удаляются из исходного файла во время предварительной обработки.  
  
 Директива `#define` обычно используется для связывания понятных идентификаторов с константами, ключевыми словами и часто используемыми операторами или выражениями. Идентификаторы, которые представляют константы, иногда называются символическими константами или константами манифеста. Идентификаторы, которые представляют операторы или выражения, называются макросами. В этой документации препроцессора используется только термин "макрос".  
  
 Если имя макроса найдено в исходном тексте программы или в аргументах некоторых других команд препроцессора, оно обрабатывается как вызов этого макроса. Имя макроса заменяется копией тела макроса. Если макрос принимает аргументы, фактические аргументы после имени макроса заменяются на формальные параметры в теле макроса. Процесс замены вызова макроса на обработанную копию тела называется расширением вызова макроса.  
  
 На практике это означает, что существует два типа макросов. Похожие на объект макросы не принимают аргументы, тогда как похожие на функцию макросы можно определить для принятия аргументов, чтобы они выглядели и действовали как вызовы функций. Поскольку макросы не создают фактические вызовы функций, иногда можно ускорить выполнение программы, заменив вызовы функций макросами. (В C++ подставляемые функции часто являются предпочтительным методом.) Однако если макросы не определять и не использовать с осторожностью, они могут привести к проблемам. Возможно, потребуется использовать круглые скобки в определениях макроса с аргументами, чтобы сохранить правильный приоритет в выражении. Кроме того, макросы могут неправильно обработать выражения с побочными эффектами. В разделе `getrandom` пример в [#define-директива](../preprocessor/hash-define-directive-c-cpp.md) для получения дополнительной информации.  
  
 После определения макроса его невозможно переопределить другим значением, если сначала не удалить исходное определение. Однако макрос можно переопределить точно таким же определением. Таким образом, одно определение может использоваться в программе несколько раз.  
  
 #**Undef** директива удаляет определение макроса. После удаления определения можно переопределить макрос другим значением. [#Define-директива](../preprocessor/hash-define-directive-c-cpp.md) и [директива #undef](../preprocessor/hash-undef-directive-c-cpp.md) обсудить `#define` и `#undef` директивы, соответственно.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Макросы и C++](../preprocessor/macros-and-cpp.md)  
  
-   [Макросы с переменным числом аргументов](../preprocessor/variadic-macros.md)  
  
-   [Предопределенные макросы](../preprocessor/predefined-macros.md)  
  
## <a name="see-also"></a>См. также  
 [Справочник по препроцессору в C/C++](../preprocessor/c-cpp-preprocessor-reference.md)