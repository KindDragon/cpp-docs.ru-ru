---
title: "gets_s, _getws_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _getws_s
- gets_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getws_s
- gets_s
dev_langs:
- C++
helpviewer_keywords:
- getws_s function
- _getws_s function
- lines, getting
- streams, getting lines
- buffers, avoiding overruns
- buffer overruns
- buffers, buffer overruns
- gets_s function
- standard input, reading from
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1cc1437d826584b89c7c4d9bb513f99af122ca0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="getss-getwss"></a>gets_s, _getws_s
Получает строку из потока `stdin` . Это версии функций [gets, _getws](../../c-runtime-library/gets-getws.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *gets_s(   
   char *buffer,  
   size_t sizeInCharacters  
);  
wchar_t *_getws_s(   
   wchar_t *buffer,  
   size_t sizeInCharacters  
);  
template <size_t size>  
char *gets_s(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws_s(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `buffer`  
 Место хранения входной строки.  
  
 [in] `sizeInCharacters`  
 Размер буфера.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение `buffer` в случае успешного выполнения. Указатель `NULL` указывает на ошибку или конец файла. Используйте [ferror](../../c-runtime-library/reference/ferror.md) или [feof](../../c-runtime-library/reference/feof.md) для определения того, что именно произошло.  
  
## <a name="remarks"></a>Примечания  
 Функция `gets_s` считывает строку из стандартного потока ввода `stdin` и сохраняет ее в буфере `buffer`. Строка состоит из всех символов до первого символа новой строки ("\n"). Затем перед возвратом строки функция `gets_s` заменяет символ новой строки нуль-символом ("\0"). Напротив, функция `fgets_s` сохраняет символ новой строки.  
  
 Если первым считан символ конца файла, в начале `buffer` сохраняется нуль-символ и возвращается значение `NULL`.  
  
 `_getws` — это версия функции `gets_s` для расширенных символов; ее аргумент и возвращаемое значение являются строками расширенных символов.  
  
 Если `buffer` имеет значение `NULL` или `sizeInCharacters` меньше или равно нулю, а также если буфер слишком мал и не вмещает входную строку и завершающий нуль-символ, эти функции вызывают обработчик недопустимого параметра, как описывается в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `NULL` и устанавливают параметр errno в значение `ERANGE`.  
  
 В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_getts`|`gets_s`|`gets_s`|`_getws`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`gets_s`|\<stdio.h>|  
|`_getws`|\<stdio.h> или \<wchar.h>|  
  
Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, `stdin`, `stdout`, и `stderr`, необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).
  
## <a name="example"></a>Пример  
  
```  
// crt_gets_s.c  
// This program retrieves a string from the stdin and   
// prints the same string to the console.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char line[21]; // room for 20 chars + '\0'  
   gets_s( line, 20 );  
   printf( "The line entered was: %s\n", line );  
}  
```  
  
```Output  
  
Hello there!The line entered was: Hello there!  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [gets, _getws](../../c-runtime-library/gets-getws.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [puts, _putws](../../c-runtime-library/reference/puts-putws.md)