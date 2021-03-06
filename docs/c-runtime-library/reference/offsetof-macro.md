---
title: "offsetof Macro | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
- offsetof
dev_langs:
- C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a70bb2823f29caf3f76224bfb91c3c9642bbdcf1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="offsetof-macro"></a>Макрос offsetof
Возвращает смещение члена относительно начала его родительской структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *structName*  
 Имя родительской структуры данных.  
  
 `memberName`  
 Имя члена в родительской структуре данных, для которого определяется смещение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `offsetof` возвращает смещение в байтах указанного члена относительно начала его родительской структуры данных. Для битовых полей оно будет неопределенным.  
  
## <a name="remarks"></a>Примечания  
 Макрос `offsetof` возвращает смещение `memberName` в байтах относительно начала структуры, указанной в *structName* как значение типа `size_t`. С помощью ключевого слова `struct` можно указывать типы.  
  
> [!NOTE]
>  Макрос `offsetof` не является функцией и не может быть описан с помощью прототипа C.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`offsetof`|\<stddef.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)