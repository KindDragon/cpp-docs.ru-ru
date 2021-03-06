---
title: "set_terminate (CRT) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- set_terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_terminate
dev_langs:
- C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eba062bd1b791f055b2ae1c74c2a0107a4039d23
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="setterminate-crt"></a>set_terminate (CRT)
Устанавливает вашу собственную подпрограмму завершения, чтобы ее можно было вызвать с помощью функции `terminate`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `termFunction`  
 Указатель на пользовательскую функцию завершения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на предыдущую функцию, зарегистрированную с помощью функции `set_terminate`, чтобы предыдущую функцию можно было впоследствии восстановить. Если предыдущая функция не задана, возвращаемое значение может использоваться для восстановления поведения по умолчанию; это значение может быть равно NULL.  
  
## <a name="remarks"></a>Примечания  
 Функция `set_terminate` устанавливает `termFunction` как функцию, вызываемую функцией `terminate`. Функция `set_terminate` используется с обработкой исключений C++ и может быть вызвана в программе в любой момент до возникновения исключения. По умолчанию `terminate` вызывает функцию `abort`. Это поведение по умолчанию можно изменить, создав собственную функцию завершения и вызвав функцию `set_terminate` с именем этой функции в качестве аргумента. `terminate` вызывает последнюю функцию, заданную в качестве аргумента для функции `set_terminate`. После выполнения всех необходимых задач очистки функция `termFunction` должна завершить программу. Если она не завершает программу (если она возвращает управление вызывавшему ее объекту), вызывается функция `abort`.  
  
 В многопоточной среде функции завершения поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной функции завершения. Таким образом, каждый поток отвечает за собственную обработку завершения.  
  
 Тип `terminate_function` определен в файле EH.H как указатель на определенную пользователем функцию завершения, `termFunction`, возвращающую значение `void`. Пользовательская функция `termFunction` может не иметь аргументов и не должна возвращать управление вызвавшему ее объекту. В противном случае вызывается функция `abort`. Создание исключения из функции `termFunction` невозможно.  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  Функция `set_terminate` работает только вне отладчика.  
  
 Существует только один обработчик `set_terminate` для всех динамически связанных файлов DLL или EXE; даже если вы вызвали функцию `set_terminate`, ваш обработчик может быть заменен другим или вы можете заменить обработчик, заданный другими файлами DLL или EXE.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`set_terminate`|\<eh.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для функции [terminate](../../c-runtime-library/reference/terminate-crt.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)