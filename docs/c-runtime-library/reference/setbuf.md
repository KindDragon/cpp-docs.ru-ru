---
title: "setbuf | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- setbuf
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
- setbuf
dev_langs:
- C++
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73de6c601f6a01fca15e8270104e2d8148539a4c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="setbuf"></a>setbuf
Управляет буферизацией потока. Эта функция не рекомендуется; вместо нее используйте функцию [setvbuf](../../c-runtime-library/reference/setvbuf.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void setbuf(  
   FILE *stream,  
   char *buffer   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE` .  
  
 `buffer`  
 Выделенный пользователем буфер.  
  
## <a name="remarks"></a>Примечания  
 Функция `setbuf` управляет буферизацией для `stream`. Аргумент `stream` должен ссылаться на открытый файл, в котором не производились чтение и запись. Если аргумент `buffer` имеет значение `NULL`, поток не буферизуется. В противном случае буфер должен указывать на массив символов длиной `BUFSIZ`, где `BUFSIZ` — размер буфера, как определено в файле STDIO.H. Вместо буфера, по умолчанию выделенного системой для данного потока, для буферизации ввода-вывода используется указанный пользователем буфер. Поток `stderr` не буферизуется по умолчанию, но с помощью функции `setbuf` можно назначить буферы для потока `stderr`.  
  
 Функция `setbuf` заменена функцией [setvbuf](../../c-runtime-library/reference/setvbuf.md), которая является предпочтительной для нового кода. Функция `setbuf` сохранена для обеспечения совместимости с существующим кодом.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`setbuf`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_setbuf.c  
// compile with: /W3  
// This program first opens files named DATA1 and  
// DATA2. Then it uses setbuf to give DATA1 a user-assigned  
// buffer and to change DATA2 so that it has no buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[BUFSIZ];  
   FILE *stream1, *stream2;  
  
   fopen_s( &stream1, "data1", "a" );  
   fopen_s( &stream2, "data2", "w" );  
  
   if( (stream1 != NULL) && (stream2 != NULL) )  
   {  
      // "stream1" uses user-assigned buffer:  
      setbuf( stream1, buf ); // C4996  
      // Note: setbuf is deprecated; consider using setvbuf instead  
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );  
  
      // "stream2" is unbuffered  
      setbuf( stream2, NULL ); // C4996  
      printf( "stream2 buffering disabled\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
stream1 set to user-defined buffer at: 0012FCDC  
stream2 buffering disabled  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)