---
title: "CDataConnection::operator CSession&amp; | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
dev_langs:
- C++
helpviewer_keywords:
- operator CSession&
- CSession& operator
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 53355a04217451594eb9ce22c4233d1c70333ea4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectionoperator-csessionamp"></a>CDataConnection::operator CSession&amp;
Возвращает ссылку на содержащиеся в нем `CSession` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
operator const CSession&();  
  
```  
  
## <a name="remarks"></a>Примечания  
 Этот оператор возвращает ссылку на содержащиеся в нем `CSession` объекта, что позволяет передавать `CDataConnection` объекта где `CSession` ожидается ссылка.  
  
## <a name="example"></a>Пример  
 При наличии функции (такие как `func` ниже), который принимает `CSession` ссылки, можно использовать **CSession &** для передачи `CDataConnection` вместо этого объекта.  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDataConnection-класс](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession*](../../data/oledb/cdataconnection-operator-csession-star.md)