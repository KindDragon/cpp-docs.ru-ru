---
title: "CUtlProps::SetPropValue | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
dev_langs:
- C++
helpviewer_keywords:
- SetPropValue method
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cd54b1483d43578bad63afff6eeab74d536ae133
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cutlpropssetpropvalue"></a>CUtlProps::SetPropValue
Задает свойство в наборе свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pguidPropSet`  
 [in] Идентификатор GUID набор свойств.  
  
 `dwPropId`  
 [in] Индекс свойства.  
  
 `pvValue`  
 [in] Указатель на значение variant, который содержит новое значение свойства.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `Failure` в случае ошибки и `S_OK` в случае успешного выполнения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс CUtlProps](../../data/oledb/cutlprops-class.md)