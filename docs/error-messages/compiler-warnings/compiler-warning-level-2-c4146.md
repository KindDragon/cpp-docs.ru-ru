---
title: "Предупреждение (уровень 2) C4146 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4146
dev_langs:
- C++
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7a9a67beb4dc122c25318c1796e22a4c35dbe38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4146"></a>Предупреждение (уровень 2) C4146 компилятора
Применение унарного минуса к типу без знака; результат оставлен без знака  
  
 Беззнаковые типы может содержать только неотрицательные значения, поэтому унарный минус (отрицание) не имеет смысла при применении к типу без знака. Операнд и результат не являются отрицательными.  
  
 На практике это происходит, когда программист пытается выразить минимальное целое значение, которое равно -2147483648. Это значение нельзя записать в качестве от -2147483648, поскольку выражение обрабатывается в два этапа:  
  
1.  Число 2147483648 вычисляется. Так как оно превышает максимальное целое значение 2147483647, тип числа 2147483648 не [int](../../c-language/integer-types.md), но `unsigned int`.  
  
2.  Унарный минус применяется к значению с результатом без знака, который также является 2147483648.  
  
 Беззнаковый тип результата, может привести к непредвиденному поведению. Если результат используется в сравнении, то сравнение без знака может использоваться, например, если другой операнд — `int`. Это объясняет, почему программа в примере выводит только одну строку.  
  
 Ожидаемая вторая строка `1 is greater than the most negative int`, так как не печатается `((unsigned int)1) > 2147483648` имеет значение false.  
  
 Можно избежать с помощью INT_MIN из файла limits.h, который имеет тип C4146 **типа signed int**.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4146:  
  
```  
// C4146.cpp  
// compile with: /W2  
#include <stdio.h>  
  
void check(int i)   
{  
    if (i > -2147483648)   // C4146  
        printf_s("%d is greater than the most negative int\n", i);  
}  
  
int main()   
{  
    check(-100);  
    check(1);  
}  
```