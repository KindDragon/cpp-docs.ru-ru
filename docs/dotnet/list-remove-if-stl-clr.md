---
title: "List::remove_if (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::remove_if
dev_langs:
- C++
helpviewer_keywords:
- remove_if member [STL/CLR]
ms.assetid: cbc66192-751b-41c5-b557-d5d7bbc2a840
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 39cdd5fe6f7bf143b6e46b8fcde1a34f919be191
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="listremoveif-stlclr"></a>list::remove_if (STL/CLR)
Удаляет элементы, которые прошли заданный тест.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Pred1>  
    void remove_if(Pred1 pred);  
```  
  
#### <a name="parameters"></a>Параметры  
 Pred  
 Тест для удаляемых элементов.  
  
## <a name="remarks"></a>Примечания  
 Функция-член удаляет из управляемой последовательности (стираниям) каждого элемента `X` для которого `pred(X)` имеет значение true. Используется для удаления всех элементов, которые определяют, как функции или делегат, удовлетворяющих заданному условию.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_list_remove_if.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b b b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// fail to remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::equal_to<wchar_t> >(   
        cliext::equal_to<wchar_t>(), L'd'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::not_equal_to<wchar_t> >(   
        cliext::not_equal_to<wchar_t>(), L'b'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b b b c  
a b b b c  
b b b  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/list >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [список (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List::Clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)   
 [List::Erase (STL/CLR)](../dotnet/list-erase-stl-clr.md)   
 [List::Remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)   
 [list::unique (STL/CLR)](../dotnet/list-unique-stl-clr.md)