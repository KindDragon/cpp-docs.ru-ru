---
title: "Ошибка компилятора C2081 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2081
dev_langs:
- C++
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10a3e8f4444fcdb0fe9e286abf5331c1d8bae523
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2081"></a>Ошибка компилятора C2081
«Идентификатор»: имя в недопустимый список формальных параметров  
  
 Синтаксическая ошибка, связанная с идентификатором.  
  
 Эта ошибка может вызываться с использованием старого стиля в списке формальных параметров. Необходимо указать тип формальных параметров в списке формальных параметров.  
  
 Следующий пример приводит к возникновению ошибки C2081:  
  
```  
// C2081.c  
void func( int i, j ) {}  // C2081, no type specified for j  
```  
  
 Возможное решение  
  
```  
// C2081b.c  
// compile with: /c  
void func( int i, int j ) {}  
```