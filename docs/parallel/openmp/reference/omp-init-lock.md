---
title: "omp_init_lock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_init_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_init_lock OpenMP function
ms.assetid: 7a65e3e2-2e31-4645-964c-c1e82e2a4d0e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 420d2a6b0d636f4beff0e8b5bc20ffef5d2510a0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ompinitlock"></a>omp_init_lock
Инициализирует простые блокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void omp_init_lock(  
   omp_lock_t *lock  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `lock`  
 Переменная типа [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md).  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [3.2.1 функции omp_init_lock and omp_init_nest_lock](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_init_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t my_lock;  
  
int main() {  
   omp_init_lock(&my_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num( );  
      int i, j;  
  
      for (i = 0; i < 5; ++i) {  
         omp_set_lock(&my_lock);  
         printf_s("Thread %d - starting locked region\n", tid);  
         printf_s("Thread %d - ending locked region\n", tid);  
         omp_unset_lock(&my_lock);  
      }  
   }  
  
   omp_destroy_lock(&my_lock);  
}  
```  
  
```Output  
Thread 0 - starting locked region  
Thread 0 - ending locked region  
Thread 0 - starting locked region  
Thread 0 - ending locked region  
Thread 0 - starting locked region  
Thread 0 - ending locked region  
Thread 0 - starting locked region  
Thread 0 - ending locked region  
Thread 0 - starting locked region  
Thread 0 - ending locked region  
Thread 1 - starting locked region  
Thread 1 - ending locked region  
Thread 1 - starting locked region  
Thread 1 - ending locked region  
Thread 1 - starting locked region  
Thread 1 - ending locked region  
Thread 1 - starting locked region  
Thread 1 - ending locked region  
Thread 1 - starting locked region  
Thread 1 - ending locked region  
Thread 2 - starting locked region  
Thread 2 - ending locked region  
Thread 2 - starting locked region  
Thread 2 - ending locked region  
Thread 2 - starting locked region  
Thread 2 - ending locked region  
Thread 2 - starting locked region  
Thread 2 - ending locked region  
Thread 2 - starting locked region  
Thread 2 - ending locked region  
Thread 3 - starting locked region  
Thread 3 - ending locked region  
Thread 3 - starting locked region  
Thread 3 - ending locked region  
Thread 3 - starting locked region  
Thread 3 - ending locked region  
Thread 3 - starting locked region  
Thread 3 - ending locked region  
Thread 3 - starting locked region  
Thread 3 - ending locked region  
```  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)