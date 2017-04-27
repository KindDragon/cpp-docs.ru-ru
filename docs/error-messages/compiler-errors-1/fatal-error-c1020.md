---
title: "Неустранимая ошибка C1020 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1020
dev_langs:
- C++
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
caps.latest.revision: 8
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 54108a74ac23d20480bfd61abcd7fb5b7c7b4694
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1020"></a>Неустранимая ошибка C1020
непредвиденный #endif  
  
 Директива `#endif` не имеет соответствующей директивы `#if`, `#ifdef`или `#ifndef` . Убедитесь, что каждая директива `#endif` имеет соответствующую директиву.  
  
 В следующем примере возникает ошибка C1020:  
  
```  
// C1020.cpp  
#endif     // C1020  
```  
  
 Возможное решение:  
  
```  
// C1020b.cpp  
// compile with: /c  
#if 1  
#endif  
```