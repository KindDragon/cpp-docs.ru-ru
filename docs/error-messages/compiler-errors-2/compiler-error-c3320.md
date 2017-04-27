---
title: "C3320 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3320
dev_langs:
- C++
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 4b4acfe97e38cf13e336b7c58ffc868c69cf7a09
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3320"></a>Ошибка компилятора C3320
"тип": имя типа не может совпадать со свойством name модуля  
  
Экспортированный определяемого пользователем типа (UDT), который может быть структура, класс, перечисление или объединение, не может иметь то же имя, как параметр, передаваемый [модуль](../../windows/module-cpp.md) свойства имени атрибута.  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3320:  
  
```cpp  
// C3320.cpp  
#include "unknwn.h"  
[module(name="xx")];  
  
[export] struct xx {   // C3320  
// Try the following line instead  
// [export] struct yy {  
   int i;  
};  
```