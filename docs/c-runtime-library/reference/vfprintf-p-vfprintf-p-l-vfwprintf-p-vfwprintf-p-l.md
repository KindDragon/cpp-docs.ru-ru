---
title: "_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _vfprintf_p
- _vfwprintf_p
- _vfprintf_p_l
- _vfwprintf_p_l
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
apitype: DLLExport
f1_keywords:
- _vfwprintf_p_l
- _vfprintf_p
- vfwprintf_p_l
- vfwprintf_p
- vfprintf_p_l
- _vfwprintf_p
- _vftprintf_p
- _vfprintf_p_l
- vfprintf_p
dev_langs:
- C++
helpviewer_keywords:
- vfprintf_p_l function
- _vftprintf_p_l function
- _vfprintf_p function
- vfprintf_p function
- vftprintf_p_l function
- _vfprintf_p_l function
- _vftprintf_p function
- _vfwprintf_p_l function
- vfwprintf_p_l function
- _vfwprintf_p function
- vftprintf_p function
- formatted text [C++]
- vfwprintf_p function
ms.assetid: 4d4a0914-4175-4b65-9ca1-037c4ef29147
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bdbb916ef756d3437c8d4df1af725fc49fdfff6d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="vfprintfp-vfprintfpl-vfwprintfp-vfwprintfpl"></a>_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l
Записывают форматированные выходные данные, используя указатель на список аргументов, с возможностью указать порядок, в котором эти аргументы используются в строке формата.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _vfprintf_p(  
   FILE *stream,  
   const char *format,  
   va_list argptr   
);  
int _vfprintf_p_l(  
   FILE *stream,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vfwprintf_p(  
   FILE *stream,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vfwprintf_p_l(  
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE` .  
  
 `format`  
 Спецификация формата.  
  
 `argptr`  
 Указатель на список аргументов.  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [Спецификации формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функции `_vfprintf_p` и `_vfwprintf_p` возвращают число записанных символов, не включая конечный нуль-символ, или отрицательное значение, если произошла ошибка вывода.  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций принимает указатель на список аргументов, а затем форматирует и записывает указанные данные в `stream`. Эти функции отличаются от версий `_vfprint_s` и `_vfwprint_s` только в том, что они поддерживают позиционные параметры. Дополнительные сведения см. в разделе [Позиционные параметры printf_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Функция `_vfwprintf_p` является версией функции `_vprintf_p` с расширенными символами; обе функции ведут себя одинаково, если поток открыт в режиме ANSI. Функция `_vprintf_p` на данный момент не поддерживает вывод данных в поток в кодировке Юникод.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
> [!IMPORTANT]
>  Убедитесь, что `format` не является строкой, определяемой пользователем. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Если `stream` или `format` является пустым указателем либо строка форматирования содержит недопустимые символы форматирования, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, функции возвращают значение -1 и задают для `errno` значение `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vftprintf_p`|`_vfprintf_p`|`_vfprintf_p`|`_vfwprintf_p`|  
|`_vftprintf_p_l`|`_vfprintf_p_l`|`_vfprintf_p_l`|`_vfwprintf_p_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|-------------|---------------------|----------------------|  
|`_vfprintf_p`, `_vfprintf_p_l`|\<stdio.h> и \<stdarg.h>|\<varargs.h>*|  
|`_vfwprintf_p`, `_vfwprintf_p_l`|\<stdio.h> или \<wchar.h> и \<stdarg.h>|\<varargs.h>*|  
  
 \* Требуется для совместимости с UNIX V.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)   
 [Позиционные параметры printf_p](../../c-runtime-library/printf-p-positional-parameters.md)   
 [_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)   
 [_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)