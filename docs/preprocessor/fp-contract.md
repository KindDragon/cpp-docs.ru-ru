---
title: "fp_contract | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7283fa9d9dfb8e35bf96e76d88eb1a9ee80e510
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="fpcontract"></a>fp_contract
Определяет, будет ли выполняться сокращение чисел с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma fp_contract [ON | OFF]  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию ключевое слово `fp_contract` имеет значение ON (включено).  
  
 Дополнительные сведения о работе с плавающей запятой см. в разделе [/FP (указать поведение с плавающей запятой)](../build/reference/fp-specify-floating-point-behavior.md).  
  
 Другие типы директив pragma для значений с плавающей запятой:  
  
-   [fenv_access](../preprocessor/fenv-access.md)  
  
-   [float_control](../preprocessor/float-control.md)  
  
## <a name="example"></a>Пример  
 Код, созданный в этом примере не использует совмещенного умножения-сложения (**fma**) инструкции на процессорах Itanium. Если закомментировать строку `#pragma fp_contract (off)`, созданный код будет использовать **fma** инструкции.  
  
```  
// pragma_directive_fp_contract.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>  
  
#pragma fp_contract (off)   
  
int main() {  
   double z, b, t;  
  
   for (int i = 0; i < 10; i++) {  
      b = i * 5.5;  
      t = i * 56.025;  
      _set_controlfp(_PC_24, _MCW_PC);  
  
      z = t * i + b;  
      printf_s ("out=%.15e\n", z);  
   }  
}  
```  
  
```Output  
out=0.000000000000000e+000  
out=6.152500152587891e+001  
out=2.351000061035156e+002  
out=5.207249755859375e+002  
out=9.184000244140625e+002  
out=1.428125000000000e+003  
out=2.049899902343750e+003  
out=2.783724853515625e+003  
out=3.629600097656250e+003  
out=4.587524902343750e+003  
```  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)