---
title: "set::const_iterator (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::set::const_iterator
dev_langs:
- C++
helpviewer_keywords:
- const_iterator member [STL/CLR]
ms.assetid: de234ad4-d420-4da8-a13a-1aec8c337d8b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: feabc936482953cc6fb5e861a21b159ff2d277a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="setconstiterator-stlclr"></a>set::const_iterator (STL/CLR)
Тип постоянного итератора для управляемой последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef T2 const_iterator;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип описывает объект незаданного типа `T2` , можно использовать в качестве константы двунаправленного итератора для управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_set_const_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Myset::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext и set >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [набор (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::iterator (STL/CLR)](../dotnet/set-iterator-stl-clr.md)