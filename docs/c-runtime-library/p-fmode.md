---
title: "__p__fmode | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __p__fmode
apilocation:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- __p__fmode
dev_langs:
- C++
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 341eab038db17b39e5b2a408db7c61c69d432fe9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="pfmode"></a>__p__fmode
Указывает на глобальную переменную `_fmode`, которая определяет значение *режима трансляции файлов* по умолчанию для операций ввода-вывода файлов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
int* __p__fmode(  
   );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на глобальную переменную `_fmode`.  
  
## <a name="remarks"></a>Примечания  
 Функция `__p__fmode` предназначена только для внутреннего пользования и не должна вызываться из кода пользователя.  
  
 Режим трансляции файлов определяет трансляцию `binary` или `text` для операций ввода-вывода [_open](../c-runtime-library/reference/open-wopen.md) и [_pipe](../c-runtime-library/reference/pipe.md). Дополнительные сведения см. в разделе [_fmode](../c-runtime-library/fmode.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|__p\__fmode|stdlib.h|