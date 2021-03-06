---
title: "#undef директивы (C/C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#undef'
dev_langs:
- C++
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 428831b2718009fc0b471d238cff965f74528a2f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="undef-directive-cc"></a>Директива #undef (C/C++)
Удаляет имя, ранее созданное с помощью `#define`, то есть отменяет его определение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#undef   
identifier  
  
```  
  
## <a name="remarks"></a>Примечания  
 `#undef` Директива удаляет текущее определение *идентификатор*. Следовательно последующие вхождения *идентификатор* игнорируются препроцессором. Для удаления определения макроса с помощью `#undef`, введите только макроса *идентификатор* ; не предоставляют список параметров.  
  
 Также можно применить директиву `#undef` к идентификатору, который не имеет предыдущего определения. Это гарантирует, что идентификатор не определен. Замена макроса не выполняется внутри инструкций `#undef`.  
  
 Директива `#undef` обычно связана с директивой `#define` для создания области в программе-источнике, в которой идентификатор имеет специальное значение. Например, определенная функция программы-источника может использовать константы манифестов для определения значений среды, которые не влияют на остальные части программы. Директива `#undef` также работает с директивой `#if` с целью контроля условной компиляции программы-источника. В разделе [директивы #if, #elif, #else и #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) для получения дополнительной информации.  
  
 В следующем примере директива `#undef` удаляет определения символической константы и макрос. Обратите внимание, что предоставляется только идентификатор макроса.  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Отменить определение макросов можно из командной строки с использованием параметра /U, за которым следуют имена макросов, определения которых нужно отменить. При выполнении этой команды действует эквивалентно последовательность `#undef` *имя макроса* инструкции в начало файла.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Директивы препроцессора](../preprocessor/preprocessor-directives.md)