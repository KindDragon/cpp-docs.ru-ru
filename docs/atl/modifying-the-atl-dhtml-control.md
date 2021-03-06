---
title: "Изменение элемента управления ATL DHTML | Документы Microsoft"
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
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 571b7f4f52e3f6838822db39ba0bbf5148d57d1e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="modifying-the-atl-dhtml-control"></a>Изменение элемента управления ATL DHTML
Мастер элементов управления ATL предоставляет начальный код, поэтому можно собрать и запустить элемент управления, поэтому можно увидеть, как методы записываются в файлы проекта и как DHTML вызывается в коде C++ элемент управления, с помощью методов распределения. Любой метод распределения можно добавить к интерфейсу. Затем можно вызывать методы в HTML-ресурса.  
  
#### <a name="to-modify-the-atl-dhtml-control"></a>Для изменения элемента управления ATL DHTML  
  
1.  В представлении класса разверните проект элемента управления.  
  
     Обратите внимание, что интерфейс, который заканчивается на «UI» содержит один метод `OnClick`. Интерфейс, который не оканчивается на «UI» не имеет никаких методов.  
  
2.  Добавьте метод с именем `MethodInvoked` интерфейс, который не оканчивается на «UI».  
  
     Этот метод будет добавлен на интерфейс, который используется в контейнере элемента управления для взаимодействия с контейнером, не на интерфейс, используемый DHTML для взаимодействия с элементом управления. Этот метод может вызываться только в контейнере.  
  
3.  Найдите метод усеченные в CPP-файл и добавьте код для отображения окна сообщения, например:  
  
 [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]  
  
4.  Добавьте другой метод с именем `HelloHTML`, только на этот раз добавьте его к интерфейсу, который заканчивается на «UI». Найти усеченные `HelloHTML` метод в расширением CPP и добавьте код для отображения окна сообщения, например:  
  
 [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]  
  
5.  Добавьте третий метод `GoToURL`, интерфейс, который не оканчивается на «UI». Реализуйте этот метод, вызвав [IWebBrowser2::Navigate](https://msdn.microsoft.com/library/aa752133.aspx), как показано ниже:  
  
 [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]  
  
     Можно использовать **IWebBrowser2** методы так, как библиотека ATL предоставляет указатель на интерфейс для вас в вашей h-файле.  
  
 Далее следует измените ресурс HTML для вызова методов, которые вы создали. Вы добавите три кнопки для вызова этих методов.  
  
#### <a name="to-modify-the-html-resource"></a>Изменение ресурса HTML  
  
1.  В обозревателе решений дважды щелкните htm-файл для отображения HTML-ресурса.  
  
     Проверка, HTML, особенно вызовов внешних методов диспетчеризации Windows. HTML-код вызывает проекта `OnClick` метод и параметры указывают текст элемента управления (`theBody`) и цвет, который нужно назначить («`red`»). Текст, следующий вызов метода — метка, которая отображается на кнопке.  
  
2.  Добавьте еще один `OnClick` метод только изменить цвет. Пример:  
  
 ```  
 <br>  
 <br>  
 <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>  
 ```  
  
     Этот метод создаст имеется кнопка, **обновление**, что пользователь может щелкнуть для возврата исходного, белый фон элемента управления.  
  
3.  Добавьте вызов `HelloHTML` созданным методом. Пример:  
  
 ```  
 <br>  
 <br>  
 <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>  
 ```  
  
     Этот метод создаст имеется кнопка, **HelloHTML**, который пользователь может щелкнуть для отображения `HelloHTML` окно сообщения.  
  
 Теперь можно построить и [проверки измененного элемента управления DHTML](../atl/testing-the-modified-atl-dhtml-control.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка элементов управления DHTML](../atl/atl-support-for-dhtml-controls.md)

