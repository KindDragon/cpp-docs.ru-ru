---
title: "collection_adapter::Reference (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::collection_adapter::reference
dev_langs:
- C++
helpviewer_keywords:
- reference member [STL/CLR]
ms.assetid: 8a624db2-2ab0-4f8c-8dcb-beb190e474ca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: da1c0bd2642d031c0e819b191bf27d05e48f3f46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="collectionadapterreference-stlclr"></a>collection_adapter::reference (STL/CLR)
Тип ссылки на элемент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef value_type% reference;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип описывает ссылку на элемент.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_collection_adapter_reference.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Mycoll::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext адаптер >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [collection_adapter::value_type (STL/CLR)](../dotnet/collection-adapter-value-type-stl-clr.md)