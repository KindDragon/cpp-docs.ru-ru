---
title: "Ошибка компилятора C2425 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2425
dev_langs:
- C++
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 31fc781296815527994bfa26017e3d81f4c3eede
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2425"></a>Ошибка компилятора C2425
'маркер' : неконстантное выражение в 'контексте'  
  
 Маркер образует часть выражения, не являющегося константой, в этом контексте.  
  
 Чтобы устранить эту проблему, замените маркер на константный литерал или на вычисление.  
  
 Следующий пример приводит к возникновению ошибки C2425:  
  
```  
// C2425.cpp  
// processor: x86  
int main() {  
   int i = 3;  
   __asm {  
      mov eax, [ebp - i]   // C2425  
      mov eax, [ebp - 3]   // OK  
   }  
}  
```