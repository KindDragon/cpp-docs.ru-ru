---
title: "Инициализация массивов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing arrays [C++]
- arrays [C++], initializing
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 42d47f8ba7f7df8285d3c4f685a212c77974b144
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-arrays"></a>Инициализация массивов
Если класс имеет конструктор, массивы этого класса инициализируются конструктором. Если число элементов в списке инициализаторов меньше числа элементов в массиве, для остальных элементов используется конструктор по умолчанию. Если конструктор по умолчанию для класса не определен, список инициализаторов должен быть полным, т. е. для каждого элемента массива должен иметься один инициализатор.  
  
 Рассмотрим класс `Point`, определяющий два конструктора:  
  
```  
// initializing_arrays1.cpp  
class Point  
{  
public:  
   Point()   // Default constructor.  
   {  
   }  
   Point( int, int )   // Construct from two ints  
   {  
   }  
};  
  
// An array of Point objects can be declared as follows:  
Point aPoint[3] = {  
   Point( 3, 3 )     // Use int, int constructor.  
};  
  
int main()  
{  
}  
```  
  
 Первый элемент `aPoint` создается с помощью конструктора `Point( int, int )`, а оставшиеся два элемента — с помощью конструктора по умолчанию.  
  
 Массивы статических членов (ли **const** или нет) могут инициализироваться в своих определениях (вне объявления класса). Пример:  
  
```  
// initializing_arrays2.cpp  
class WindowColors  
{  
public:  
    static const char *rgszWindowPartList[7];  
};  
  
const char *WindowColors::rgszWindowPartList[7] = {  
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",  
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };  
int main()  
{  
}  
```  
  
