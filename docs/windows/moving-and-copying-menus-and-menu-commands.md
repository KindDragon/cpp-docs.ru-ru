---
title: "Перемещение и копирование меню и команды меню | Документы Microsoft"
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
- commands, copying on menus
- menu items, moving
- commands, moving on menus
- menu items, copying
ms.assetid: 1d8df535-9922-4579-a9c2-37aeac1856eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6042647d0eff213dae82440b9733cff64e94631
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="moving-and-copying-menus-and-menu-commands"></a>Перемещение и копирование меню и команд меню
Вы можете перемещать или копировать меню и команды меню с помощью метода перетаскивания или с помощью команд контекстного меню (щелкните правой кнопкой мыши меню).  
  
### <a name="to-move-or-copy-menus-or-menu-commands-using-the-drag-and-drop-method"></a>Перемещение или копирование меню или команд меню с помощью метода перетаскивания  
  
1.  Перетащите или скопируйте элемент, который требуется переместить.  
  
    -   Новое расположение в текущем меню.  
  
    -   Другое меню. (Можно перейти к другим меню, перетащив на них указатель мыши.)  
  
2.  Удалите команды меню, когда направляющая покажет нужное положение.  
  
### <a name="to-move-or-copy-menus-or-menu-commands-using-shortcut-menu-commands"></a>Перемещение или копирование меню или команд меню с помощью команд контекстного меню  
  
1.  Щелкните правой кнопкой мыши одно или несколько меню или команд меню.  
  
2.  В контекстном меню выберите **Вырезать** (для перемещения) или **Копировать**.  
  
3.  При перемещении элементов в другой ресурс меню ресурса или файл описания ресурсов [откройте его в другом окне](/visualstudio/ide/customizing-window-layouts-in-visual-studio).  
  
4.  Выберите положение меню или команды меню, которую нужно переместить или скопировать.  
  
5.  Выберите в контекстном меню команду **Вставить**. Перемещенный или скопированный пункт помещается перед выбранным пунктом.  
  
    > [!NOTE]
    >  Вы также можете перетаскивать, копировать и вставлять в другие меню в других окнах меню.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактор меню](../windows/menu-editor.md)