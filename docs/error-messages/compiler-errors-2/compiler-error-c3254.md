---
title: "Ошибка компилятора C3254 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3254
dev_langs:
- C++
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7fea1dce2c872b1ab472c228f64d5937b81f9943
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3254"></a>Ошибка компилятора C3254
«явное переопределение»: класс содержит явное переопределение «override», но не является производным от интерфейса, содержащего объявление функции  
  
 Когда вы [явно переопределить](../../cpp/explicit-overrides-cpp.md) метода, класса, который содержит переопределенный метод должен быть производным, прямо или косвенно, из типа, содержащего функцию переопределение.  
  
 Следующий пример приводит к возникновению ошибки C3254:  
  
```  
// C3254.cpp  
__interface I  
{  
   void f();  
};  
  
__interface I1 : I  
{  
};  
  
struct A /* : I1 */  
{  
   void I1::f()  
   {   // C3254, uncomment : I1 to resolve this C3254  
   }  
};  
  
int main()  
{  
}  
```