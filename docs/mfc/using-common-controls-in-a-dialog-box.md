---
title: "Использование стандартных элементов управления в диалоговом окне | Документы Microsoft"
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
- common controls [MFC], in dialog boxes
- dialog box controls [MFC], common controls
- Windows common controls [MFC], in dialog boxes
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 67a9c77e6a8e5721bca6e3741b4b337cfdb42393
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-common-controls-in-a-dialog-box"></a>Использование стандартных элементов управления в диалоговом окне
Общие элементы управления Windows можно использовать в [диалоговым окнам](../mfc/dialog-boxes.md), образуют представления записей и любое другое окно, на основе шаблона диалогового окна. Для форм, а также будет работать следующую процедуру с незначительными изменениями.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-use-a-common-control-in-a-dialog-box"></a>Для использования стандартного элемента управления в диалоговое окно  
  
1.  Поместить элемент управления в шаблоне диалогового окна [с помощью редактора диалоговых окон](../mfc/using-the-dialog-editor-to-add-controls.md).  
  
2.  Добавьте в класс диалоговых окон переменную-член, представляющий элемент управления. В **добавления переменной-члена** диалоговом проверка **управляющей переменной** и убедитесь, что **управления** выбран для **категории**.  
  
3.  Если этот общий элемент управления предоставляет входные данные для программы, объявите дополнительный элемент variable(s) в классе диалогового окна для обработки тех входных значений.  
  
    > [!NOTE]
    >  Можно добавить эти переменные-члены с помощью контекстного меню в представлении классов (см. [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)).  
  
4.  В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) для класса диалогового окна, задайте начального условия для стандартного элемента управления. Использование переменной-члена, созданные на предыдущем шаге, используйте функции-члены для задания начального значения и другие параметры. О параметрах см. следующие описания элементов управления, Дополнительные сведения.  
  
     Можно также использовать [обмен данными диалоговых окон](../mfc/dialog-data-exchange-and-validation.md) окон (DDX) для инициализации элементов управления в диалоговом окне.  
  
5.  В обработчиках для элементов управления в диалоговом окне используйте переменную-член работать с элементом управления. Следующие описания элементов управления, Дополнительные сведения см. в методах.  
  
    > [!NOTE]
    >  Переменная-член будет существовать только при условии, что существует самого окна. Вы не сможете запрашивать элемент управления для входных значений после закрытия диалогового. Для работы с входные значения из стандартного элемента управления, переопределите `OnOK` в класс диалогового окна. Во время переопределения запрос к элементу управления для входных значений и сохранить эти значения в переменные-члены класса диалогового окна.  
  
    > [!NOTE]
    >  Обмен данными диалоговых окон также можно использовать для задания или получения значений из элементов управления в диалоговом окне.  
  
## <a name="remarks"></a>Примечания  
 Добавление некоторых общих элементов управления в диалоговое приведет к прекращению работы диалоговое окно. Ссылаться на [Добавление элементов управления в диалоговое окно приводит к функции больше не диалогового окна](../windows/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md) Дополнительные сведения об обработке такой ситуации.  
  
## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать  
  
-   [Добавление элементов управления в диалоговое окно вручную вместо с помощью редактора диалоговых окон](../mfc/adding-controls-by-hand.md)  
  
-   [Является производным элемента управления из одного из стандартных общих элементов управления Windows](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [Использование общего элемента управления как дочернего окна](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [Получение уведомлений из элемента управления](../mfc/receiving-notification-from-common-controls.md)  
  
-   [Использовать обмен данными (диалоговых окон DDX)](../mfc/dialog-data-exchange-and-validation.md)  
  
## <a name="see-also"></a>См. также  
 [Создание и использование элементов управления](../mfc/making-and-using-controls.md)   
 [Элементы управления](../mfc/controls-mfc.md)

