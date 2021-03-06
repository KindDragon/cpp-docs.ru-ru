---
title: "Если (OpenMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- if OpenMP clause
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f878a04a7db2243109d034ad93496e860ab1e3c7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="if-openmp"></a>if (OpenMP)
Указывает, следует ли выполнять цикл параллельно или последовательно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
if(expression)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `expression`  
 Целочисленное выражение, если значение равно true (ненулевой), приводит к тому код в параллельной области для параллельного выполнения. Если выражение имеет значение false (0), параллельной области выполняется последовательно (одним потоком).  
  
## <a name="remarks"></a>Примечания  
 `if` применяется к следующие директивы:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.3 конструкция parallel](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_if.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
void test(int val)  
{  
    #pragma omp parallel if (val)  
    if (omp_in_parallel())  
    {  
        #pragma omp single  
        printf_s("val = %d, parallelized with %d threads\n",  
                 val, omp_get_num_threads());  
    }  
    else  
    {  
        printf_s("val = %d, serialized\n", val);  
    }  
}  
  
int main( )  
{  
    omp_set_num_threads(2);  
    test(0);  
    test(2);  
}  
```  
  
```Output  
val = 0, serialized  
val = 2, parallelized with 2 threads  
```  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)