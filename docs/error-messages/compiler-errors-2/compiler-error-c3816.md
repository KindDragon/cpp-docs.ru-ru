---
title: "Ошибка компилятора C3816 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3816
dev_langs:
- C++
helpviewer_keywords:
- C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e771249c615bde8fb96243ab665b7ba5beaaa14e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3816"></a>Ошибка компилятора C3816
«объявление» был ранее объявлен или определены с помощью другого управляемого или WinRTmodifier  
  
 Предварительное объявление и текущее объявление требуют отсутствия конфликтов и несоответствий в объявлениях атрибутов.  
  
 В следующем примере показано возникновение ошибки C3816 и приводятся сведения по ее устранению.  
  
```  
// C3816a.cpp  
// compile with: /clr /c  
class C1;  
// try the following line instead  
// ref class C1;  
  
ref class C1{  // C3816, forward declaration does not use ref  
};  
```