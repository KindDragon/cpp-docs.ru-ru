---
title: "Предупреждение (уровень 3) C4635 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16b6a19618afeed952cfa594961a0e4ccb777d26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4635"></a>Предупреждение компилятора (уровень 3) C4635
Цель комментария XML-документа: неправильно сформированный XML: причина  
  
 Компилятор обнаружил проблему с XML-тегами.  Устраните проблему и выполните повторную компиляцию.  
  
 Следующий пример приводит к возникновению ошибки C4635:  
  
```  
// C4635.cpp  
// compile with: /doc /clr /W3 /c  
/// <summary>     
/// The contents of the folder have changed.  
/// <summary/>   // C4635  
  
// try the following line instead  
// /// </summary>  
public ref class Test {};  
```  
  
 Обратите внимание, что в результате для данного примера говорится: **Закрывающий тег member не соответствует открывающему тегу summary.**  
  
 Проблема в этом примере это закрывающий тег для \<сводки > сформирован неправильно, и компилятор не распознает его как \<сводки > закрывающего тега.  \<Член > тег включается в XDC-файл компилятором в каждой компиляции/doc.  Таким образом, проблема здесь в том, что закрывающий тег \</member >, не соответствует предыдущему открывающему тегу, обработанному компилятором (\<сводки >.