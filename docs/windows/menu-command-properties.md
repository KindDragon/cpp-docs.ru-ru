---
title: "Свойства команды меню | Документы Microsoft"
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
- menu items, properties
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 186790db57c20abf9f67f693ff60029257ebd4f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="menu-command-properties"></a>Свойства команды меню
Приведенные ниже сведения представлены в таком же виде, в каком отображаются свойства меню в [окне свойств](/visualstudio/ide/reference/properties-window) при выборе команды меню. Они перечислены в алфавитном порядке. В окне свойств эти сведения можно также просматривать с сортировкой по категориям.  
  
|Свойство.|Описание:|  
|--------------|-----------------|  
|**Break**|Допустимо одно из следующих значений.<br /><br /> -   **Нет** (по умолчанию): без разрыва.<br />-   **Столбец**. Для статических меню. Команда меню помещается в новую строку. В контекстных меню при этом значении команда меню помещается в новый столбец без разделительной линии между столбцами. Установка этого свойства влияет на внешний вид меню только во время выполнения. В редакторе внешний вид меню не меняется.<br />-   **Панель**. Аналогично варианту "столбец" за исключением того, что в контекстных меню при этом значении новый столбец отделяется от старого вертикальной линией. Установка этого свойства влияет на внешний вид меню только во время выполнения. В редакторе внешний вид меню не меняется.|  
|**Подпись**|Текст, представляющий команду меню (имя меню). Чтобы указать одну из букв названия команды меню как входящую в сочетание клавиш, поместите перед ней знак амперсанда (&).|  
|**Помечено**|Если задано значение True, у команды меню изначально установлен флажок. Тип — логический. Значение по умолчанию — False.|  
|**Включено**|Если задано значение **False**, пункт меню отключен.|  
|**Grayed (Серым цветом)**|Если задано значение True, команда меню изначально выделена серым цветом и неактивна. Тип — логический. Значение по умолчанию — False.|  
|**Справка**|Выравнивает пункт меню по правому краю. Например, команда меню **Справка** всегда находится справа во всех приложениях Windows. Если задано это свойство пункта меню, данный пункт будет отображаться прижатым к правому краю и в самом конце меню. Применяется к элементам верхнего уровня. Значение по умолчанию — **False**.|  
|**Идентификатор**|Этот символ определяется в файле заголовка. Тип: символ, целое число или строка в кавычках. Можно использовать любой символ, который обычно доступен в любом редакторе, даже если [окно свойств](/visualstudio/ide/reference/properties-window) не содержит раскрывающийся список для выбора этого символа.|  
|**Контекстное меню**|Если задано значение True, команда меню является всплывающим меню. Тип — логический. Значение по умолчанию: True — для меню верхнего уровня в строке меню, в противном случае — значение False.|  
|**Запрашивать**|Содержит текст, отображаемый в строке состояния, при выделении этой команды меню. Текст помещается в таблицу строк с тем же идентификатором, что и команда меню. Это свойство доступно для любого типа проекта, но во время выполнения проявляются особенности, зависящие от MFC.|  
|**Right to Left Justify (Выравнивание справа налево)**|Выравнивание команды меню по правому краю в строке меню во время выполнения. Тип — логический. Значение по умолчанию — False.|  
|**Right to Left Order (Справа налево)**|Отображение команд меню справа налево в тех случаях, когда интерфейс локализован для языка с направлением чтения справа налево, например, иврита или арабского языка.|  
|**Separator**|Если задано значение True, команда меню является разделителем. Тип — логический. Значение по умолчанию — False.|  
  

  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактор меню](../windows/menu-editor.md)