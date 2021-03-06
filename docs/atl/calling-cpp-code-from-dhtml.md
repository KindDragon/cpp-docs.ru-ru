---
title: "Вызов кода C++ из DHTML | Документы Microsoft"
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
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e2d0da431249ef886ceca1e2b7f6cbfc99418dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="calling-c-code-from-dhtml"></a>Вызов кода C++ из DHTML
Элемент управления DHTML может размещаться в контейнер, например тестовый контейнер или Internet Explorer. В разделе [тестирование свойств и событий с использованием тестового контейнера](../mfc/testing-properties-and-events-with-test-container.md) сведения о том, как получить доступ к контейнеру теста.  
  
 Контейнер, размещение элемента управления взаимодействует с элементом управления с помощью интерфейсов обычный элемент управления. DHTML использует интерфейс диспетчеризации, которое заканчивается на «UI», для взаимодействия с кодом C++ и ресурс HTML. В [изменения элемента управления ATL DHTML](../atl/modifying-the-atl-dhtml-control.md), Показать Добавление методов будет вызвана эти различные интерфейсы.  
  
 Чтобы увидеть пример вызова кода C++ из DHTML, [Создание элемента управления DHTML](../atl/creating-an-atl-dhtml-control.md) с помощью мастера элементов управления ATL и проверьте такой код в файле заголовка, а также в HTML-файле.  
  
## <a name="declaring-webbrowser-methods-in-the-header-file"></a>Объявления методов веб-браузер, в файле заголовка  
 Для вызова методов C++ в пользовательском Интерфейсе DHTML, необходимо добавить методы для элемента управления пользовательского интерфейса. Например, файл заголовка, создаваемые с помощью мастера элементов управления ATL содержит метод C++ `OnClick`, который входит в состав пользовательского интерфейса мастера создания элемента управления.  
  
 Изучите `OnClick` в h-файл элемента управления:  
  
 [!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]  
  
 Первый параметр `pdispBody`, является указателем на интерфейс диспетчеризации объектом тела. Второй параметр `varColor`, определяющий цвет, который будет применен к элементу управления.  
  
## <a name="calling-c-code-in-the-html-file"></a>Вызов кода C++ в HTML-файле  
 После объявления методов веб-браузер, в файле заголовка можно вызывать методы из HTML-файла. Обратите внимание, в HTML-файл, мастер элементов управления ATL вставляет три метода диспетчеризации Windows: три `OnClick` методы, которые отправляют сообщения, чтобы изменить цвет фона элемента управления.  
  
 Ознакомьтесь с одним из методов в HTML-файле.  
  
 `<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`  
  
 В коде HTML выше внешнего метода окна `OnClick`, вызывается как часть тег кнопки. Метод имеет два параметра: `theBody`, ссылки, которые body документа HTML и `"red"`, указывающая, что цвет фона элемента управления будет изменен на красный при нажатии кнопки. `Red` После тега — Метка кнопки.  
  
 В разделе [изменения элемента управления ATL DHTML](../atl/modifying-the-atl-dhtml-control.md) Дополнительные сведения о предоставлении собственных методов. В разделе [определения элементов проекта элемента управления DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md) Дополнительные сведения о HTML-файл.  
  
## <a name="see-also"></a>См. также  
 [Поддержка элементов управления DHTML](../atl/atl-support-for-dhtml-controls.md)

