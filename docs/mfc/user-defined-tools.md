---
title: "Пользовательские инструменты | Документы Microsoft"
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
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17f0751a2cb3f78730ec948d737dc99b85c2e735
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="user-defined-tools"></a>Инструменты, определяемые пользователем
MFC поддерживает определенные пользователем инструменты. Определяемый пользователем инструмент является специальная команда, выполняющая программу внешних, определяемый пользователем. Процесс настройки можно использовать для управления определенные пользователем инструменты. Однако нельзя использовать этот процесс, если объекта приложения не является производным от [CWinAppEx класс](../mfc/reference/cwinappex-class.md). Дополнительные сведения о настройке см. в разделе [Настройка для MFC](../mfc/customization-for-mfc.md).  
  
 Если вы включили поддержку определенные пользователем инструменты, диалоговое окно настроек автоматически включает **средства** вкладки. На следующем рисунке показана **средства** страницы.  
  
 ![Вкладки средства в диалоговом окне настройки](../mfc/media/custdialogboxtoolstab.png "custdialogboxtoolstab")  
Настройки на вкладке средства диалогового окна  
  
## <a name="enabling-user-defined-tools-support"></a>Включение пользовательских средств поддержки  
 Чтобы включить определенные пользователем инструменты в приложении, вызовите [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools). Тем не менее сначала необходимо определить несколько констант в файлах ресурсов приложения для использования в качестве параметров для этого вызова.  
  
 В редакторе ресурсов создайте фиктивный команду, которая использует идентификатор соответствующую команду. В следующем примере мы используем **ID_TOOLS_ENTRY** как идентификатор команды. Этот идентификатор команды отмечает расположение в одном или нескольких меню, где платформа будет вставлять определенные пользователем инструменты.  
  
 Необходимо выделить несколько последовательных идентификаторов в таблице строк, представляющих определенные пользователем инструменты. Количество строк, которое выделено равно максимальному числу пользователей средств, которые пользователи могут определять. В следующем примере эти именованные **ID_USER_TOOL1** через **ID_USER_TOOL10**.  
  
 Можно предложить пользователям, чтобы помочь им выбрать каталоги и аргументы для внешних программ, которые будут вызываться в качестве средства. Чтобы сделать это, создайте два всплывающее меню в редакторе ресурсов. В следующем примере эти именованные **IDR_MENU_ARGS** и **IDR_MENU_DIRS**. Для каждой команды в этих меню определите строку в таблице строк вашего приложения. Идентификатор ресурса строки должен быть равен идентификатор команды.  
  
 Можно также создать класс, производный от [CUserTool класса](../mfc/reference/cusertool-class.md) для замены реализация по умолчанию. Чтобы сделать это, передать сведения среды выполнения для производного класса в качестве четвертого параметра в CWinAppEx::EnableUserTools вместо RUNTIME_CLASS ([CUserTool класса](../mfc/reference/cusertool-class.md)).  
  
 После определения соответствующих констант, вызовите [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) для включения пользовательских средств.  
  
 Следующий вызов метода показано, как использовать эти константы:  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]  
  
 В этом примере вкладке инструменты будут включены в **настройки** диалоговое окно. Платформа заменят любые команды, совпадает с Идентификатором команды **ID_TOOLS_ENTRY** ни в одном меню с набором средств в настоящее время определены пользователя каждый раз, когда пользователь открывает соответствующее меню. Идентификаторы команд **ID_USER_TOOL1** через **ID_USER_TOOL10** , зарезервированы для использования пользовательских средств. Класс [CUserTool класса](../mfc/reference/cusertool-class.md) обрабатывает вызовы пользовательских средств. На вкладке средство **настройки** диалоговое окно содержит кнопки справа от поля ввода аргумента и каталога для доступа к меню **IDR_MENU_ARGS** и **IDR_MENU_DIRS**. Когда пользователь выбирает команду из следующих меню, платформа добавляет соответствующее текстовое поле строки, которая содержит идентификатор ресурса равно идентификатор команды.  
  
### <a name="including-predefined-tools"></a>Включая стандартных инструментов  
 Если необходимо заранее определить некоторые средства при запуске приложения, необходимо переопределить [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) метод главного окна приложения. В этом методе необходимо выполнить следующие действия.  
  
##### <a name="to-add-new-tools-in-loadframe"></a>Чтобы добавить новые средства в LoadFrame  
  
1.  Получение указателя на [класса CUserToolsManager](../mfc/reference/cusertoolsmanager-class.md) путем вызова метода [CWinAppEx::GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager).  
  
2.  Каждое средство, который вы хотите создать, вызовите [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool). Этот метод возвращает указатель на [CUserTool класс](../mfc/reference/cusertool-class.md) объекта и добавляет только что созданного пользователя средства внутренней коллекции средств. Если введенные данные среды выполнения для производного класса от [класса CUserTool](../mfc/reference/cusertool-class.md) как четвертый параметр [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools), [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool) будет создать экземпляр и вместо этого следует возвращать экземпляр этого класса.  
  
3.  Для каждого средства необходимо установить его текстовая метка, задав `CUserTool::m_strLabel` и установить ее команды путем вызова `CUserTool::SetCommand`. Реализация по умолчанию [класса CUserTool](../mfc/reference/cusertool-class.md) автоматически извлекает доступных значков из программы, указанной в вызове `SetCommand`.  
  
## <a name="see-also"></a>См. также  
 [Настройка для MFC](../mfc/customization-for-mfc.md)   
 [Класс CUserTool](../mfc/reference/cusertool-class.md)   
 [Класс CUserToolsManager](../mfc/reference/cusertoolsmanager-class.md)   
 [Класс CWinAppEx](../mfc/reference/cwinappex-class.md)




