---
title: "ограниченные | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.restricted
dev_langs:
- C++
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 569d57da691f40857f54dcae1c383ff7758564f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="restricted"></a>restricted
Указывает, что член модуле, интерфейсе или disp-интерфейса не может вызываться произвольным образом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ restricted(  
   interfaces  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 `interfaces`  
 Один или несколько интерфейсов, которые не может вызываться произвольным образом COM-объекта. Этот параметр допустим только при применении к классу.  
  
## <a name="remarks"></a>Примечания  
 **Ограниченных** языка C++ имеет ту же функциональность, что [ограниченных](http://msdn.microsoft.com/library/windows/desktop/aa367157) языка MIDL.  
  
## <a name="example"></a>Пример  
 Следующий код показывает, как использовать **ограниченных** атрибута:  
  
```  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод, `interface`, **класса**,`struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**кокласс** (при применении к **классу** или `struct`)|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
