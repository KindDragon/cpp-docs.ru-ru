---
title: "auto_gcroot::operator auto_gcroot | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- auto_gcroot.operator auto_gcroot
- auto_gcroot::operator auto_gcroot
- msclr.auto_gcroot.operator auto_gcroot
- msclr::auto_gcroot::operator auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot operator
ms.assetid: 43e3f27a-9f68-444f-9149-a9282a9b935a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 58ccf1aa32a999fd85f6dc0a14fb514f6508a386
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="autogcrootoperator-autogcroot"></a>auto_gcroot::operator auto_gcroot
Оператор приведения типа `auto_gcroot` и совместимые типы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename _other_type>  
operator auto_gcroot<_other_type>();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Текущий `auto_gcroot` приведение к `auto_gcroot<_other_type>`.  
  
## <a name="example"></a>Пример  
  
```  
// msl_auto_gcroot_op_auto_gcroot.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {}  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class ClassB : ClassA {  
public:  
   ClassB( String ^ s) : ClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main() {  
   auto_gcroot<ClassB^> b = gcnew ClassB("first");  
   b->PrintHello();  
   auto_gcroot<ClassA^> a = (auto_gcroot<ClassA^>)b;  
   a->PrintHello();  
}  
```  
  
```Output  
Hello from first B!  
Hello from first A!  
```  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\auto_gcroot.h >  
  
 **Пространство имен** msclr  
  
## <a name="see-also"></a>См. также  
 [Члены auto_gcroot](../dotnet/auto-gcroot-members.md)