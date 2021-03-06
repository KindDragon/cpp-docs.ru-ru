---
title: "rename, _wrename | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- rename
- _wrename
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wrename
- _trename
- Rename
dev_langs:
- C++
helpviewer_keywords:
- trename function
- directories [C++], renaming
- renaming directories
- names [C++], changing file
- _trename function
- rename function
- wrename function
- files [C++], renaming
- _wrename function
- names [C++], changing directory
- renaming files
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34da3f704f3350a9fbd8750c940cdc4e847cfb40
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="rename-wrename"></a>rename, _wrename
Переименовывает файл или каталог.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int rename(  
   const char *oldname,  
   const char *newname   
);  
int _wrename(  
   const wchar_t *oldname,  
   const wchar_t *newname   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *oldname*  
 Указатель на старое имя.  
  
 *newname*  
 Указатель на новое имя.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций при успешном выполнении возвращает 0. При возникновении ошибки функция возвращает ненулевое значение и задает для `errno` одно из следующих значений:  
  
 `EACCES`  
 Файл или каталог, указанный в *newname*, уже существует, либо его не удалось создать (недопустимый путь); или *oldname* является каталогом, а *newname* указывает другой путь.  
  
 `ENOENT`  
 Файл или путь, указанный в *oldname*, не найден.  
  
 `EINVAL`  
 Имя содержит недопустимые символы.  
  
 Другие возможные возвращаемые значения см. в разделе [_doserrno, _errno, syserrlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция **rename** переименовывает файл или каталог, указанный в *oldname* и присваивает имя, заданное в *newname*. Старое имя должно быть путем к существующему файлу или каталогу. Новое имя не должно быть путем к существующему файлу или каталогу. Можно использовать функцию **rename** для перемещения файла из одного каталога или с одного устройства на другое, указав другой путь в аргументе *newname*. Однако нельзя использовать функцию **rename** для перемещения каталога. Каталоги можно переименовать, но нельзя перемещать.  
  
 `_wrename` — это версия функции **_rename** для расширенных символов; аргументы для функции `_wrename` представляют собой строки расширенных символов. Поведение `_wrename` и **_rename** идентично в противном случае.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_trename`|**rename**|**rename**|`_wrename`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|**rename**|\<io.h> или \<stdio.h>|  
|`_wrename`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_renamer.c  
/* This program attempts to rename a file named  
 * CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation  
 * to succeed, a file named CRT_RENAMER.OBJ must exist and  
 * a file named CRT_RENAMER.JBO must not exist.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int  result;  
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";  
  
   /* Attempt to rename file: */  
   result = rename( old, new );  
   if( result != 0 )  
      printf( "Could not rename '%s'\n", old );  
   else  
      printf( "File '%s' renamed to '%s'\n", old, new );  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)