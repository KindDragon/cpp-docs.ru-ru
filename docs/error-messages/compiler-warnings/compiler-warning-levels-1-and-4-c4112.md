---
title: "Предупреждение (уровни 1 и 4) C4112 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e82b2425aef840d8da7a0d0ad4dc4b81bd2a812
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Предупреждение компилятора (уровни 1 и 4) C4112
\#строки требуется целое число между 1 и числом  
  
 Директива [#Line](../../preprocessor/hash-line-directive-c-cpp.md) указывает целочисленный параметр, который не входит в допустимый диапазон.  
  
 Если указанный параметр имеет значение меньше 1, счетчик строк сбрасывается до 1. Если указанный параметр больше, чем *номер*, представляющий определенный компилятором предел, то счетчик строк не изменяется. Это предупреждение уровня 1 в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) и предупреждение уровня 4 в расширениях Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 Следующий пример приводит к возникновению ошибки C4112:  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```