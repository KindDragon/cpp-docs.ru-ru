---
title: "Элементы управления ActiveX в MFC. Свойства | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC ActiveX - элементы управления, свойства"
  - "свойства [MFC]"
  - "свойства [MFC], элементы управления ActiveX"
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Элементы управления ActiveX в MFC. Свойства
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Элемент управления ActiveX вызывает события для связи с его контейнером элементов управления.  Контейнер, в буфер обмена, используются методы и свойства для взаимодействия с элементом управления.  Методы и свойства схожи в использовании цели и, соответственно, к функциям элемента и переменные\-члены класса C\+\+.  Свойства элементов данных элемент управления ActiveX, предоставляемых в любой контейнер.  Свойства предоставляют интерфейс для приложений, содержащих элементы управления ActiveX, такие как контейнеры клиентов автоматизации и элемент управления ActiveX.  
  
 Свойства также называются атрибутами.  
  
 Дополнительные сведения о методах элементов управления ActiveX см. в статье [Элементы управления ActiveX MFC. Методы](../mfc/mfc-activex-controls-methods.md).  
  
 Элементы управления ActiveX могут реализовывать и стандартные и пользовательские методы и свойства.  Класс `COleControl` обеспечивает реализацию стандартных свойств. \(Полный список стандартных свойств см. в статье [Элементы управления ActiveX MFC. Добавление стандартных свойств](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Stock%20Properties.md)\). Пользовательские свойства, определяемые разработчиком, добавляют специализированные возможности в элемент управления ActiveX.  Дополнительные сведения см. в разделе [Элементы управления ActiveX MFC. Добавление пользовательских свойств](../mfc/mfc-activex-controls-adding-custom-properties.md) в.  
  
 И пользовательским и стандартные свойства, как и методы, поддерживаются механизмом, состоящий из схемы подготовки к сообщению, обрабатывает свойства и методы и существующие функции\-члены класса `COleControl`.  Кроме того, эти свойства могут иметь параметры, разработчик использует для передачи дополнительные сведения к элементу управления.  
  
 В следующих статьях рассматриваются свойства элемента управления ActiveX более подробно.  
  
-   [Элементы управления ActiveX MFC. Добавление стандартных свойств](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Stock%20Properties.md)  
  
-   [Элементы управления ActiveX MFC. Добавление пользовательских свойств](../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [Элементы управления ActiveX MFC. Предварительная реализацию свойства](../mfc/mfc-activex-controls-advanced-property-implementation.md)  
  
-   [Элементы управления ActiveX MFC. Доступ ко внешним свойства](../mfc/mfc-activex-controls-accessing-ambient-properties.md)  
  
## См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)