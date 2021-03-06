---
title: "AtlTraceErrorRecords | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- AtlTraceErrorRecords function
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 024a4331b71b3414aa7d83f27ecaca4e5d2f11de
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="atltraceerrorrecords"></a>AtlTraceErrorRecords
Выводит записи об ошибке OLE DB сведения об устройстве дампа, если возвращается сообщение об ошибке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hErr`  
 [in] `HRESULT` Возвращенных функции-члена шаблона потребителя OLE DB.  
  
## <a name="remarks"></a>Примечания  
 Если `hErr` не `S_OK`, `AtlTraceErrorRecords` выводит записи об ошибке OLE DB сведения об устройстве дампа ( **отладки** вкладки в окне вывода или файл). Данные записи об ошибке, получаемое от поставщика, включает номер строки, источник, описание, файл справки, контекст и идентификатор GUID для каждой операции записи ошибки. `AtlTraceErrorRecords` выводит эти сведения только в отладочных построениях. В сборках выпуска это пустую заглушку, которая оптимизирована out.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [Класс CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)