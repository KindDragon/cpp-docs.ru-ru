---
title: "auto_handle::get | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_handle::get"
  - "msclr::auto_handle::get"
  - "auto_handle.get"
  - "msclr.auto_handle.get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::get"
ms.assetid: 8c75727b-8f21-44b3-be3e-7eb8858da4f7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# auto_handle::get
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает содержащуюся объект.  
  
## Синтаксис  
  
```  
_element_type ^ get();  
```  
  
## Возвращаемое значение  
 , Который содержит объект.  
  
## Пример  
  
```  
// msl_auto_handle_get.cpp  
// compile with: /clr  
#include "msclr\auto_handle.h"  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ){  
      Console::WriteLine( "in ClassA constructor:" + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "in ClassA destructor:" + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
void PrintA( ClassA^ a ) {  
   a->PrintHello();  
}  
  
int main() {  
   auto_handle<ClassA> a = gcnew ClassA( "first" );  
   a->PrintHello();  
  
   ClassA^ a2 = a.get();  
   a2->PrintHello();  
  
   PrintA( a.get() );  
}  
```  
  
  **в конструкторе ClassA: сначала**  
**Hello от первого суффикса\!**  
**Hello от первого суффикса\!**  
**Hello от первого суффикса\!**  
**в деструкторе ClassA: сначала**   
## Требования  
 **Файл заголовка**\<msclr\\auto\_handle.h\>  
  
 **Пространство имен** msclr  
  
## См. также  
 [Члены auto\_handle](../dotnet/auto-handle-members.md)