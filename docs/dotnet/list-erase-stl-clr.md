---
title: "List::Erase (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::erase
dev_langs:
- C++
helpviewer_keywords:
- erase member [STL/CLR]
ms.assetid: 78705058-1e83-441d-b267-d4fb56451c0b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 54595b61ddd21ccd81cf4f2846224789861cb480
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="listerase-stlclr"></a>list::erase (STL/CLR)
Удаляет элементы в указанных позициях.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Параметры  
 first  
 Начало диапазона для удаления.  
  
 last  
 Конец диапазона для удаления.  
  
 где  
 Подлежащий удалению элемент.  
  
## <a name="remarks"></a>Примечания  
 Первая функция-член удаляет элемент управляемой последовательности, указанный параметром `where`. Используется для удаления одного элемента.  
  
 Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`). Используется для удаления ноль или более последовательных элементов.  
  
 Обе функции-члены возвращают итератор, указывающий на первый элемент, находящийся за всеми удаленными элементами, или [list::end (STL/CLR)](../dotnet/list-end-stl-clr.md) `()` Если такого элемента не существует.  
  
 После удаления элементов, количество копий элемента линейно количество элементов между концом стирания и дальнюю конец последовательности. (После удаления одного или нескольких элементов на любом конце последовательности, выполнено ни одной копии элемента.)  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_erase.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::list<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)