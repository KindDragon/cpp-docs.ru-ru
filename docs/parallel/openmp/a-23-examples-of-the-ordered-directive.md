---
title: "Примеры A.23 упорядоченный директивы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83d77bb4f064a7ee69b013b36de919b57486b3e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23   Примеры директивы ordered
Можно иметь несколько разделов упорядоченный с `for` задается с помощью `ordered` предложения. Первый пример не соответствует требованиям, так как API указывается следующее:  
  
 «Итерации цикла с `for` конструкция же не может выполняться `ordered` директив более чем один раз и он должен выполняться не более одного `ordered` директива.» (См. [раздел 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) на странице 22)  
  
 В этом примере несоответствующих всех итераций выполните упорядоченный разделами:  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
}  
```  
  
 Показано в следующем примере совместимые `for` более чем с одной упорядоченную часть:  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    if (i <= 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
    (i > 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
}  
```