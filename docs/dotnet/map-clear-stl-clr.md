---
title: "MAP::Clear (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::map::clear
dev_langs:
- C++
helpviewer_keywords:
- clear member [STL/CLR]
ms.assetid: 2a6a01fe-2998-447d-9ae8-6cb6343d0dfa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0af5d2bc19422c3e28550863d2197ebc5dd5343f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mapclear-stlclr"></a>map::clear (STL/CLR)
Удаляет все элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член вызывает [map::erase (STL/CLR)](../dotnet/map-erase-stl-clr.md) `(` [map::begin (STL/CLR)](../dotnet/map-begin-stl-clr.md) `(),` [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md) `())`. Используется, чтобы обеспечить пустой управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_map_clear.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
  
// display contents " [a 1] [b 2]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
size() = 0  
 [a 1] [b 2]  
size() = 0  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [Карта (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map::erase (STL/CLR)](../dotnet/map-erase-stl-clr.md)