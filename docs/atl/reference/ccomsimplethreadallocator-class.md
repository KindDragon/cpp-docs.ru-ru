---
title: "Класс CComSimpleThreadAllocator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 04946d07bea39eb739c31a3254355d3527d2e9c3
ms.lasthandoff: 04/01/2017

---
# <a name="ccomsimplethreadallocator-class"></a>Класс CComSimpleThreadAllocator
Этот класс управляет выбора потока для класса `CComAutoThreadModule`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComSimpleThreadAllocator
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSimpleThreadAllocator::GetThread](#getthread)|Выбирает поток.|  
  
## <a name="remarks"></a>Примечания  
 `CComSimpleThreadAllocator`управляет выбором потока для [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread`просто выполняет циклический переход по каждому потоку и возвращает следующим в последовательности.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="getthread"></a>CComSimpleThreadAllocator::GetThread  
 Выбирает поток, указав следующий поток в последовательности.  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>Параметры  
 `pApt`  
 В реализации по умолчанию ATL не используется.  
  
 `nThreads`  
 Максимальное число потоков в модуле exe-файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число от нуля и ( `nThreads` - 1). Определяет один из потоков в модуле exe-файла.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить `GetThread` для предоставления другой метод выделения или использовать `pApt` параметра.  
  
 `GetThread`вызывается методом [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).  
  
## <a name="see-also"></a>См. также  
 [Класс CComApartment](../../atl/reference/ccomapartment-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
