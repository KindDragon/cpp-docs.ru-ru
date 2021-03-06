---
title: "_com_error::HRESULTToWCode | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::HRESULTToWCode
dev_langs:
- C++
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 14c4cdf85e67bdb0acd8dbadd178e3fbd2dbaf54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Блок, относящийся только к системам Microsoft**  
  
 Сопоставляет 32-разрядный `HRESULT` с 16-разрядным `wCode`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `hr`  
 32-разрядный `HRESULT` должен быть сопоставлен 16-разрядное `wCode`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 16-разрядное `wCode` , полученного из 32-разрядных `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 В разделе [_com_error::WCode](../cpp/com-error-wcode.md) для получения дополнительной информации.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [Класс _com_error](../cpp/com-error-class.md)