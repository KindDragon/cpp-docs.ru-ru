---
title: "Ошибка компилятора C3540 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3540
dev_langs:
- C++
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3befc331c4f43f4efd4e5039258e0faddae97db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3540"></a>Ошибка компилятора C3540
«Тип»: невозможно применить sizeof к типу, который содержит «auto»  
  
 [Sizeof](../../cpp/sizeof-operator.md) оператор не может применяться к указанному типу, так как он содержит `auto` спецификатор.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3540.  
  
```  
// C3540.cpp  
// Compile with /Zc:auto  
int main() {  
    auto x = 123;  
    sizeof(x);    // OK  
    sizeof(auto); // C3540  
    return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово Auto](../../cpp/auto-keyword.md)   
 [/ Zc: auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [Оператор sizeof](../../cpp/sizeof-operator.md)