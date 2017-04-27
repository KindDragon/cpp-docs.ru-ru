---
title: "Предупреждение компилятора (уровень 1 и уровень 4) C4700 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4700"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4700"
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 1 и уровень 4) C4700
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использована неинициализированная локальная переменная "имя"  
  
 Локальная переменная *имя* используется без предварительного присвоения значения, что может привести к непредсказуемым результатам.  
  
 Следующий пример приводит к возникновению ошибки C4700:  
  
```  
// C4700.cpp  
// compile with: /W1  
int main() {  
   int i;  
   return i;   // C4700  
}  
```  
  
 При указании параметра компиляции [\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) это предупреждение будет иметь уровень 4.  Следующий пример приводит к возникновению ошибки C4700:  
  
```  
// C4700b.cpp  
// compile with: /W4 /clr:safe /c  
using namespace System;  
int main() {  
   Int32^ bi;  
   return *bi;   // C4700  
}  
```