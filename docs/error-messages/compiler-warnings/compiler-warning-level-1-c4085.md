---
title: "Ошибка компилятора предупреждение (уровень 1) C4085 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4085
dev_langs:
- C++
helpviewer_keywords:
- C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 562d2433240c57b4d21bf0b2984f709d9ff54375
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4085"></a>Предупреждение компилятора (уровень 1) C4085
требуется параметр директивы pragma: "on" или "off"  
  
 Прагме требуется параметр **on** или **off** . Прагма игнорируется.  
  
 В следующем примере возникает ошибка C4085:  
  
```  
// C4085.cpp  
// compile with: /W1 /LD  
#pragma optimize( "t", maybe )  // C4085  
```