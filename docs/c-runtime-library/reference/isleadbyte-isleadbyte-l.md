---
title: "isleadbyte, _isleadbyte_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _isleadbyte_l
- isleadbyte
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _istleadbyte
- _isleadbyte_l
- isleadbyte
dev_langs:
- C++
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82c8f6eb81e96527c0955d9b19fd8ce931e8d7fe
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l
Определяет, является ли символ начальным байтом многобайтового символа.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Проверяемое целое число.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `isleadbyte` возвращает ненулевое значение, если аргумент удовлетворяет условию теста, или значение 0 в противном случае. В языковом стандарте "C" и в языковых стандартах однобайтовой кодировки (SBCS) `isleadbyte` всегда возвращает значение 0.  
  
## <a name="remarks"></a>Примечания  
 Макрос `isleadbyte` возвращает ненулевое значение, если его аргумент является первым байтом многобайтового символа. `isleadbyte` выдает значимый результат для любого целочисленного аргумента от – 1 (`EOF`) для `UCHAR_MAX` (0xFF) включительно.  
  
 Ожидаемый тип аргумента `isleadbyte` — `int`. Если передается символ со знаком, компилятор может преобразовать его в целое число по расширению знака, создавая непредсказуемые результаты.  
  
 Версия этой функции с суффиксом `_l` идентична, однако для поведения, определяемого языковым стандартом, вместо текущего языкового стандарта в ней используется переданный языковой стандарт.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istleadbyte`|Всегда возвращает значение false|**_** `isleadbyte`|Всегда возвращает значение false|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`isleadbyte`|\<ctype.h>|  
|`_isleadbyte_l`|\<ctype.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)