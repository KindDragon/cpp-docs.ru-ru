---
title: "Предупреждение компилятора (уровень 4) C4408 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4408"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4408"
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4408
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

анонимная структура или объединение не объявляет никаких элементов данных  
  
 У анонимной структуры или объединения должен быть по крайней мере один элемент данных.  
  
 Следующий пример приводит к возникновению ошибки C4408.  
  
```  
// C4408.cpp  
// compile with: /W4 /LD  
static union  
{  
   // int i;  
};  
// a named union can have no data members  
// } MyUnion;  
```