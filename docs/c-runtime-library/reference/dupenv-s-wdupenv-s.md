---
title: "_dupenv_s, _wdupenv_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_dupenv_s"
  - "_wdupenv_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "tdupenv_s"
  - "_dupenv_s"
  - "wdupenv_s"
  - "dupenv_s"
  - "_tdupenv_s"
  - "_wdupenv_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_dupenv_s - функция"
  - "_tdupenv_s - функция"
  - "_wdupenv_s - функция"
  - "dupenv_s - функция"
  - "переменные среды"
  - "tdupenv_s - функция"
  - "wdupenv_s - функция"
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _dupenv_s, _wdupenv_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает значение из текущей среды.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows.  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
errno_t _dupenv_s(    char **buffer,    size_t *numberOfElements,    const char *varname ); errno_t _wdupenv_s(    wchar_t **buffer,    size_t *numberOfElements,    const wchar_t *varname );  
```  
  
#### Параметры  
 `buffer`  
 Буфер для хранения значения переменной.  
  
 `numberOfElements`  
 Размер `buffer`.  
  
 `varname`  
 Имя переменной среды.  
  
## Возвращаемое значение  
 Нуль при успешном выполнении, код ошибки при сбое.  
  
 Эти функции проверяют свои параметры. Если `buffer` или `varname` имеют значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функции задают для `errno` значение `EINVAL` и возвращают `EINVAL`.  
  
 Если этим функциям не удается выделить достаточно памяти, они задают для параметра `buffer` значение `NULL`, а для `numberOfElements` значение 0 и возвращают `ENOMEM`.  
  
## Заметки  
 Функция `_dupenv_s` выполняет поиск в списке переменных среды для `varname`.  Если переменная найдена, `_dupenv_s` выделяет буфер и копирует значение переменной в буфер.  Адрес и длина буфера возвращаются в `buffer` и `numberOfElements`.  Выделяя собственно буфер, `_dupenv_s` обеспечивает более удобную альтернативу [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
> [!NOTE]
>  Ответственность за освобождение памяти путем вызова функции [free](../../c-runtime-library/reference/free.md) лежит на вызывающей программе.  
  
 Если переменная не найдена, для `buffer` задается значение `NULL`, для `numberOfElements` — 0, и возвращаемое значение равно 0, так как эта ситуация не считается условием ошибки.  
  
 Если вас не интересует размер буфера, можно передать значение `NULL` для `numberOfElements`.  
  
 `_dupenv_s` не учитывает регистр в операционной системе Windows.  `_dupenv_s` для получения доступа к среде использует копию среды, на которую указывает глобальная переменная `_environ`.  Дополнительные сведения о функции `_environ` см. в подразделе примечаний раздела [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
 Значение параметра `buffer` является копией значения переменной среды; его изменение не влияет на среду.  Чтобы изменить значение переменной среды, используйте функцию [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md).  
  
 `_wdupenv_s` — это версия `_dupenv_s` с расширенными символами; аргументы для `_wdupenv_s` — это строки расширенных символов.  Глобальная переменная `_wenviron` — это версия `_environ` с расширенными символами.  Дополнительные сведения о функции `_wenviron` см. в подразделе примечаний раздела [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tdupenv_s`|`_dupenv_s`|`_dupenv_s`|`_wdupenv_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_dupenv_s`|\<stdlib.h\>|  
|`_wdupenv_s`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_dupenv_s.c  
#include  <stdlib.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## Пример результатов выполнения  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## Эквивалент в .NET Framework  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Константы среды](../../c-runtime-library/environmental-constants.md)   
 [\_dupenv\_s\_dbg, \_wdupenv\_s\_dbg](../../c-runtime-library/reference/dupenv-s-dbg-wdupenv-s-dbg.md)   
 [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)