---
title: "Ошибка компилятора C2665 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fdf6737c881df52793e1f59f04a1821a3c788134
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2665"></a>Ошибка компилятора C2665
«функция»: ни одна из перегрузок Число1 число2 параметра может выполнить преобразование из типа «тип»  
  
 Параметр перегруженной функции не может быть преобразован в требуемый тип.  Возможные решения:  
  
-   Укажите оператор преобразования.  
  
-   Используйте явное преобразование.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2665.  
  
```  
// C2665.cpp  
void func(short, char*){}  
void func(char*, char*){}  
  
int main() {  
   func(0, 1);   // C2665  
   func((short)0, (char*)1);   // OK  
}  
```