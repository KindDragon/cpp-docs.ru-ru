---
title: "Неустранимая ошибка C1019 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1019
dev_langs:
- C++
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b980d08adc2d941d817735dc92df55de5c8be686
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1019"></a>Неустранимая ошибка C1019
непредвиденный #else  
  
 Директива `#else` находится за пределами конструкции `#if`, `#ifdef`или `#ifndef` . Используйте `#else` только в одной из этих конструкций.  
  
 При компиляции следующего примера возникнет ошибка C1019:  
  
```  
// C1019.cpp  
#else   // C1019  
#endif  
  
int main() {}  
```  
  
 Возможное решение  
  
```  
// C1019b.cpp  
#if 1  
#else  
#endif  
  
int main() {}  
```