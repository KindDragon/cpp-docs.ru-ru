---
title: "PROVIDER_COLUMN_ENTRY_TYPE_LENGTH | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH macro
ms.assetid: a60b1a8b-0903-4ff4-91ec-ed62126449fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cb7d5eb61674cc5db6af4af2df8ec0a06712ea1e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="providercolumnentrytypelength"></a>PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
Представляет отдельного столбца, поддерживаемых поставщиком.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(name  
, ordinal, dbtype, size, member )  
```  
  
#### <a name="parameters"></a>Параметры  
 *name*  
  
 [in] Имя столбца.  
  
 `ordinal`  
 [in] Номер столбца. Если столбец является столбцом закладки, номер столбца не должно быть 0.  
  
 `dbtype`  
 [in] Тип данных в [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
 `size`  
 [in] Длина столбца в байтах.  
  
 `member`  
 [in] Переменная члена в классе данных, в которой хранятся данные.  
  
## <a name="remarks"></a>Примечания  
 Аналогично [PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md) , но также позволяет указать тип данных столбца, а также размер.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)