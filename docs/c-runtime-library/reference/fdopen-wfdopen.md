---
title: "_fdopen, _wfdopen | Документы Майкрософт"
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fdopen
- _wfdopen
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
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
dev_langs:
- C++
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2474c25d30415d48252a2621ae5f7e69e5fed4d3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="fdopen-wfdopen"></a>_fdopen, _wfdopen

Связывает поток с файлом, который ранее был открыт для низкоуровневого ввода-вывода.

## <a name="syntax"></a>Синтаксис

```c
FILE *_fdopen(
   int fd,
   const char *mode
);
FILE *_wfdopen(
   int fd,
   const wchar_t *mode
);
```

### <a name="parameters"></a>Параметры

*fd*  
Дескриптор открытого файла.

*mode*  
Тип доступа к файлу.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на открытый поток. Значение указателя null обозначает ошибку. Если возникает ошибка, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EBADF`, означающее недопустимый идентификатор файла, или в значение `EINVAL`, означающее, что параметр `mode` был пустым указателем.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

`_fdopen` Функция связывает поток ввода-вывода с файлом, который определяется параметром *fd*, таким образом файл, который открыт для низкоуровневого ввода-вывода возможность буферизации и форматирования. `_wfdopen` — это двухбайтовая версия `_fdopen`; *режим* аргумент `_wfdopen` представляет собой строку расширенных символов. В остальных отношениях поведение функций `_wfdopen` и `_fdopen` идентично.

Переданные дескрипторов файлов `_fdopen` принадлежат возвращаемым `FILE *` потока. Если `_fdopen` прошла успешно, не следует вызывать [ \_закрыть](../../c-runtime-library/reference/close.md) на дескриптор файла. Вызов [fclose](../../c-runtime-library/reference/fclose-fcloseall.md) в возвращенном `FILE *` также закрывает дескриптор файла.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|\_Юникод и \_MBCS не определены|\_Определенные многобайтовой Кодировки|\_Определенные ЮНИКОДА|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_tfdopen`|`_fdopen`|`_fdopen`|`_wfdopen`|

*Режим* символьная строка указывает тип доступа к файлам, запрошенный для файла:  

`"r"`  
Открывает для чтения. Если файл не существует или его невозможно найти, вызов `fopen` завершается ошибкой.

`"w"`  
Открывает пустой файл для записи. Если указанный файл существует, его содержимое удаляется.

`"a"`  
Открывает для записи, в конце файла (добавление). Создает файл, если он не существует.

`"r+"`  
Открывает для чтения и записи. (Файл должен существовать.)

`"w+"`  
Открывает пустой файл для чтения и записи. Если указанный файл существует, его содержимое удаляется.

`"a+"`  
Открывается для чтения и добавления. Создает файл, если он не существует.

Если файл открыт с помощью типа доступа `"a"` или `"a+"`, все операции записи выполняются в конце файла. Указатель файла можно перемещать с помощью функции `fseek` или `rewind`, но он всегда возвращается в конец файла перед выполнением любой операции записи. Поэтому перезаписать существующие данные невозможно. Если задан тип доступа `"r+"`, `"w+"` или `"a+"`, чтение и запись разрешены (считается, что файл открыт для "обновления"). Однако при переключении между чтением и записью должны быть промежуточные операции `fflush`, `fsetpos`, `fseek` или `rewind`. Если требуется, можно указать текущую позицию для операции `fsetpos` или `fseek`.

Помимо вышеуказанных значений следующих символов также может быть включено в *режим* Чтобы задать режим перевода для символов новой строки:

`t`  
Откройте файл в текстовом (переведенном) режиме. В этом режиме сочетания символов возврата каретки и перевода строки (CR-LF) преобразуются в один символ перевода строки (LF) на входе, а символы перевода строки (LF) преобразуются на выходе в сочетания символов возврата каретки и перевода строки (CR-LF). Кроме того, на входе Ctrl+Z интерпретируется как символ конца файла. В файлах, открытых для чтения или записи, функция `fopen` проверяет наличие CTRL+Z в конце файла и удаляет его, если это возможно. Это делается потому, что использование функций `fseek` и `ftell` для перемещения в файле, который заканчивается CTRL+Z, может вызвать неправильное поведение функции `fseek` вблизи конца файла.

`b`  
Открыть в двоичном (непреобразованном) режиме. Все преобразования из режима `t` отключены.

`c`  
Включите флажок фиксации для связанного объекта `filename` , чтобы содержимое файлового буфера записывалось непосредственно на диск при вызове `fflush` или `_flushall` .

`n`  
Сбросьте флажок фиксации для связанного объекта `filename` , задайте для него значение "без фиксации". Это значение по умолчанию. Оно также переопределяет глобальный флаг фиксации при компоновке программы с COMMODE.OBJ. Значение по умолчанию глобального флага фиксации — "без фиксации", если только программа не скомпонована явно с файлом COMMODE.OBJ.

`t`, `c`, И `n` *режим* представляют собой расширения Microsoft для `fopen` и `_fdopen`. Не используйте их, если нужно сохранить совместимость с ANSI.

Если `t` или `b` не указаны в параметре *режим*, режим преобразования по умолчанию определяется глобальной переменной [ \_fmode](../../c-runtime-library/fmode.md). Если `t` или `b` указан как префикс аргумента, функция завершается с ошибкой и возвращает значение NULL. Обсуждение текстового и двоичного режимов см. в разделе [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Допустимые символы для *режим* строку, используемую в `fopen` и `_fdopen` соответствуют *oflag* аргументы, используемые в [ \_откройте](../../c-runtime-library/reference/open-wopen.md) и [ \_sopen](../../c-runtime-library/reference/sopen-wsopen.md), как показано в следующей таблице:

|Символы в *режим* строки|Эквивалентный *oflag* значение для `_open` и `_sopen`|
|---------------------------------|---------------------------------------------------|
|`a`|**\_O\_WRONLY &#124; \_O\_APPEND** (обычно  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O\_APPEND**)|
|`a+`|**\_O\_RDWR &#124; \_O\_APPEND** (обычно  **\_O\_RDWR &#124; \_O\_APPEND &#124; \_O\_CREAT** )|
|`r`|**\_O\_: RDONLY**|
|`r+`|**\_O\_RDWR**|
|`w`|**\_O\_WRONLY** (обычно  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|`w+`|**\_O\_RDWR** (обычно  **\_O\_RDWR &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|`b`|**\_O\_ДВОИЧНЫЕ**|
|`t`|**\_O\_TEXT**|
|`c`|Нет|
|`n`|Нет|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|`_fdopen`|\<stdio.h>|
|`_wfdopen`|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```c
// crt_fdopen.c
// This program opens a file by using low-level
// I/O, then uses _fdopen to switch to stream
// access. It counts the lines in the file.

#include <stdlib.h>
#include <stdio.h>
#include <fcntl.h>
#include <io.h>
#include <share.h>

int main( void )
{
   FILE *stream;
   int  fd, count = 0;
   char inbuf[128];

   // Open a file.
   if( _sopen_s( &fd, "crt_fdopen.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
      exit( 1 );

   // Get stream from file descriptor.
   if( (stream = _fdopen( fd, "r" )) == NULL )
      exit( 1 );

   while( fgets( inbuf, 128, stream ) != NULL )
      count++;

   // After _fdopen, close by using fclose, not _close.
   fclose( stream );
   printf( "Lines in file: %d\n", count );
}
```

### <a name="input-crtfdopentxt"></a>Входные данные: crt_fdopen.txt

```
Line one
Line two
```

### <a name="output"></a>Вывод

```
Lines in file: 2
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
[\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
[fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
[fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
[freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
[\_открыть, \_wopen](../../c-runtime-library/reference/open-wopen.md)
