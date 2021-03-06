---
title: "IGetDataSourceImpl::GetDataSource | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
dev_langs:
- C++
helpviewer_keywords:
- GetDataSource method
ms.assetid: b70995d2-b951-452e-a2d4-fb3eb085886e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a30f2030dc6a1e45836d0a50aebf7a722f950bf3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="igetdatasourceimplgetdatasource"></a>IGetDataSourceImpl::GetDataSource
Возвращает указатель интерфейса на объект источника данных, для которого был создан сеанс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(GetDataSource)(REFIID riid,   
   IUnknown ** ppDataSource);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IGetDataSource::GetDataSource](https://msdn.microsoft.com/en-us/library/ms725443.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Полезно, если необходимо получить доступ к свойствам в объекте источника данных.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)