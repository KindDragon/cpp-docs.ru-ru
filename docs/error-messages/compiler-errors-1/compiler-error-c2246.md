---
title: "Ошибка компилятора C2246 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2246
dev_langs:
- C++
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c78a1b36e85724ecb397bff67d60c666cb64ba3d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2246"></a>Ошибка компилятора C2246
"идентификатор": недопустимый статический элемент данных в локально определенном классе  
  
 Член класса, структуры или объединения с локальной областью объявлен как `static`.  
  
 Следующий пример приводит к возникновению ошибки C2246:  
  
```  
// C2246.cpp  
// compile with: /c  
void func( void ) {  
   class A { static int i; };   // C2246  i is local to func  
   static int j;   // OK  
};  
```