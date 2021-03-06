---
title: "Класс HStringReference | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
dev_langs:
- C++
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97900bd44dfdcede187b20b181c64d235eac60fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreference-class"></a>Класс HStringReference
Представляет HSTRING, созданной из существующей строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class HStringReference;  
```  
  
## <a name="remarks"></a>Примечания  
 Время существования резервный буфер в новый HSTRING не управляется средой выполнения Windows. Вызывающий объект выделяет строку источника, чтобы избежать выделения кучи и избежать утечки памяти в стеке. Кроме того вызывающий объект должен убедиться, исходная строка остается неизменным в течение времени существования вложенного HSTRING. Дополнительные сведения см. в разделе [WindowsCreateStringReference функция](http://msdn.microsoft.com/en-us/0361bb7e-da49-4289-a93e-de7aab8712ac).  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор HStringReference::HStringReference](../windows/hstringreference-hstringreference-constructor.md)|Инициализирует новый экземпляр класса HStringReference.|  
  
### <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|[Метод HStringReference::CopyTo](../windows/hstringreference-copyto-method.md)|Копирует текущий HStringReference объект к объекту HSTRING.|  
|[Метод HStringReference::Get](../windows/hstringreference-get-method.md)|Возвращает значение базового дескриптора HSTRING.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Оператор HStringReference::Operator=](../windows/hstringreference-operator-assign-operator.md)|Значение другой объект HStringReference перемещается в текущий объект HStringReference.|  
|[Оператор HStringReference::Operator==](../windows/hstringreference-operator-equality-operator.md)|Указывает, равны ли два параметра.|  
|[Оператор HStringReference::Operator!=](../windows/hstringreference-operator-inequality-operator.md)|Указывает, равны ли два параметра.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HStringReference`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)