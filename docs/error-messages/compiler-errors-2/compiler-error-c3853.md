---
title: "Ошибка компилятора C3853 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3853"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3853"
ms.assetid: 5b71805d-52b4-44ec-80ae-37c68d876f6a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C3853
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\=": повторная инициализация ссылки или присвоение через ссылку на функцию не допускается  
  
 Не удается присвоить значение ссылке через функцию, поскольку функции не являются значениями.  
  
 Следующий пример демонстрирует причины возникновения ошибки C3853:  
  
```  
// C3853.cpp  
// compile with: /EHsc  
#include <iostream>  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   rf = afunc;   // C3853, can't reassign to a ref that's an lvalue  
   int i = 99;  
   int & ri = i;  
   std::cout << i << std::endl;  
   ri = 0;   // OK, i = 88;  
   std::cout << i << std::endl;  
}  
```