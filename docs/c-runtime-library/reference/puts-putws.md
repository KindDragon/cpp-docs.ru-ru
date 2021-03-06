---
title: "puts, _putws | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _putws
- puts
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
- _putts
- _putws
- puts
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], writing
- _putts function
- standard output, writing to
- putws function
- puts function
- putts function
- _putws function
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 06f90cf85d19fab3dd08b8b0c3d789d263c55fbf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="puts-putws"></a>puts, _putws
Записывает строку в поток **stdout**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int puts(  
   const char *str   
);  
int _putws(  
   const wchar_t *str   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `str`  
 Выходная строка.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает неотрицательное значение в случае успешного выполнения. Если функция `puts` завершается с ошибкой, она возвращает `EOF`; если функция `_putws` завершается с ошибкой, она возвращает **WEOF**. Если параметр `str` является пустым указателем, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции задают для `errno` значение `EINVAL` и возвращают `EOF` или **WEOF**.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `puts` записывает `str` в стандартный поток вывода **stdout**, заменяя завершающий строку нуль-символ ("\0") на символ новой строки ("\n") в потоке вывода.  
  
 Функция `_putws` является версией функции `puts` с расширенными символами; обе функции ведут себя одинаково, если поток открыт в режиме ANSI. Функция `puts` на данный момент не поддерживает вывод данных в поток в кодировке Юникод.  
  
  **_putwch** записывает знаки Юникода, используя текущий параметр языкового СТАНДАРТА КОНСОЛИ.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_putts`|`puts`|`puts`|`_putws`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`puts`|\<stdio.h>|  
|`_putws`|\<stdio.h>|  
  
Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, `stdin`, `stdout`, и `stderr`, необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_puts.c  
/* This program uses puts to write a string to stdout.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   puts( "Hello world from puts!" );  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
Hello world from puts!  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)