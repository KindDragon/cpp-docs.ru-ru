---
title: "Ошибка компилятора C2715 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2715
dev_langs:
- C++
helpviewer_keywords:
- C2715
ms.assetid: c81567a7-5b65-468f-aaf9-835f91e468e4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f19098cedb4e62511056c669c4e43530af2bd0c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2715"></a>Ошибка компилятора C2715
«Тип»: невозможно выдать или перехватить этот тип  
  
 Типы значений не являются допустимыми аргументами, обработки исключений в управляемом коде (см. [обработка исключений](../../windows/exception-handling-cpp-component-extensions.md) для получения дополнительной информации).  
  
```  
// C2715a.cpp  
// compile with: /clr  
using namespace System;  
  
value struct V {  
   int i;  
};  
  
void f1() {  
   V v;  
   v.i = 10;  
   throw v;   // C2715  
   // try the following line instead  
   // throw ((V^)v);  
}  
  
int main() {  
   try {  
      f1();  
   }  
  
   catch(V v) { if ( v.i == 10 ) {   // C2715  
   // try the following line instead  
   // catch(V^ pv) { if ( pv->i == 10 ) {  
         Console::WriteLine("caught 10 - looks OK");  
      }   
      else {  
         Console::WriteLine("catch looks bad");  
      }  
   }  
   catch(...) {  
      Console::WriteLine("catch looks REALLY bad");  
   }  
}  
```  
