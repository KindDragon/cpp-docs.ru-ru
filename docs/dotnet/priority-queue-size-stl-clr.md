---
title: "priority_queue::size (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::priority_queue::size
dev_langs:
- C++
helpviewer_keywords:
- size member [STL/CLR]
ms.assetid: 37ef4be3-daac-4b5a-9a00-085863f694e0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 88e2f017a47de85d4e8426a26f05ff1fb41bbe0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueuesize-stlclr"></a>priority_queue::size (STL/CLR)
Подсчитывает количество элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член возвращает длину управляемой последовательности. Используется для определения количества элементов в данный момент в управляемой последовательности. Если вас интересует ли последовательность имеет ненулевое значение, размер, в разделе [priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)`()`.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_priority_queue_size.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
size() = 3 starting with 3  
size() = 2 after popping  
size() = 4 after adding 2  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/очереди >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)