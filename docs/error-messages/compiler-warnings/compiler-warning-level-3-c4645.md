---
title: "Ошибка компилятора предупреждение (уровень 3) C4645 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4645
dev_langs:
- C++
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e27ecf588ed8c6b581e0ac6d29b29108fd33b8b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4645"></a>Предупреждение компилятора (уровень 3) C4645
функция, объявленная с атрибутом __declspec(noreturn) имеет оператор return  
  
 A [return](../../cpp/return-statement-in-program-termination-cpp.md) найден в функции, помеченной модификатором [noreturn](../../cpp/noreturn.md) `__declspec` . Оператор `return` был пропущен.  
  
 Следующий пример приводит к возникновению ошибки C4645.  
  
```  
// C4645.cpp  
// compile with:  /W3  
void __declspec(noreturn) func() {  
   return;   // C4645, delete this line to resolve  
}  
  
int main() {  
}  
```