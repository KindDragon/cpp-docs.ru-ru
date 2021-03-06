---
title: "Выравнивание элементов управления по направляющей | Документы Microsoft"
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
- DLUs (dialog units)
- controls [C++], aligning
- Dialog editor, snap to guides
- guides, tick mark interval
- dialog box controls, placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eed9acf533939d305e42478bb87307bc0a055d3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="aligning-controls-on-a-guide"></a>Выравнивание элементов управления по направляющей
Маркеры изменения размера элементов управления привязываются к направляющим при перемещении элементов управления, а направляющие привязываются к элементам управления (если они не элементов управления, ранее привязанных к руководству). При перемещении руководства элементы управления, привязанные к нему переместить также. Элементы управления привязаны к несколько структур изменяется при перемещении одной из направляющих.  
  
 Деления линейки, задающие размещение направляющих и элементов управления определяются единицы диалогового (окна DLU). Единица зависит от размера шрифта диалогового, обычно 8 точек MS Shell Dlg. Горизонтальная Единица диалогового окна — Средняя Ширина шрифта диалогового деленная на четыре. Вертикальная Единица диалогового окна — это средняя высота шрифта, деленная на восемь.  
  
### <a name="to-size-a-group-of-controls-with-guides"></a>Чтобы изменить размер группы элементов управления с направляющими  
  
1.  Привяжите одну сторону элемента управления (или элементов управления) к руководству.  
  
2.  Перетащите направляющую на другую сторону элемента управления (или элементов управления).  
  
     При необходимости с несколькими элементами управления, размер каждого, чтобы привязать к второй направляющей.  
  
3.  Переместите любую направляющую, чтобы изменить размер элемента управления (или элементов управления).  
  
### <a name="to-change-the-intervals-of-the-tick-marks"></a>Чтобы изменить интервал делений  
  
1.  Из **формат** меню, выберите **параметры направляющих**.  
  
2.  В [диалоговое окно "Параметры направляющих"](../windows/guide-settings-dialog-box.md)в **интервал между линиями сетки** укажите новую ширину и высоту в единицах диалогового окна.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Состояния редактора диалоговых окон (направляющие и сетки)](../windows/dialog-editor-states-guides-and-grids.md)   
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)

