---
title: "priority_queue::pop (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::priority_queue::pop"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pop - член [STL/CLR]"
ms.assetid: d363b3f1-247b-466a-a300-c5918b0dfd4e
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# priority_queue::pop (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Удаляет самый высокий — proirity элемент.  
  
## Синтаксис  
  
```  
void pop();  
```  
  
## Заметки  
 Удаляет элемент функцию\-член наивысшего приоритета контролируемой последовательности, которая должна быть непустой.  Он используется для сокращения очередь одним элементом в обратно.  
  
## Пример  
  
```  
// cliext_priority_queue_pop.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop();   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **B C.**  
 **a B**   
## Требования  
 **Заголовок:**\<cliext\/queue\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [priority\_queue::push](../dotnet/priority-queue-push-stl-clr.md)