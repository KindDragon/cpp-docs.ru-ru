---
title: "omp_get_num_procs | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_num_procs
dev_langs:
- C++
helpviewer_keywords:
- omp_get_num_procs OpenMP function
ms.assetid: 14a10b8f-e59b-4211-a292-687648c9f760
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a183b6c7b1d2a53e4cfc9b4cc6fa11b5a2177d5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ompgetnumprocs"></a>omp_get_num_procs
Возвращает количество процессоров, доступных при вызове функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int omp_get_num_procs();  
```  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [3.1.5 функция omp_get_num_procs](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_get_num_procs.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    printf_s("%d\n", omp_get_num_procs( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_num_procs( ));  
        }  
}  
```  
  
```Output  
// Expect the following output when the example is run on a two-processor machine:  
2  
2  
```  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)