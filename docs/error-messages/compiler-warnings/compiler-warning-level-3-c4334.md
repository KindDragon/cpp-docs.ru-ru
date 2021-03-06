---
title: "Предупреждение (уровень 3) C4334 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7218caa399aec0bd1b9755fb6d0942991732121e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4334"></a>Предупреждение компилятора (уровень 3) C4334
«оператор»: результат 32-разрядного смещения неявно преобразуется в 64 бита (предполагалось 64-разрядное смещение?)  
  
 Результат 32-разрядного смещения неявно преобразовано в 64-разрядный, а компилятор предполагает, что 64-разрядное смещение был предназначен.  Чтобы устранить это предупреждение, используйте 64-разрядный сдвиг или явно привести результат сдвига к 64-разрядной.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4334.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```