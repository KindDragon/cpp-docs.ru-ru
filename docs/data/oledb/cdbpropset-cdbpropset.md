---
title: "CDBPropSet::CDBPropSet | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class, constructor
ms.assetid: 02ae5d9e-c067-47ca-8111-a03e86b5626b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: db118c9c814d957c43f11414ee583a2ccc7a416b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cdbpropsetcdbpropset"></a>CDBPropSet::CDBPropSet
Конструктор. Инициализирует **rgProperties**, **cProperties**, и **guidPropertySet** поля [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      CDBPropSet(const GUID& guid);  

CDBPropSet(const CDBPropSet& propset);  

CDBPropSet();  
```  
  
#### <a name="parameters"></a>Параметры  
 `guid`  
 [in] Идентификатор GUID, используемый для инициализации **guidPropertySet** поля.  
  
 *propset*  
 [in] Другой `CDBPropSet` объект для создания копии.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDBPropSet-класс](../../data/oledb/cdbpropset-class.md)   
 [CDBPropSet::SetGUID](../../data/oledb/cdbpropset-setguid.md)   
 [Структуры DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx)