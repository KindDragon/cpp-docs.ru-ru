---
title: "Ошибка компилятора предупреждение (уровень 1) C4002 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4002
dev_langs:
- C++
helpviewer_keywords:
- C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c11b40f29ccbd0e58afdce08463a87dc71181d6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4002"></a>Предупреждение компилятора (уровень 1) C4002
слишком много фактических параметров для макроопределения "идентификатор"  
  
 Количество фактических параметров в макросе превышает количество формальных параметров в определении макроса. Препроцессор собирает лишние параметры, но игнорирует их в расширении макроса.  
  
 Ошибка C4002 может возникать в результате неправильного использования [Variadic Macros](../../preprocessor/variadic-macros.md).  
  
 Следующий пример приводит к возникновению предупреждения C4002:  
  
```  
// C4002.cpp  
// compile with: /W1  
#define test(a) (a)  
  
int main() {  
   int a = 1;  
   int b = 2;  
   a = test(a,b);   // C4002  
   // try..  
   a = test(a);  
}  
```  
  
 Эта ошибка также может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: лишние запятые в макросе больше не принимаются.  
  
 Компилятор больше не принимает лишние запятые в макросе. Чтобы код функционировал в Visual Studio .NET 2003 и в версиях Visual Studio .NET для Visual C++, следует удалить лишние запятые.  
  
```  
// C4002b.cpp  
// compile with: /W1  
#define F(x,y)  
int main()  
{  
   F(2,,,,,,3,,,,,,)   // C4002  
   // Try the following line instead:  
   // F(2,3)  
}  
```