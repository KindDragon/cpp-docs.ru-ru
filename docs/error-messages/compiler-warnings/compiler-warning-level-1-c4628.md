---
title: "Предупреждение (уровень 1) C4628 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4628
dev_langs:
- C++
helpviewer_keywords:
- C4628
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c121f7bc954cb5df560d2b5517ba1e40c48ad0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4628"></a>Предупреждение компилятора (уровень 1) C4628
диграфы не поддерживаются при наличии параметра -Ze. Последовательность знаков "digraph" не преобразована в альтернативный маркер для "char"  
  
 Диграфы не поддерживаются в режиме [/Ze](../../build/reference/za-ze-disable-language-extensions.md). Это предупреждение будет идти из-за ошибки.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Следующий пример приводит к возникновению ошибки C4628:  
  
```  
// C4628.cpp  
// compile with: /WX  
#pragma warning(default : 4628)  
int main()  
<%   // C4628 <% digraph for {  
}  
```