---
title: "_expand | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _expand
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6b2bf8ba3e30165f11e3392e04519a3d49cfd4a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="expand"></a>_expand
Изменяет размер блока памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_expand(   
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `memblock`  
 Указатель на ранее выделенный блок памяти.  
  
 `size`  
 Новый размер в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `_expand` возвращает указатель на перераспределенный блок памяти. Функция `_expand`, в отличие от функции `realloc`, не может перемещать блок, чтобы изменить его размер. Таким образом, если доступно достаточно памяти, чтобы увеличить блок без его перемещения, параметр `memblock` в функции `_expand` совпадает с возвращаемым значением.  
  
 При обнаружении ошибки во время работы функции `_expand` она возвращает значение `NULL`. Например, если функция `_expand` используется, чтобы сжать блок памяти, она может обнаружить повреждение в куче с малыми блоками или недопустимый указатель блока и вернуть значение `NULL`.  
  
 Если памяти недостаточно для увеличения блока до заданного размера без его перемещения, функция возвращает значение `NULL`. Функция `_expand` никогда не возвращает блок, увеличенный до меньшего размера, чем было запрошено. Если происходит сбой, параметр `errno` указывает характер ошибки. Дополнительные сведения о функции `errno` см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы проверить новый размер элемента, используйте функцию `_msize`. Чтобы получить указатель на тип, отличный от `void`, используйте приведение типов для возвращаемого значения.  
  
## <a name="remarks"></a>Примечания  
 Функция `_expand` изменяет размер блока ранее выделенного блока памяти, пытаясь увеличить или уменьшить блок без его перемещения в куче. Параметр `memblock` указывает на начало блока. Параметр `size` указывает новый размер блока в байтах. Содержимое блока в пределах наименьшего из нового и старого размеров остается неизменным. Параметр `memblock` не должен быть освобожденным блоком.  
  
> [!NOTE]
>  На 64-разрядных платформах функция `_expand` может не изменить блок, если новый размер меньше, чем текущий размер; в частности, если размер блока был меньше 16 КБ и, следовательно, блок был размещен в куче низкой фрагментации, функция `_expand` оставляет блок без изменений и возвращает `memblock`.  
  
 Когда приложение связано с отладочной версией библиотек времени выполнения языка C, функция `_expand` соответствует функции [_expand_dbg](../../c-runtime-library/reference/expand-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Эта функция проверяет свои параметры. Если `memblock` является пустым указателем, эта функция вызывает обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL` , и функция возвращает значение `NULL`. Если значение параметра `size` превышает значение `_HEAP_MAXREQ`, для параметра `errno` задается значение `ENOMEM` и функция возвращает `NULL`.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_expand`|\<malloc.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_expand.c  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char *bufchar;  
   printf( "Allocate a 512 element buffer\n" );  
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )  
      exit( 1 );  
   printf( "Allocated %d bytes at %Fp\n",   
         _msize( bufchar ), (void *)bufchar );  
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )  
      printf( "Can't expand" );  
   else  
      printf( "Expanded block to %d bytes at %Fp\n",   
            _msize( bufchar ), (void *)bufchar );  
   // Free memory   
   free( bufchar );  
   exit( 0 );  
}  
```  
  
```Output  
Allocate a 512 element buffer  
Allocated 512 bytes at 002C12BC  
Expanded block to 1024 bytes at 002C12BC  
```  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_msize](../../c-runtime-library/reference/msize.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)