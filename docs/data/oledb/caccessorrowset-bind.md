---
title: "CAccessorRowset::Bind | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccessorRowset.Bind
- CAccessorRowset::Bind
dev_langs:
- C++
helpviewer_keywords:
- Bind method
ms.assetid: 42a1fc86-f570-4e54-9b82-7f7141564214
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 778f8afabbe845c382782ea15e3e47f8736d07fa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="caccessorrowsetbind"></a>CAccessorRowset::Bind
Создает привязку, если указана **bBind** как false в [CCommand::Open](../../data/oledb/ccommand-open.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Bind();  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CAccessorRowset](../../data/oledb/caccessorrowset-class.md)