---
title: "Предупреждение (уровень 1) C4353 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4353
dev_langs:
- C++
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8dd3ec65dac6720509b9c918f272d2eb6ff2720c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4353"></a>Предупреждение компилятора (уровень 1) C4353
использовано нестандартное расширение: константа 0 в качестве выражения функции. Вместо этого используйте функцию «__noop» встроенная функция  
  
 Нельзя использовать константу, равную нулю (0) как выражение функции. Дополнительные сведения см. в разделе [__noop](../../intrinsics/noop.md).  
  
 Следующий пример приводит к возникновению ошибки C4353:  
  
```  
// C4353.cpp  
// compile with: /W1  
void MyPrintf(void){};  
#define X 0  
#if X  
   #define DBPRINT MyPrint  
#else  
   #define DBPRINT 0   // C4353 expected  
#endif  
int main(){  
DBPRINT();  
}  
```