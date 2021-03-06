---
title: "Архитектуру представления документов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CView class [MFC], view architecture
- CDocument class [MFC]
- MFC, views
- views [MFC], MFC document/view model
- document objects [MFC]
- document objects [MFC], MFC document/view model
- MFC, documents
- documents [MFC], MFC document/view model
- document objects [MFC], document/view architecture
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 45c595b78b17ed00691533369ec4837345fcce03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="documentview-architecture"></a>Архитектура "документ-представление"
По умолчанию мастер приложений MFC создает основу для приложений с класс документа и класс представления. MFC разделяет управление данными в этих двух классов. Документ хранит данные и управляет печать данных и координирует обновления нескольких представлений данных. Представление отображает данные и управляет взаимодействием пользователя с ним, включая выбор и изменение.  
  
 В этой модели объекта документа MFC считывает и записывает данные в постоянное хранилище. Документ также может предоставлять интерфейс к данным, везде, где она находится (например, как в базе данных). Объект отдельное представление управляет отображением данных в отображении данных в окне на выбор пользователя и изменение данных. Представление получает отображают данные из документа и взаимодействует в документ любые изменения данных.  
  
 Можно легко переопределить или игнорировать разделение документов и представлений, существуют веских причин этой модели, в большинстве случаев. Одна из наиболее — при необходимости несколько представлений одного документа, например, электронной таблицы и представления диаграммы. Объект отдельное представление представляют каждое представление данных, а код, общие для всех представлений (например, ядро вычисления) может находиться в документе с помощью модели документов и представлений. Документ также принимает задачу обновления всех представлений при каждом изменении данных.  
  
 Архитектурой документ/представление MFC позволяет легко поддерживать несколько представлений, несколько типов документов, окна разделителей и другие функции ценные пользовательского интерфейса.  
  
 Элементы структуры MFC макрос наиболее видимой для пользователя и вы программист, — это документов и представлений. Большая часть работы по разработке приложения с помощью платформы переходит в записи документа и представления классов. Описание этого семейства статьи:  
  
-   В целях документов, представлений и их взаимодействие в платформе.  
  
-   Что необходимо сделать для их реализации.  
  
 Основа документов и представлений приведены четыре основные классы.  
  
 [CDocument](../mfc/reference/cdocument-class.md) (или [COleDocument](../mfc/reference/coledocument-class.md)) класс поддерживает объекты, используемые для хранения и управления данных программы и обеспечивает базовую функциональность для классов определенной документа. Документ представляет собой единицу данных, пользователь обычно открывается с помощью команды Открыть в меню файл и сохраняет с помощью команды "Сохранить" в меню "файл".  
  
 [CView](../mfc/reference/cview-class.md) (или один из многих производные классы) обеспечивает базовую функциональность для классов представления, определяемые программистом. Представление прикрепляемые к документу и действует как посредник между документом и пользователь: представление отображает изображение документа на экране и интерпретирует как операции после документа ввод данных пользователем. Представление также отображает изображение, чтобы печать и предварительный просмотр.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md) (или один из его вариантов) поддерживает объекты, которые предоставляет рамку вокруг одного или нескольких представлений документа.  
  
 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) (или [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) или [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)) поддерживает объект, который координирует один или несколько существующих документов данного типа и управляет ими, создание соответствующих документ, представления и объекты окон фрейма для этого типа.  
  
 На следующем рисунке показана связь между документом и его представление.  
  
 ![Представление является частью документа, который отображается](../mfc/media/vc379n1.gif "vc379n1")  
Документа и представления  
  
 Реализация документов и представлений в библиотеке классов Отделяет сами данные из своего отображения и операции с данными пользователя. Все изменения данных осуществляется через класс документа. Представление вызывает этот интерфейс для доступа и обновления данных.  
  
 Документы, их связанных с ним представлений и фреймов, фрейма представления создаются шаблоном документа. Шаблон документа отвечает за создание и управление ими все документы один тип документа.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Портрет архитектуры "документ представление"](../mfc/a-portrait-of-the-document-view-architecture.md)  
  
-   [Преимущества архитектуры "документ представление"](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Классы документа и представления, созданные с помощью мастера приложений](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)  
  
-   [Альтернативы для архитектуры "документ представление"](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [Добавление нескольких представлений в один документ](../mfc/adding-multiple-views-to-a-single-document.md)  
  
-   [Использование документов](../mfc/using-documents.md)  
  
-   [Использование представлений](../mfc/using-views.md)  
  
-   [Множественные типы документов, представления и окна фреймов](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
-   [Инициализировать добавления пользователя в документ и представление классов](../mfc/creating-new-documents-windows-and-views.md)  
  
-   [Использование классов базы данных с документами и представлениями](../data/mfc-using-database-classes-with-documents-and-views.md)  
  
-   [Использование классов базы данных без документов и представлений](../data/mfc-using-database-classes-without-documents-and-views.md)  
  
-   [Примеры](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)   
 [Windows](../mfc/windows.md)   
 [Окна фрейма](../mfc/frame-windows.md)   
 [Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Создание документа или представления](../mfc/document-view-creation.md)   
 [Создание документов, окон и представлений](../mfc/creating-new-documents-windows-and-views.md)

