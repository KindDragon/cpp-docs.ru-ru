---
title: "Класс COleResizeBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
dev_langs:
- C++
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0cc0b9f85392a69191ee3c948985c61bd2d1f494
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coleresizebar-class"></a>Класс COleResizeBar
Тип панели элементов управления, который поддерживает изменение размера элементов OLE "на месте".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleResizeBar::COleResizeBar](#coleresizebar)|Создает объект `COleResizeBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleResizeBar::Create](#create)|Создает и инициализирует дочернее окно Windows и связывает его `COleResizeBar` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COleResizeBar`объекты отображаются в виде [CRectTracker](../../mfc/reference/crecttracker-class.md) со штриховой границей и внешней маркеры изменения размера.  
  
 `COleResizeBar`объекты являются элементами обычно внедренных объектов окна фрейма, производных от [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) класса.  
  
 Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="coleresizebar"></a>COleResizeBar::COleResizeBar  
 Создает объект `COleResizeBar`.  
  
```  
COleResizeBar();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите **создать** для создания объекта панели изменения размера.  
  
##  <a name="create"></a>COleResizeBar::Create  
 Создает дочернее окно и связывает его с `COleResizeBar` объекта.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_RESIZE_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на родительское окно изменения размера строки.  
  
 `dwStyle`  
 Указывает [стиль окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) атрибуты.  
  
 `nID`  
 Идентификатор дочернего окна панели изменения размера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если изменения размера панели был создан; в противном случае — 0.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC SUPERPAD](../../visual-cpp-samples.md)   
 [CControlBar-класс](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)
