---
title: "Ошибка компилятора C3761 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3761"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3761"
ms.assetid: 0c16f093-7a78-4838-b90b-0c67ef6e9270
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3761
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": атрибут "retval" может применяться только к последнему аргументу функции  
  
 Атрибут [retval](../../windows/retval.md) был применен к аргументу функции, не стоящему последним в списке.  
  
 Следующий пример приводит к возникновению ошибки C3761:  
  
```  
// C3761.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(name=test) ];  
  
[dispinterface]  
__interface I  
{  
   [id(1)] HRESULT func([out, retval] int* i, [in] int j);  
   // try the following line instead  
   // [id(1)] HRESULT func([in] int i, [out, retval] int* j);  
};  
  
[coclass]  
struct C : I {   // C3761  
   HRESULT func(int* i, int j)  
   // try the following line instead  
   // HRESULT func(int j, int* i)  
   {  
      return S_OK;  
   }  
};  
  
int main()  
{  
}  
```