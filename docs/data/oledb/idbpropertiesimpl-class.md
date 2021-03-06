---
title: "Класс IDBPropertiesImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBPropertiesImpl class
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e1b1486d5eff73b4f868f5990ceb628cfb7dd20a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="idbpropertiesimpl-class"></a>Класс IDBPropertiesImpl
Предоставляет реализацию для `IDBProperties` интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IDBPropertiesImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|Возвращает значения свойств источника данных, источника данных и инициализации свойства групп, заданных в настоящее время на объекте источника данных или значений свойств в группу свойств инициализации, заданных в настоящее время на перечислитель.|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|Возвращает сведения обо всех свойствах, поддерживаемых поставщиком.|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|Устанавливает свойства на источник данных и инициализации группы свойств, для объектов источников данных, или группу свойств инициализации для перечислителей.|  
  
## <a name="remarks"></a>Примечания  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) обязательный интерфейс для объектов источников данных и дополнительный интерфейс для перечислителей. Тем не менее если перечислитель предоставляет [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx), он должен предоставлять `IDBProperties`. `IDBPropertiesImpl` реализует `IDBProperties` с помощью статической функции определяется [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)