---
title: "List::generic_value (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::generic_value
dev_langs:
- C++
helpviewer_keywords:
- generic_value member [STL/CLR]
ms.assetid: daa0fc3f-cda2-4531-8cc2-a523737d4103
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 75d5d667e24addf0977d8979f3e8dd7fdb9d38ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="listgenericvalue-stlclr"></a>list::generic_value (STL/CLR)
Тип элемента для использования с универсальный интерфейс для контейнера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef GValue generic_value;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип описывает объект типа `GValue` , описывающий значение хранимого элемента для использования с универсальный интерфейс для класса контейнера шаблона.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_generic_value.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a a c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::generic_container (STL/CLR)](../dotnet/list-generic-container-stl-clr.md)   
 [List::generic_iterator (STL/CLR)](../dotnet/list-generic-iterator-stl-clr.md)   
 [list::generic_reverse_iterator (STL/CLR)](../dotnet/list-generic-reverse-iterator-stl-clr.md)