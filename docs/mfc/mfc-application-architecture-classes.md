---
title: "Классы архитектуры приложения MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы архитектуры приложений"
  - "классы [C++], MFC - библиотека"
  - "MFC [C++], разработка приложений"
  - "MFC [C++], классы"
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Классы архитектуры приложения MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Классы в этой категории, составляющие архитектуру приложения платформы.  Они предоставляют функциональные возможности, общие для большинства приложений.  Заливки в платформу для добавления функции для конкретного приложения.  Обычно это сделать новые классы, производные от классов архитектуры, а затем добавлять новые члены или переопределять существующие функции\-члены.  
  
 [Мастер приложений](../Topic/MFC%20Application%20Wizard.md) создать несколько типов приложений, использующих платформу приложения в различных вариантах.  Приложения однодокументного интерфейса \(SDI\) и \(MDI\)\) позволяют полностью использовать части от платформы архитектурой документов и представлений.  Другие приложения, например приложения на основе диалоговых окон, приложения на основе форм и библиотеки DLL, используют только некоторые из функций архитектуры документов и представлений.  
  
 Приложения документа или представления содержат один или несколько основные документов, представления и фреймовые окна.  Объект шаблона документов связывают классы для всех документов и представлений и набора кадра.  
  
 Однако не следует использовать архитектуры документов и представлений в приложении MFC, существует несколько преимуществ методика.  Поддержка контейнера и сервера MFC OLE основана на архитектуре документ\/представление, как поддержка печати и предварительного просмотра.  
  
 Все приложения MFC имеют по крайней мере 2 объекта: объект приложения, являющийся производным от [CWinApp](../mfc/reference/cwinapp-class.md), и некоторые параметры сортировки объекта главного окна, производная \(часто косвенно\) из [CWnd](../Topic/CWnd%20Class.md). \(Чаще всего главного окна являются производными от [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) или [CDialog](../mfc/reference/cdialog-class.md), которые являются производными от `CWnd`\).  
  
 Приложения, которые используют архитектуру " документ\-представление " содержат дополнительные объекты.  Основные объекты:  
  
-   Объект приложения, являющийся производным от класса [CWinApp](../mfc/reference/cwinapp-class.md), как упоминалось ранее.  
  
-   Один или несколько объектов класса документа, производных от класса [CDocument](../Topic/CDocument%20Class.md).  Объекты класса документа за внутреннего представления данных манипулированного в представлении.  Они могут быть связаны с файлом данных.  
  
-   Один или несколько объектов представления, производных от класса [CView](../Topic/CView%20Class.md).  Каждое представление окно, вложено в документ и связанных с фреймовым окном.  Представления отображают и управляют данными, содержащимися в объекте класса документа.  
  
 Приложения документ\/представление также содержат фреймовые производные из окна \( [CFrameWnd](../mfc/reference/cframewnd-class.md)\) и шаблоны документов, производных от \( [CDocTemplate](../mfc/reference/cdoctemplate-class.md)\).  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)