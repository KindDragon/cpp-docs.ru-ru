---
title: "Класс CSession | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
dev_langs:
- C++
helpviewer_keywords:
- CSession class
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a5f2a764aaa7e10b957955dc11ee35ee44f9472
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="csession-class"></a>класс CSession
Представляет сеанс доступа к одной базе данных.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CSession  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Прерывание](../../data/oledb/csession-abort.md)|Отменяет (прекращает) транзакции.|  
|[Закрыть](../../data/oledb/csession-close.md)|Завершает сеанс.|  
|[Фиксация](../../data/oledb/csession-commit.md)|Завершает транзакцию.|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|Возвращает сведения, касающиеся транзакции.|  
|[Открыть](../../data/oledb/csession-open.md)|Открывает новый сеанс для объекта источника данных.|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|Начинает новую транзакцию для этого сеанса.|  
  
## <a name="remarks"></a>Примечания  
 Один или несколько сеансов можно связать с каждой подключения поставщика (источник данных), который представляется [CDataSource](../../data/oledb/cdatasource-class.md) объекта. Чтобы создать новую `CSession` для `CDataSource`, вызовите [CSession::Open](../../data/oledb/csession-open.md). Чтобы начать транзакцию базы данных `CSession` предоставляет `StartTransaction` метод. После запуска транзакции можно зафиксировать с помощью **фиксации** метод, или отмените его с помощью **прервать** метод.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CatDB](../../visual-cpp-samples.md)   
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)