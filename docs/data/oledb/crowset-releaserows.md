---
title: "CRowset::ReleaseRows | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ReleaseRows
- CRowset::ReleaseRows
- ATL::CRowset<TAccessor>::ReleaseRows
- CRowset<TAccessor>.ReleaseRows
- CRowset.ReleaseRows
- ATL.CRowset.ReleaseRows
- ATL.CRowset<TAccessor>.ReleaseRows
- CRowset<TAccessor>::ReleaseRows
- ATL::CRowset::ReleaseRows
dev_langs:
- C++
helpviewer_keywords:
- ReleaseRows method
ms.assetid: fa7254f5-566f-4754-bdf7-d0874256926f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 000fa9fe18e3d9d7168d430d5a9843acc55696fb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetreleaserows"></a>CRowset::ReleaseRows
Вызовы [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) для освобождения дескриптора текущей строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT ReleaseRows() throw();  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowset](../../data/oledb/crowset-class.md)