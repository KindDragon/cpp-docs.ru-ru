---
title: "_spawnle, _wspawnle | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _spawnle
- _wspawnle
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- spawnle
- _spawnle
- wspawnle
- _wspawnle
dev_langs:
- C++
helpviewer_keywords:
- spawnle function
- processes, creating
- _wspawnle function
- processes, executing new
- process creation
- wspawnle function
- _spawnle function
ms.assetid: 80308892-2815-49b1-8cca-53894c366f5a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 877ec03e7aa5678078031f7e29190f0d92dc6b27
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="spawnle-wspawnle"></a>_spawnle, _wspawnle
Создает и выполняет новый процесс.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
intptr_t _spawnle(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wspawnle(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mode`  
 Режим выполнения для вызывающего процесса.  
  
 `cmdname`  
 Путь к выполняемому файлу.  
  
 `arg0, arg1, ... argn`  
 Список указателей на аргументы. Аргумент `arg0` обычно является указателем на параметр `cmdname`. Аргументы `arg1` – `argn` являются указателями на строки символов, которые образуют новый список аргументов. После `argn`должно следовать указатель `NULL` , отмечающий конец списка аргументов.  
  
 `envp`  
 Массив указателей на параметры среды.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение синхронных функций `_spawnle` или `_wspawnle` (для параметра `_P_WAIT` указано значение `mode`) — это состояние завершения нового процесса. Возвращаемое значение асинхронной функции `_spawnle` или `_wspawnle` (для параметра`_P_NOWAIT` указано значение `_P_NOWAITO` или `mode`) — это дескриптор процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Для состояния выхода можно задать ненулевое значение, если порожденный процесс специально вызывает процедуру `exit` с ненулевым аргументом. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение-1 указывает на ошибку (новый процесс не запущен). В этом случае `errno` имеет одно из следующих значений.  
  
 `E2BIG`  
 Длина списка аргументов превышает 1024 байта.  
  
 `EINVAL`  
 Недопустимый аргумент `mode`.  
  
 `ENOENT`  
 Файл или путь не найден.  
  
 `ENOEXEC`  
 Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.  
  
 `ENOMEM`  
 Недостаточно памяти для выполнения нового процесса.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций создает и выполняет новый процесс и передает каждый аргумент командной строки как отдельный параметр, а также передает массив указателей на параметры среды.  
  
 Эти функции проверяют свои параметры. Если параметр `cmdname` или `arg0` является пустой строкой или пустым указателем, вызывается обработчик недопустимых параметров, как описано в статье [Parameter Validation](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL`и возвращают -1. Нет порожденных новых процессов.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_spawnle`|\<process.h>|  
|`_wspawnle`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 См. пример в разделе [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)