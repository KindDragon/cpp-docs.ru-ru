---
title: "Предупреждение (уровень 1) C4600 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4600
dev_langs:
- C++
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b031f423d2230ffea03c33d35c3d959cafc9bf37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4600"></a>Предупреждение компилятора (уровень 1) C4600
\#Директива pragma «имя макроса»: требуется допустимая строка пустым  
  
 Нельзя указывать пустую строку при передаче или имени макроса с помощью [pop_macro](../../preprocessor/pop-macro.md) или [push_macro](../../preprocessor/push-macro.md).  
  
 Следующий пример приводит к возникновению ошибки C4600:  
  
```  
// C4600.cpp  
// compile with: /W1  
int main()  
{  
   #pragma push_macro("")   // C4600 passing an empty string  
}  
```