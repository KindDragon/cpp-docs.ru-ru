---
title: "Ошибка компилятора C2975 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2975
dev_langs:
- C++
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f779ec2623b6b07f61c1e8347304288d0bcfe96a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2975"></a>Ошибка компилятора C2975

> "*аргумент*": недопустимый аргумент шаблона для "*типа*", требуется константное выражение времени компиляции

Аргумент шаблона не соответствует объявлению шаблона; Константное выражение должно заключаться в угловые скобки. Переменные не разрешены в качестве фактических аргументов шаблона. Проверьте определение шаблона, чтобы найти правильные типы.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2975 и также показано правильное использование:

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

C2975 также происходит при использовании &#95; &#95; СТРОКИ &#95; &#95; как константы времени компиляции с [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md). Одним из решений будет компилироваться в [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) вместо **/ZI**.

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```