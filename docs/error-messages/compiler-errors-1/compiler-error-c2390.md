---
title: "Ошибка компилятора C2390 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 93d4cbd9de274d53fdc0369c2b85dbf2e97af48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2390"></a>Ошибка компилятора C2390
«Идентификатор»: неправильный класс хранения «спецификатор»  
  
 Класс хранения не является допустимым для глобальной области идентификатора. Класс хранения по умолчанию используется вместо недопустимый класс.  
  
 Возможные решения:  
  
-   Если идентификатор является функцией, объявите его с `extern` хранилища.  
  
-   Если идентификатор является формальным параметром или локальной переменной, объявите его с хранилищем автоматически.  
  
-   Если идентификатор является глобальной переменной, объявите его без класса хранения (автоматическая память).  
  
## <a name="example"></a>Пример  
  
-   Следующий пример приводит к возникновению ошибки C2390:  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```