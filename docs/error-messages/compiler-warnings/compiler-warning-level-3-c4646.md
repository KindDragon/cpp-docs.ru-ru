---
title: "Ошибка компилятора предупреждение (уровень 3) C4646 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4646
dev_langs:
- C++
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b44b85fc8834dcc262b10ee26f34752f8eeb429
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4646"></a>Предупреждение компилятора (уровень 3) C4646
функция, объявленная с атрибутом __declspec(noreturn) имеет тип, отличный от void  
  
 Функция, помеченная модификатором [noreturn](../../cpp/noreturn.md) `__declspec` , должна иметь тип возврата [void](../../cpp/void-cpp.md) .  
  
 В следующем примере возникает ошибка C4646.  
  
```  
// C4646.cpp  
// compile with: /W3 /WX  
int __declspec(noreturn) TestFunction()  
{   // C4646  make return type void  
}  
```