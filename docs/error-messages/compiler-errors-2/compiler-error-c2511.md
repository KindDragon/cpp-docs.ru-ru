---
title: "Ошибка компилятора C2511 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2511
dev_langs:
- C++
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 904f8671aff18d7a9216567abc3db0f2f5cd82de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2511"></a>Ошибка компилятора C2511
«Идентификатор»: перегруженная функция-член не найден в «класс»  
  
 Версия функции не объявлено с указанными параметрами.  Возможные причины:  
  
1.  Функции переданы неверные параметры.  
  
2.  Передача параметров в неправильном порядке.  
  
3.  Неверное написание имен параметров.  
  
 Следующий пример приводит к возникновению ошибки C2511:  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```