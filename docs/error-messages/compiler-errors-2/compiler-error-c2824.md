---
title: "Ошибка компилятора C2824 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2824"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2824"
ms.assetid: 5bd865f7-e0af-404e-80fe-e2b798b44a59
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2824
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

тип возвращаемого значения для "оператора" должен быть "void \*"  
  
 В случае использования указателей без смещения, при перегрузке оператора `new` должно возвращаться значение `void *`.  
  
 Следующий пример приводит к возникновению ошибки C2824:  
  
```  
// C2824.cpp  
// compile with: /c  
class   A {  
   A* operator new(size_t i, char *m);   // C2824  
   // try the following line instead  
   // void* operator new(size_t i, char *m);  
};  
```