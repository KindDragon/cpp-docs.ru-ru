---
title: "Использование CHotKeyCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CHotKeyCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHotKeyCtrl - класс, использование"
  - "элементы управления сочетанием клавиш"
  - "ключи, сочетание клавиш и CHotKeyCtrl"
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Использование CHotKeyCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Управление горячей ", представленным классом [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md), окно, в котором отображается текстовое представление сочетания клавиш пользовательских типов в него, например CTRL\+SHIFT\+Q.  Оно также поддерживает внутреннее представление данного ключа в форме виртуального кода клавиши и набора флажков, предоставляющих состояние переноса.  Элемент управления " горячей фактически не задает горячую клавишу — это можно выбрать программы. \(Виртуальные кода клавиши Для списка стандартных см. Winuser.h\).  
  
 Используйте элемент управления " горячей " для получения входных данных пользователя, для которого горячая клавиш, связываемый с окном или потоком.  Управления горячей " часто используются в диалоговых окнах, например, можно указать, следует ли, что пользователь присвоил горячая клавиш.  За программы извлечения значений, горячую горячей клавиши ПРОБЕЛ из элемента управления и вызвать соответствующие функции для связывания горячая клавиш с окном или потоком.  
  
## Дополнительные сведения  
  
-   [Использование элемента управления горячей "](../Topic/Using%20a%20Hot%20Key%20Control.md)  
  
-   [Параметр горячую ПРОБЕЛ](../Topic/Setting%20a%20Hot%20Key.md)  
  
-   [Глобальные горячие клавиши](../Topic/Global%20Hot%20Keys.md)  
  
-   [Горячие клавиши для определенного](../Topic/Thread-Specific%20Hot%20Keys.md)  
  
## См. также  
 [Элементы управления](../mfc/controls-mfc.md)