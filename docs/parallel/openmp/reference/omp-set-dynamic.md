---
title: "omp_set_dynamic | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_set_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_set_dynamic OpenMP function
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00ee1ad4c42e0d2f1303854cbd050e5601d0c3cd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ompsetdynamic"></a>omp_set_dynamic
Указывает, что число потоков, доступных в последующих параллельной области может настраиваться по времени выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `val`  
 Значение, указывающее, если число потоков, доступных в последующих параллельной области может настраиваться средой выполнения.  Если значение ненулевое, среда выполнения можно настроить количество потоков, если значение равно нулю, среда выполнения не динамически изменяются число потоков.  
  
## <a name="remarks"></a>Примечания  
 Число потоков, не может превышать значение, установленное [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или [OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md).  
  
 Используйте [omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) для отображения текущего значения параметра `omp_set_dynamic`.  
  
 Параметр для `omp_set_dynamic` переопределит параметр [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) переменной среды.  
  
 Дополнительные сведения см. в разделе [3.1.7 функция omp_set_dynamic](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)