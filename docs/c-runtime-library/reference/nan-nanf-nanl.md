---
title: "nan, nanf, nanl | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- nanf
- nan
- nanl
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- nan
- nanl
- nanf
dev_langs:
- C++
helpviewer_keywords:
- nan function
- nanf function
- nanl function
ms.assetid: 790e9158-80ab-43e0-8f5a-096198553fd9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8c3ba2620b43199788cfbcc237bc09a2cd112035
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="nan-nanf-nanl"></a>nan, nanf, nanl
Возвращает несигнальное значение NaN (QNaN).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double nan(  
   const char* input   
);  
float nanf(  
   const char* input   
);  
long double nanl(  
   const char* input   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `input`  
 Строковое значение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функции `nan` возвращают несигнальное значение NaN (QNaN).  
  
## <a name="remarks"></a>Примечания  
 Функции `nan` возвращают значение с плавающей запятой, которое соответствует несигнальному значению NaN (QNaN). Значение параметра `input` игнорируется. Сведения о том, как значение NaN представляется для вывода, см. в разделе [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`nan`, `nanf`, `nanl`|\<math.h>|\<cmath>|  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [_finite, _finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [_fpclass, _fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)