---
title: "ASP, мастер компонентов страницы активного сервера ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.asp.asp
dev_langs:
- C++
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69d3837cc0996c0e0e0784214cfbfa6744afbf94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP, мастер компонентов страницы активного сервера ATL
Эта страница мастер компонентов ATL Active Server страница используется для указания дополнительных параметров для обработки информации и состояний, связанных с компонентами ASP.  
  
 **Необязательные методы**  
 Добавляет необязательные методы ASP **OnStartPage** и **OnEndPage**, в объект. Необходимо выбрать этот параметр, чтобы установить все встроенные объекты Active Server Pages. По умолчанию он выбран.  
  
-   **OnStartPage или OnEndPage** [OnStartPage](https://msdn.microsoft.com/library/ms691624.aspx) вызывается в первый раз, скрипт пытается получить доступ к объекту. **OnEndPage** вызывается, когда объект заканчивает обработку скрипта.  
  
 **Встроенный объект**  
 Необходимо выбрать **OnStartPage или OnEndPage** параметр, чтобы установить все встроенные объекты ASP.  
  
|Параметр|Описание:|  
|------------|-----------------|  
|**Запрос**|Предоставляет доступ к встроенная функция Active Server Pages **запроса** объекта. Объект запроса используется для передачи HTTP-запроса.|  
|**Ответ**|Предоставляет доступ к встроенная функция Active Server Pages **ответ** объекта. В ответ на запрос объект Response передает данные в браузер должен отображать для пользователя.|  
|**Сеанс**|Предоставляет доступ к встроенная функция Active Server Pages **сеанса** объекта. **Сеанса** объект сохраняет сведения о сеансе текущего пользователя, хранит и получает сведения о состоянии.|  
|**Приложение**|Предоставляет доступ к встроенная функция Active Server Pages **приложения** объекта. **Приложения** управляет состояние, которое является общим множества объектов ASP.|  
|**Сервер**|Предоставляет доступ к встроенная функция Active Server Pages **сервера** объекта. **Сервера** позволяет создавать другие объекты ASP.|  
  
## <a name="see-also"></a>См. также  
 [Мастер компонентов страницы активного сервера ATL](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [Компонентов страницы активного сервера ATL](../../atl/reference/adding-an-atl-active-server-page-component.md)

