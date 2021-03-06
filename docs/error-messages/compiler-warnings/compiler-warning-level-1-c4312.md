---
title: "Ошибка компилятора предупреждение (уровень 1) C4312 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4312
dev_langs:
- C++
helpviewer_keywords:
- C4312
ms.assetid: 541906ed-4f62-4bcb-947f-cf9ae7411bcb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a4e6fa46fe9b84b138fffedf206d08ffbb30790
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4312"></a>Предупреждение компилятора (уровень 1) C4312
"операция": преобразование из "тип 1" в "тип 2" большего размера  
  
 Это предупреждение сообщает о попытке присвоить 32-разрядное значение 64-разрядному указателю, например при приведении 32-разрядного `int` или `long` к 64-разрядному указателю.  
  
 Это преобразование может быть небезопасным даже для значений указателей, которые помещаются в 32 бита, при расширении знака. Если отрицательное целое 32-разрядное число присваивается 64-разрядному указателю, расширение знака приводит к тому, что значение указателя ссылается на адрес в памяти, отличный от значения целого числа.  
  
 Это предупреждение возникает только для 64-разрядных целевых сред компиляции. Дополнительные сведения см. в разделе [правила использования указателей](http://msdn.microsoft.com/library/windows/desktop/aa384242).  
  
 В следующем примере кода возникает ошибка C4312 при компиляции для 64-разрядных сред.  
  
```  
// C4312.cpp  
// compile by using: cl /W1 /LD C4312.cpp  
void* f(int i) {  
   return (void*)i;   // C4312 for 64-bit targets  
}  
  
void* f2(__int64 i) {  
   return (void*)i;   // OK  
}  
```