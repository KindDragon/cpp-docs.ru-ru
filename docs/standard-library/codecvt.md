---
title: "&lt;codecvt&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- codecvt
- <codecvt>
dev_langs:
- C++
helpviewer_keywords:
- codecvt header
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea9bf0c81e66f875a3a94ab1e5783bcd4de91edd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltcodecvtgt"></a>&lt;codecvt&gt;
Определяет несколько классов шаблонов, которые описывают объекты на основе класса шаблона [codecvt](../standard-library/codecvt-class.md). Эти объекты могут служить как [аспекты языкового стандарта](../standard-library/locale-class.md#facet_class) для управления преобразованиями между последовательностями значений типа `Elem` и последовательностями значений типа `char`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <codecvt>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Аспекты языкового стандарта, объявленные в этом заголовке, преобразуются между несколькими кодировками символов. Для расширенных символов (хранящихся в программе в виде целых чисел фиксированного размера):  
  
-   UCS-4 — в кодировке Юникод (ISO 10646) в рамках программы;  
  
-   UCS-4 — в кодировке Юникод (ISO 10646) в рамках программы в виде 32-разрядного целого числа;  
  
-   UCS-2 — в кодировке Юникод в рамках программы;  
  
-   UCS-2 — в кодировке Юникод в рамках программы в виде 16-разрядного целого числа;  
  
-   UTF-16 — в кодировке Юникод в рамках программы в виде одного  
  
-   UTF-16 — в кодировке Юникод в рамках программы в виде одного или двух 16-разрядных целых чисел. (Обратите внимание, что это не соответствует всем требованиям допустимых кодировок Юникода для расширенных символов в стандартном языке C или C++. Тем не менее это широко используется.)  
  
 Для потоков байтов (хранящихся в файле, передаваемых в виде последовательности байтов или сохраненных в программе в массиве `char`):  
  
-   UTF-8 — в кодировке Юникод;  
  
-   UTF-8 — в кодировке Юникод в потоке байтов как один или несколько 8-битовых байтов с детерминированным порядком байтов;  
  
-   UTF-16LE — в кодировке Юникод;  
  
-   UTF-16LE — в кодировке Юникод в потоке байтов в виде UTF-16 с каждым 16-разрядным целым числом, представленным в виде двух 8-битовых байт, с первым менее старшим байтом;  
  
-   UTF-16BE — в кодировке Юникод;  
  
-   UTF-16BE — в кодировке Юникод в потоке байтов в виде UTF-16 с каждым 16-разрядным целым числом, представленным в виде двух 8-битовых байт, с первым более старшим байтом.  
  
### <a name="enumerations"></a>Перечисления  
  
|||  
|-|-|  
|[codecvt_mode](../standard-library/codecvt-enums.md#codecvt_mode)|Указывает сведения о конфигурации для аспектов языкового стандарта.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[codecvt_utf8](codecvt-utf8-class.md)|Представляет аспект языкового стандарта, который выполняет преобразование между расширенными символами в кодировке UCS-2 или UCS-4 и потоком байтов в кодировке UTF-8.|  
|[codecvt_utf8_utf16](codecvt-utf8-utf16-class.md)|Представляет аспект языкового стандарта, который выполняет преобразование между расширенными символами в кодировке UTF-16 и потоком байтов в кодировке UTF-8.|  
|[codecvt_utf16](codecvt-utf16-class.md)|Представляет аспект языкового стандарта, который выполняет преобразование между расширенными символами в кодировке UCS-2 или UCS-4 и потоком байтов в кодировке UTF-16LE или UTF-16BE.|  

  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<codecvt>  
  
 **Пространство имен:** stdt  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)




