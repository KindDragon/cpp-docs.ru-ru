---
title: "Обновление текса на панели строки состояния | Документы Microsoft"
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
- updating user interface objects [MFC]
- ON_UPDATE_COMMAND_UI macro [MFC]
- user interface objects [MFC], updating
- text, status bar
- CStatusBar class [MFC], updating
- SetText method [MFC]
- panes, status bar
- status bars [MFC], updating
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0fb0f9bdaa032340256eee4781bfd775767f62ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>Обновление текса на панели строки состояния
В этой статье объясняется, как изменить текст, отображаемый в панели строки состояния MFC. Строка состояния — объект window класса [CStatusBar](../mfc/reference/cstatusbar-class.md) — содержит несколько «областей». Каждая область — прямоугольной области строки состояния, можно использовать для отображения информации. Например во многих приложениях отображать состояние CAPS LOCK, NUM LOCK и другие ключи в крайней правой области. Приложения часто также отображаются информативные текста в левой панели (0), иногда называется «панель сообщений». Например строки состояния MFC по умолчанию использует панель сообщений для отображения строка, объясняющая выбранного пункта меню или панели инструментов кнопки. Рисунок в [строки состояния](../mfc/status-bar-implementation-in-mfc.md) показывает строку состояния из приложения, созданные с помощью мастера приложений MFC.  
  
 По умолчанию не поддерживает MFC `CStatusBar` области при создании области. Чтобы активировать область, необходимо использовать `ON_UPDATE_COMMAND_UI` макрос для каждой области состояния панели и обновления панелей. Так как не отправлять панелей **WM_COMMAND** сообщений (они не похожи на кнопки панели инструментов), необходимо вручную ввести код.  
  
 Предположим, что одной из панелей имеет `ID_INDICATOR_PAGE` как его идентификатор команды и что он содержит номер текущей страницы документа. Следующая процедура описывает создание новой области в строке состояния.  
  
### <a name="to-make-a-new-pane"></a>Чтобы сделать новую область  
  
1.  Определить идентификатор панели команд.  
  
     На **представление** меню, нажмите кнопку **представление ресурсов**. Щелкните правой кнопкой мыши ресурс проекта и нажмите кнопку **символы ресурсов**. В диалоговом окне "символы ресурсов" щелкните `New`. Введите имя идентификатора команды: например, `ID_INDICATOR_PAGE`. Укажите значение для идентификатора, или примите значение предложенными диалоговое окно "символы ресурсов". Например, для `ID_INDICATOR_PAGE`, примите значение по умолчанию. Закройте диалоговое окно "символы ресурсов".  
  
2.  Определите строку по умолчанию для отображения в области.  
  
     Откройте представление ресурсов, дважды щелкните **таблица строк** в окне, которое содержит список типов ресурсов для вашего приложения. С **таблица строк** редактор открыт, выберите **новую строку** из **вставить** меню. В окне свойств строки выберите идентификатор команды в своей области (например, `ID_INDICATOR_PAGE`) и введите строковое значение по умолчанию, например «Страница». Закройте редактор строк. (Вам нужна строка по умолчанию, чтобы избежать ошибки компилятора.)  
  
3.  Добавление панели к **индикаторы** массива.  
  
     В файле MAINFRM. CPP, найдите **индикаторы** массива. Этот массив содержит идентификаторы команд для всех показателей в строке состояния, в порядке слева направо. На соответствующую точку в массиве, введите идентификатор команды в своей области, как показано ниже, для `ID_INDICATOR_PAGE`:  
  
     [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]  
  
 Для отображения текста в области рекомендуется вызывать **SetText** функции-члена класса `CCmdUI` в функции обработчика обновления для области. Например, может потребоваться настроить целочисленная переменная `m_nPage` , содержащее номер текущей страницы и используйте **SetText** присваивается текст панели строковую версию этого числа.  
  
> [!NOTE]
>  **SetText** подход является рекомендуемым. Это возможно, для выполнения этой задачи на несколько более низкий уровень, вызвав `CStatusBar` функции-члена `SetPaneText`. Тем не менее по-прежнему необходимо обработчика обновлений. Без такой обработчик для области MFC автоматически отключает области, удаляя его содержимого.  
  
 Ниже показано, как использовать функцию обработчика обновления для отображения текста в области.  
  
#### <a name="to-make-a-pane-display-text"></a>Чтобы сделать область отображения текста  
  
1.  Добавьте обработчик команды обновления для команды.  
  
     Вручную добавьте прототип для обработчика, как показано ниже для `ID_INDICATOR_PAGE` (в MAINFRM. H):  
  
     [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]  
  
2.  В соответствующий. CPP файлов, добавьте определение обработчика, как показано ниже для `ID_INDICATOR_PAGE` (в MAINFRM. CPP):  
  
     [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]  
  
     Последние три строки этого обработчика, представляют собой код, который отображает текст.  
  
3.  В сопоставлении соответствующее сообщение, добавьте `ON_UPDATE_COMMAND_UI` макросов, как показано ниже для `ID_INDICATOR_PAGE` (в MAINFRM. CPP):  
  
     [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]  
  
 После определения значения `m_nPage` переменную-член (класса `CMainFrame`), этот метод вызывает номер страницы для отображения в области во время обработки бездействия таким же образом, что приложение обновляет другие показатели. Если `m_nPage` изменения, отображаемое во время следующего цикла простоя.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Обновление объектов пользовательского интерфейса (как в обновлении кнопки панели инструментов и элементы меню, изменение условий программы)](../mfc/how-to-update-user-interface-objects.md)  
  
## <a name="see-also"></a>См. также  
 [Реализация строки состояния в MFC](../mfc/status-bar-implementation-in-mfc.md)   
 [Класс CStatusBar](../mfc/reference/cstatusbar-class.md)
