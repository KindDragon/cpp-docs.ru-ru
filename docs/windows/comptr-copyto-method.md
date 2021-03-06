---
title: "Метод ComPtr::CopyTo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1f47df584fb456c721c92823a87ca525beb052d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="comptrcopyto-method"></a>Метод ComPtr::CopyTo
Копирует текущий или указанный интерфейс, связанный с этим объектом ComPtr, в заданный указатель.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  
template<  
   typename U  
>  
  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
#### <a name="parameters"></a>Параметры  
 `U`  
 Имя типа.  
  
 `ptr`  
 После завершения операции представляет указатель на запрошенный интерфейс.  
  
 `riid`  
 Идентификатор интерфейса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения неявной операции QueryInterface.  
  
## <a name="remarks"></a>Примечания  
 Первая функция возвращает копию указателя на интерфейс, связанный с этим объектом ComPtr. Эта функция всегда возвращает значение S_OK.  
  
 Вторая функция выполняет операцию QueryInterface в интерфейсе, связанном с этим объектом ComPtr, для интерфейса, указанного в параметре `riid`.  
  
 Третья функция выполняет операцию QueryInterface в интерфейсе, связанном с этим объектом ComPtr, для базового интерфейса параметра `U`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)