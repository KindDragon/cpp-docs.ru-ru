---
title: "Последовательность операций для создания приложений OLE | Microsoft Docs"
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
  - "приложения [OLE]"
  - "приложения [OLE], создание"
  - "приложения OLE [C++]"
  - "приложения OLE [C++], создание"
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Последовательность операций для создания приложений OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующей таблице показаны свою роль и роль платформы в создании OLE компоновку и внедрение приложения.  Они представляют собой параметры, доступные вместо последовательность действий для выполнения.  
  
### Создание приложения OLE  
  
|Задача|Выполняется|.NET Framework.|  
|------------|-----------------|---------------------|  
|Создание компонента модели COM.|Запустите мастер приложений MFC.  Выберите пункт **Весь сервер** или **Mini\-server** на вкладке **Поддержка составн. док\-тов**.|Платформа создает общую схему приложения с включенной возможностью модели COM компонент.  Все возможности модели COM можно передавать данные к существующим приложениям только с небольшими изменениями.|  
|Создайте приложение контейнера с нуля.|Запустите мастер приложений MFC.  Выберите **Контейнер** на вкладке **Поддержка составн. док\-тов**.  Использование представления классов см. в редактор исходного кода.  Введите код для тестирования функций обработчика модели COM.|Платформа создает схемы, приложение может привести COM\-объект, созданные приложениями компонента модели COM \(сервера\).|  
|Создайте приложение, поддерживающий автоматизацию с нуля.|Запустите мастер приложений MFC.  Выберите **Автоматизация** из вкладки **Дополнительные параметры**.  Используйте представление классов для предоставления методов и свойств в приложении для автоматизации.|Платформа создает схемы приложение, может быть активировано и автоматизировано другими приложениями.|  
  
## См. также  
 [Сборка в платформе](../mfc/building-on-the-framework.md)   
 [Последовательность операций для сборки приложений MFC](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Последовательность операций при создании элементов управления ActiveX](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [Последовательность операций для создания приложений баз данных](../mfc/sequence-of-operations-for-creating-database-applications.md)