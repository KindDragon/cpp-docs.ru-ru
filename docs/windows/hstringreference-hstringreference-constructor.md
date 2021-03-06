---
title: "Конструктор HStringReference::HStringReference | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
dev_langs:
- C++
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 398ea9403f784c30f8e015101c25b071f1d6fb29
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreferencehstringreference-constructor"></a>Конструктор HStringReference::HStringReference
Инициализирует новый экземпляр класса HStringReference.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest],   
                 unsigned int len) throw();  
  
HStringReference(HStringReference&& other) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `sizeDest`  
 Параметр шаблона, задающее размер буфера назначения HStringReference.  
  
 `str`  
 Ссылка на строку расширенных символов.  
  
 `len`  
 Максимальная длина `str` буфером параметров для использования в этой операции. Если `len` параметр не указан, вся `str` параметр используется. Если параметр `len` больше, чем параметр `sizeDest`, значит для `len` установлено значение `sizeDest`-1.  
  
 `other`  
 Другой объект HStringReference.  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует новый объект HStringReference того же размера, что и параметр `str`.  
  
 Второй конструктор инициализирует новый объект HStringReference, размер которого определен параметром `len`.  
  
 Третий конструктор инициализирует новый объект HStringReference значению `other` параметра, а затем удаляет `other` параметра.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)