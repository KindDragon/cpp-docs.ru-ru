---
title: "Ошибка компилятора C2310 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2310
dev_langs:
- C++
helpviewer_keywords:
- C2310
ms.assetid: 1969c682-b97e-43fb-b9a9-f783e7ff1710
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 05c6b4501261764bf3c97a699fa2935b50ec0896
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2310"></a>Ошибка компилятора C2310
обработчики catch необходимо указать один тип  
  
 Обработчик catch не указывает тип или несколько типов.  
  
 Следующий пример приводит к возникновению ошибки C2310:  
  
```  
// C2310.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try {  
      throw "Out of memory!";  
   }  
   catch( int ,int) {}   // C2310 two types  
   // try the following line instead  
   // catch( int)  {}  
}  
```