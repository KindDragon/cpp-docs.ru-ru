---
title: "Получение уведомлений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 50911440acbc7514b091a439d42bf73ee60353f9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="receiving-notifications"></a>Получение уведомлений
OLE DB предоставляет интерфейсы для получения уведомлений при возникновении событий. Они описаны в [уведомления объект OLE DB](https://msdn.microsoft.com/en-us/library/ms725406.aspx) в *Справочник программиста OLE DB*. Программа установки этих событий использует стандартный механизм COM точки подключения. Например, объект ATL, который хочет получить событий с помощью `IRowsetNotify` реализует `IRowsetNotify` интерфейс, добавив `IRowsetNotify` в списке производный класс и предоставляя его через **COM_INTERFACE_ENTRY** макрос.  
  
 `IRowsetNotify` имеется три метода, которые могут быть вызваны в различные моменты времени. Если вы хотите ответить только один из этих методов, можно использовать [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) класса, который возвращает **E_NOTIMPL** для методов, которые вас не интересуют.  
  
 При создании набора строк необходимо указать поставщику нужных объектов возвращаемого набора строк для поддержки **IConnectionPointContainer**, который необходим для настройки уведомлений.  
  
 Ниже показано, как открыть набор строк из объекта ATL и использовать `AtlAdvise` функции, чтобы настроить уведомления стока. `AtlAdvise` Возвращает объект cookie, который используется при вызове `AtlUnadvise`.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  

product.Open(session, _T("Products"), &propset);  
  

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)