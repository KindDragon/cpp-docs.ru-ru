---
title: "STACK::Stack (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::stack::stack
dev_langs:
- C++
helpviewer_keywords:
- stack member [STL/CLR]
ms.assetid: f1cfb3fe-4d22-41e5-906b-e8faa0bcde9b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a59b353bb6ca1dc55933234c68f39f4b76dd16a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="stackstack-stlclr"></a>stack::stack (STL/CLR)
Создает объект контейнера адаптера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
stack();  
stack(stack<Value, Container>% right);  
stack(stack<Value, Container>^ right);  
explicit stack(container_type% wrapped);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Копируемый объект.  
  
 в оболочку  
 Упакованное контейнер для использования.  
  
## <a name="remarks"></a>Примечания  
 Конструктор:  
  
 `stack();`  
  
 Создает оболочку пустой контейнер. Используется, чтобы указать пустую начальную управляемую последовательность.  
  
 Конструктор:  
  
 `stack(stack<Value, Container>% right);`  
  
 Создает оболочку контейнер, который является копией `right.get_container()`. Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объект стека `right`.  
  
 Конструктор:  
  
 `stack(stack<Value, Container>^ right);`  
  
 Создает оболочку контейнер, который является копией `right->get_container()`. Они позволяют указать начальную управляемую последовательность, является копией последовательности, контролируемой объект стека `*right`.  
  
 Конструктор:  
  
 `explicit stack(container_type% wrapped);`  
  
 использует существующий контейнер `wrapped` как изолированного контейнера. Используется для создания стека из существующего контейнера.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_stack_construct.cpp   
// compile with: /clr   
#include <cliext/stack>   
#include <cliext/vector>   
  
typedef cliext::stack<wchar_t> Mystack;   
typedef cliext::vector<wchar_t> Myvector;   
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;   
int main()   
    {   
// construct an empty container   
    Mystack c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Myvector v2(5, L'x');   
    Mystack_vec c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mystack_vec c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Mystack_vec c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 x x x x x  
 x x x x x  
 x x x x x  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/stack >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [стек (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [STACK::Assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)   
 [STACK::generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)   
 [stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)