---
title: "Ошибка компилятора C2503 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2503
dev_langs:
- C++
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a5a005e07f885fa9113f7810e15ba8bb6a19c80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2503"></a>Ошибка компилятора C2503
«класс»: базовые классы не могут содержать массивы нулевого размера  
  
 Базовый класс или структура содержит массив нулевого размера. Массив в классе должен присутствовать хотя бы один элемент.  
  
 Следующий пример приводит к возникновению ошибки C2503:  
  
```  
// C2503.cpp  
// compile with: /c  
class A {  
   public:  
   int array [];  
};  
  
class B : A {};    // C2503  
  
class C {  
public:  
   int array [10];  
};  
  
class D : C {};  
```