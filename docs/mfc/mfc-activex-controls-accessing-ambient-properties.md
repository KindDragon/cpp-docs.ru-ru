---
title: "Элементы управления ActiveX MFC: Доступ к свойствам окружения | Документы Microsoft"
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
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b05e6d37a0550cf157dcd43a22689c9db029b51f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>Элементы управления ActiveX в MFC. Доступ к свойствам окружения
В этой статье рассматриваются как доступ к свойствам окружения контейнера элемента управления для элемента управления ActiveX.  
  
 Доступ к свойствам окружения контейнера элемента управления можно получить сведения о его контейнера. Эти свойства предоставляют визуальные характеристики, такие как цвет фона контейнера, текущего шрифта, используемые при помощи контейнера и рабочие характеристики, такие как ли контейнер в настоящий момент в пользовательском режиме или в режиме конструктора. Элемент управления может использовать внешние свойства для настройки внешнего вида и поведения для конкретного контейнера, в который он внедрен. Тем не менее элемент управления никогда не следует предполагать, контейнера будут поддерживать любого конкретного свойства окружения. На самом деле некоторые контейнеры могут не поддерживать все свойства окружения вообще. В случае отсутствия внешнее свойство элемента управления должен принимать разумное значение по умолчанию.  
  
 Для доступа к внешним, вызвать [COleControl::GetAmbientProperty](../mfc/reference/colecontrol-class.md#getambientproperty). Эта функция ожидает идентификатор диспетчера для свойства окружения в качестве первого параметра (файл OLECTL. H определяет коды обработки стандартный набор свойствам окружения).  
  
 Параметры `GetAmbientProperty` функции являются идентификатор dispatch ID variant тег, указывающее, ожидаемый тип свойства и указатель на область памяти, где должно быть возвращено значение. Тип данных, к которому относится этот указатель будет зависеть от variant тег. Функция возвращает **TRUE** Если контейнер поддерживает свойство, в противном случае он возвращает **FALSE**.  
  
 В следующем примере получается значение свойства окружения, называется «UserMode». Если свойство не поддерживается в качестве контейнера, значение по умолчанию **TRUE** предполагается:  
  
 [!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]  
  
 Для удобства `COleControl` предоставляет вспомогательные функции, доступ ко многим часто используемые свойства окружения и возвращающие значения по умолчанию, если свойства недоступны. Эти вспомогательные функции выглядят следующим образом:  
  
-   [COleControl::AmbientBackColor](../mfc/reference/colecontrol-class.md#ambientbackcolor)  
  
-   [AmbientDisplayName](../mfc/reference/colecontrol-class.md#ambientdisplayname)  
  
-   [AmbientFont](../mfc/reference/colecontrol-class.md#ambientfont)  
  
    > [!NOTE]
    >  Вызывающий объект должен вызвать **выпуска ()** возвращаемый шрифта.  
  
-   [AmbientForeColor](../mfc/reference/colecontrol-class.md#ambientforecolor)  
  
-   [AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)  
  
-   [AmbientScaleUnits](../mfc/reference/colecontrol-class.md#ambientscaleunits)  
  
-   [AmbientTextAlign](../mfc/reference/colecontrol-class.md#ambienttextalign)  
  
-   [AmbientUserMode](../mfc/reference/colecontrol-class.md#ambientusermode)  
  
-   [AmbientUIDead](../mfc/reference/colecontrol-class.md#ambientuidead)  
  
-   [AmbientShowHatching](../mfc/reference/colecontrol-class.md#ambientshowhatching)  
  
-   [AmbientShowGrabHandles](../mfc/reference/colecontrol-class.md#ambientshowgrabhandles)  
  
 При изменении значения свойства окружающей среды (через какое-либо действие контейнера), **OnAmbientPropertyChanged** вызове функции-члена элемента управления. Переопределите эту функцию-член для обработки такого уведомления. Параметр для **OnAmbientPropertyChanged** идентификатор диспетчеризации измененное свойство окружения. Возможно, значение этого идентификатора диспетчеризации **DISPID_UNKNOWN**, указывающая, что одно или несколько свойств внешнего изменилось, но сведения о том, какие свойства были затронуты недоступна.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

