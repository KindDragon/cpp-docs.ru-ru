---
title: "Класс allocator_suballoc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- allocators/stdext::allocators::allocator_suballoc
- allocators/stdext::allocator_suballoc
dev_langs:
- C++
helpviewer_keywords:
- allocator_suballoc class
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1ded5189cc96c77a397f4589a696a1b3b767093c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="allocatorsuballoc-class"></a>Класс allocator_suballoc
Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_suballoc](../standard-library/cache-suballoc-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Type>  
class allocator_suballoc;
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`Type`|Тип элементов, распределяемых распределителем.|  
  
## <a name="remarks"></a>Примечания  
 Макрос [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) передает этот класс как параметр `name` в следующей инструкции: `ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)



