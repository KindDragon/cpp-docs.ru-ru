---
title: "сообщение | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- message_CPP
- vc-pragma.message
dev_langs:
- C++
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb998ef084f259601478ea9614a2bd8dc3da0d68
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="message"></a>сообщение
Отправляет строковый литерал в стандартный вывод, не завершая компиляцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma message( messagestring )  
```  
  
## <a name="remarks"></a>Примечания  
 Типичное применение **сообщение** pragma — Отображать информационные сообщения во время компиляции.  
  
 *Messagestring* параметр может быть макросом, который расширяется до строкового литерала, и можно сцепить эти макросы со строковыми литералами в любой комбинации.  
  
 При использовании предопределенного макроса в **сообщение** pragma, макрос должен вернуть строку, в противном случае необходимо преобразовать вывод макроса в строку.  
  
 В следующем фрагменте кода используется **сообщение** директивы pragma, для отображения сообщений во время компиляции:  
  
```  
// pragma_directives_message1.cpp  
// compile with: /LD  
#if _M_IX86 >= 500  
#pragma message("_M_IX86 >= 500")  
#endif  
  
#pragma message("")  
  
#pragma message( "Compiling " __FILE__ )   
#pragma message( "Last modified on " __TIMESTAMP__ )  
  
#pragma message("")  
  
// with line number  
#define STRING2(x) #x  
#define STRING(x) STRING2(x)  
  
#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")  
  
#pragma message("")  
```  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)