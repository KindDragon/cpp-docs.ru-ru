---
title: "Предупреждение (уровень 3) C4570 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4570
dev_langs:
- C++
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ecd1794de0ad36c5116d5db9f051ed9ddc9cf12e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4570"></a>Предупреждение компилятора (уровень 3) C4570
«Тип»: не объявлен явно как абстрактный, однако содержит абстрактные функции  
  
 Тип, содержащий [абстрактный](../../windows/abstract-cpp-component-extensions.md) функции должен быть помечен как абстрактный.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4570.  
  
```  
// C4570.cpp  
// compile with: /clr /W3 /c  
ref struct X {   // C4570  
// try the following line instead  
// ref class X abstract {  
   virtual void f() abstract;  
};  
```