---
title: "Ошибка компилятора C2605 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2605"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2605"
ms.assetid: a0e6f132-5acf-4e19-b277-ddf196d182bf
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2605
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

name: этот метод зарезервирован в управляемом классе или классе WinRT  
  
 Определенные имена зарезервированы компилятором для внутренних функций.  Подробнее:  [Деструкторы и завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2605:  
  
```  
// C2605.cpp  
// compile with: /clr /c  
ref class R {  
protected:  
   void Finalize() {}   // C2605  
};  
```