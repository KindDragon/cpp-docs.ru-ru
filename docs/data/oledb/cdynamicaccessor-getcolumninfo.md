---
title: "CDynamicAccessor::GetColumnInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetColumnInfo
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- GetColumnInfo method
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9f311e9fc5330a68edba4fd5029e97b75033406
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorgetcolumninfo"></a>CDynamicAccessor::GetColumnInfo
Возвращает метаданные столбца, требуемые большинством объектов-получателей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetColumnInfo(IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `pRowset`  
 [in] Указатель на [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) интерфейса.  
  
 *pColumns*  
 [out] Указатель на область памяти, в которую возвращается число столбцов в наборе строк. Это число включает закладку для столбца, если таковой имеется.  
  
 *ppColumnInfo*  
 [out] Указатель на область памяти, в которую будет возвращен массив **DBCOLUMNINFO** структуры. В разделе «Структуры DBCOLUMNINFO» в [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) в *справочника программиста OLE DB*.  
  
 `ppStringsBuffer`  
 [out] Указатель на область памяти, в которую возвращается указатель памяти, для всех строковых значений (имена используются как в пределах *columnid* или *pwszName*) в одном блоке распределения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
## <a name="remarks"></a>Примечания  
 В разделе [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) в *Справочник программиста OLE DB* сведения о типах данных **DBORDINAL**, **DBCOLUMNINFO**, и **olechar, КОТОРЫЕ**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)