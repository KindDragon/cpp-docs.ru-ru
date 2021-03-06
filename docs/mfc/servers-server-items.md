---
title: "Серверы: Элементы сервера | Документы Microsoft"
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
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2fe196eb561c336e45402de6c390146a0d77bea4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="servers-server-items"></a>Серверы. Элементы сервера
Когда контейнер запускает сервер, чтобы пользователь может изменить элемент внедренного или связанного OLE, серверное приложение создает «элемента сервера». Серверный элемент, который представляет собой объект класса, производного от `COleServerItem`, предоставляет интерфейс между серверного документа и приложения-контейнера.  
  
 `COleServerItem` Класс определяет несколько функций переопределяемый член, вызываемыми OLE, обычно в ответ на запросы из контейнера. Элементы сервера может представлять часть серверного документа или весь документ. При внедрении элемента OLE в документе-контейнере, серверный элемент представляет документ всего сервера. При связывании объекта OLE, серверный элемент может представлять части серверного документа или весь документ, в зависимости от того, является ли ссылка к части или целого.  
  
 В [HIERSVR](../visual-cpp-samples.md) выборки, например, класс элемента сервера **CServerItem**, содержит элемент, являющийся указателем на объект класса **CServerNode**. **CServerNode** объекта является узлом приложения HIERSVR документ, который представляет собой дерево. Когда **CServerNode** объект является корневым узлом, **CServerItem** представляет весь документ. Когда **CServerNode** объект является дочерним для узла, **CServerItem** представляет часть документа. См. Образец MFC OLE [HIERSVR](../visual-cpp-samples.md) пример взаимодействия.  
  
##  <a name="_core_implementing_server_items"></a>Реализация элементы сервера  
 При использовании мастера приложений для получения кода «Начальная» для приложения, все, что нужно сделать, чтобы включить элементы сервера в начальный код — выберите один из параметров сервера на странице параметров OLE. При добавлении элементов сервера в существующее приложение, выполните следующие действия:  
  
#### <a name="to-implement-a-server-item"></a>Для реализации элемента сервера  
  
1.  Создайте производный класс от класса `COleServerItem`.  
  
2.  В производном классе, переопределять `OnDraw` функции-члена.  
  
     Платформа вызывает `OnDraw` для отрисовки элемента OLE в метафайл. Контейнер приложение использует этот метафайла для отрисовки элемента. Класс представления приложения также имеет `OnDraw` функция-член, который используется для отрисовки элемента, если серверное приложение активно.  
  
3.  Реализовать переопределение `OnGetEmbeddedItem` для класса серверного документа. Дополнительные сведения см. в статье [серверы: реализация документов сервера](../mfc/servers-implementing-server-documents.md) пример MFC OLE и [HIERSVR](../visual-cpp-samples.md).  
  
4.  Реализации класса своего элемента сервера `OnGetExtent` функции-члена. Платформа вызывает эту функцию для извлечения размер элемента. Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="_core_a_tip_for_server.2d.item_architecture"></a>Подсказки для элемента сервера архитектуры  
 Как отмечалось в [реализации элементы сервера](#_core_implementing_server_items), серверных приложений необходима возможность отображения элементов в режиме сервера и в метафайл используется приложением-контейнером. Библиотеки классов Microsoft Foundation архитектуру приложения, класс представления элемента `OnDraw` функции-члена отображает элемент, когда она редактируется (см. [CView::OnDraw](../mfc/reference/cview-class.md#ondraw) в *Справочник по библиотеке классов* ). Серверный элемент `OnDraw` отрисовывает элемент в метафайл во всех остальных случаях (в разделе [COleServerItem::OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)).  
  
 Избежать повторения кода, создав вспомогательные функции в вашем классе серверного документа и вызывать их из `OnDraw` функций в классах представление и элемента сервера. Пример MFC OLE [HIERSVR](../visual-cpp-samples.md) использует такую стратегию: функции **CServerView::OnDraw** и **CServerItem::OnDraw** обе вызывают **CServerDoc::DrawTree**  для отрисовки элемента.  
  
 Представление и элемент имеют `OnDraw` для функций-членов так, как они нарисуйте в различных условиях. Представление необходимо учитывать такие факторы, как масштабирование, выделенного фрагмента и экстента, обрезки и элементы пользовательского интерфейса, такие как полосы прокрутки. С другой стороны, серверный элемент всегда выводит весь объект OLE.  
  
 Дополнительные сведения см. в разделе [CView::OnDraw](../mfc/reference/cview-class.md#ondraw), [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerItem::OnDraw](../mfc/reference/coleserveritem-class.md#ondraw), и [COleServerDoc::OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)в *Справочник по библиотеке классов*.  
  
## <a name="see-also"></a>См. также  
 [Серверы](../mfc/servers.md)

