---
title: "Класс IOpenRowsetImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOpenRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IOpenRowsetImpl class
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 67f457b4a56d57f33a18473e987fa00b6c10b0df
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="iopenrowsetimpl-class"></a>Класс IOpenRowsetImpl
Предоставляет реализацию для `IOpenRowset` интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### <a name="parameters"></a>Параметры  
 `SessionClass`  
 Класс, производный от `IOpenRowsetImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|Создает объект набора строк. Не вызывается непосредственно пользователем.|  
|[OpenRowset](../../data/oledb/iopenrowsetimpl-openrowset.md)|Открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса. (Не в ATLDB. H)|  
  
## <a name="remarks"></a>Примечания  
 [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx) интерфейса является обязательным для объекта сеанса. Он открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)