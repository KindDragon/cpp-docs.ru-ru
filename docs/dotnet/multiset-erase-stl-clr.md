---
title: "multiset::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase - член [STL/CLR]"
ms.assetid: 3ff9fe2d-bf43-446a-bd3f-74550313a1d2
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# multiset::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Удаляет элементы в указанных положениях.  
  
## Синтаксис  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
size_type erase(key_type key)  
```  
  
#### Параметры  
 first  
 Начало диапазона, чтобы привести к удалению.  
  
 key  
 Значение ключа, чтобы привести к удалению.  
  
 last  
 Элемент диапазона, чтобы привести к удалению.  
  
 , где  
 Элемент, который необходимо привести к удалению.  
  
## Заметки  
 Первый функцию\-член удаляет элемент контролируемой последовательности, указанное в `where` и возвращает первый элемент указывает итератор, оставшиеся за удаленным элементом, или [multiset::end](../dotnet/multiset-end-stl-clr.md)`()`, если такой элемент не существует.  Он используется для удаления одного элемента.  
  
 Второй функцию\-член удаляет элементы контролируемой последовательности в диапазоне `[``first``,` `last``)` и возвращает первый элемент указывает итератор, оставшиеся за всеми удаленными элементами, или `end()`, если такой элемент не существует.  Он используется для удаления ноль или более соседние элементы.  
  
 Третий функцию\-член удаляет любой элемент контролируемой последовательности ключ которой имеет соответствующий заказ на `key` и возвращается число удаленных элементов.  Он используется для удаления и подсчитать все элементы, соответствующие указанному ключу.  
  
 Каждое erase элемента имеет время пропорциональное в логарифму числа элементов в контролируемой последовательности.  
  
## Пример  
  
```  
// cliext_multiset_erase.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.insert(L'd');   
    c1.insert(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    Mymultiset::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**erase\(begin\(\)\) \= B**  
 **B C, d, e**  
**erase\(begin\(\), end\(\)\-1\) \= e**  
**size\(\) \= 1**   
## Требования  
 **Заголовок:**\<cliext\/set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::clear](../dotnet/multiset-clear-stl-clr.md)