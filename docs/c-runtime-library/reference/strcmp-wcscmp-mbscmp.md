---
title: "strcmp, wcscmp, _mbscmp | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- wcscmp
- _mbscmp
- strcmp
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbscmp
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
dev_langs:
- C++
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ced77db630f0cffede96192dbb9fc69ec0061db
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="strcmp-wcscmp-mbscmp"></a>strcmp, wcscmp, _mbscmp
Сравнивают строки.  
  
> [!IMPORTANT]
>  `_mbscmp` не может использоваться в приложениях, запускаемых в среде выполнения Windows. Дополнительные сведения см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int strcmp(  
   const char *string1,  
   const char *string2   
);  
int wcscmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `string1`, `string2`  
 Строки с завершающим нулем для сравнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение каждой из этих функций отображает порядковое отношение строки `string1` к строке `string2`.  
  
|Значение|Отношение string1 к string2|  
|-----------|----------------------------------------|  
|< 0|`string1` меньше `string2`|  
|0|`string1` идентична `string2`|  
|> 0|`string1` больше `string2`|  
  
 При ошибке проверки параметра функция `_mbscmp` возвращает ошибку `_NLSCMPERROR`, которая определена в \<string.h> и \<mbstring.h>.  
  
## <a name="remarks"></a>Примечания  
 Функция `strcmp` выполняет порядковое сравнение строк `string1` и `string2` и возвращает значение, которое указывает их отношение. Функции `wcscmp` и `_mbscmp` являются версиями функции `strcmp` для расширенных и многобайтовых символов соответственно. `_mbscmp` распознает последовательности многобайтовых символов в соответствии с текущей многобайтовой кодовой страницей и возвращает `_NLSCMPERROR` при ошибке. Дополнительные сведения см. в разделе [Кодовые страницы](../../c-runtime-library/code-pages.md). Кроме того, если `string1` или `string2` является пустым указателем, функция `_mbscmp` вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция `_mbscmp` возвращает значение `_NLSCMPERROR` и устанавливает параметр `errno` в значение `EINVAL`. Функции `strcmp` и `wcscmp` не проверяют свои параметры. В остальном эти три функции ведут себя идентично.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcscmp`|`strcmp`|`_mbscmp`|`wcscmp`|  
  
 Функции `strcmp` отличаются от функций `strcoll` тем, что сравнение `strcmp` является порядковым и не зависит от языкового стандарта. `strcoll` сравнивает строки лексикографически с использованием категории `LC_COLLATE` текущего языкового стандарта. Подробнее о категории `LC_COLLATE` см. в разделе [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 В языковом стандарте "C" порядок символов в наборе символов (набор символов ASCII) совпадает с лексикографическим порядком символов. Однако в других языковых стандартах порядок символов в наборе символов может отличаться от лексикографического порядка. Например, в некоторых европейских языковых стандартах символ a (значение 0x61) предшествует символу ä (значение 0xE4) в наборе символов, но ä предшествует символу a лексикографически.  
  
 При использовании языковых стандартов, в которых порядок символов в кодировке и лексикографический порядок различаются, используйте `strcoll` вместо `strcmp` для лексикографического сравнения строк. Также можно использовать функцию `strxfrm` для исходных строк, а затем использовать функцию `strcmp` для результирующих строк.  
  
 Функции `strcmp` учитывают регистр. Функции `_stricmp`, `_wcsicmp` и `_mbsicmp` перед сравнением преобразуют строки в нижний регистр. Две строки, содержащие символы, которые расположены между Z и a в таблице ASCII ("[", "`\`", "]", "`^`", "`_`" и "```"), сравниваются по-разному в зависимости от их регистра. Например, две строки `"ABCDE"` и `"ABCD^"` сравниваются с одним результатом, если сравнение производится в нижнем регистре (`"abcde"` > `"abcd^"`), и с другим, если сравнение производится в верхнем регистре (`"ABCDE"` < `"ABCD^"`).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strcmp`|<string.h>|  
|`wcscmp`|<string.h> или <wchar.h>|  
|`_mbscmp`|\<mbstring.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_strcmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof (tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
```Output  
Compare strings:  
   The quick brown dog jumps over the lazy fox  
   The QUICK brown dog jumps over the lazy fox  
  
   strcmp:   String 1 is greater than string 2  
   _stricmp:  String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>См. также  
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [_memicmp, _memicmp_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)