---
title: "omp_get_wtime | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_wtime
dev_langs:
- C++
helpviewer_keywords:
- omp_get_wtime OpenMP function
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57307df6a2e13c6bd3dbd90892669119f8526d70
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ompgetwtime"></a>omp_get_wtime
Возвращает значение в секундах времени, прошедшего с какой-то момент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double omp_get_wtime( );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение в секундах времени прошло с момента некоторые произвольный, но согласованные.  
  
## <a name="remarks"></a>Примечания  
 Во время выполнения программы, делая возможности последующего сравнения будет поддерживать целостность этой точки.  
  
 Дополнительные сведения см. в разделе [3.3.1 функция omp_get_wtime](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_get_wtime.cpp  
// compile with: /openmp  
#include "omp.h"  
#include <stdio.h>  
#include <windows.h>  
  
int main() {  
    double start = omp_get_wtime( );  
    Sleep(1000);  
    double end = omp_get_wtime( );  
    double wtick = omp_get_wtick( );  
  
    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",  
             start, end, end - start);  
  
    printf_s("wtick = %.16g\n1/wtick = %.16g\n",  
             wtick, 1.0 / wtick);  
}  
```  
  
```Output  
start = 594255.3671159324  
end = 594256.3664474116  
diff = 0.9993314791936427  
wtick = 2.793651148400146e-007  
1/wtick = 3579545  
```  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)