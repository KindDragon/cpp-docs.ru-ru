---
title: "Ошибка вычислителя выражений CXX0064 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0064"
  - "CXX0064"
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка вычислителя выражений CXX0064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нельзя задать точку останова на границе виртуальной функции\-члена  
  
 Для виртуальной функции\-члена была задана точка останова посредством указателя на объект, например:  
  
```  
pClass->vfunc( int );  
```  
  
 Точка останова для виртуальной функции\-члена может быть задана путем ввода класса, например:  
  
```  
Class::vfunc( int );  
```  
  
 Эта ошибка идентична ошибке CAN0064.