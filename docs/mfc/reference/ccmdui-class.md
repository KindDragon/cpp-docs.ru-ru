---
title: "Класс CCmdUI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
dev_langs:
- C++
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32413fe7939b5e5d5d3d41bf32a923dd308f0395
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccmdui-class"></a>CCmdUI-класс
Используется только в `ON_UPDATE_COMMAND_UI` обработчик в `CCmdTarget`-производного класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCmdUI  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CCmdUI::ContinueRouting](#continuerouting)|Указывает механизму маршрутизации команд для продолжения рассылки текущее сообщение по цепочке обработчиков.|  
|[CCmdUI::Enable](#enable)|Включает или отключает элемент пользовательского интерфейса для этой команды.|  
|[CCmdUI::SetCheck](#setcheck)|Задает состояние проверки элемента пользовательского интерфейса для этой команды.|  
|[CCmdUI::SetRadio](#setradio)|Как `SetCheck` функции-члена, но работает групп переключателей.|  
|[CCmdUI::SetText](#settext)|Задает текст для элемента пользовательского интерфейса для этой команды.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CCmdUI::m_nID](#m_nid)|Идентификатор объекта пользовательского интерфейса.|  
|[CCmdUI::m_nIndex](#m_nindex)|Индекс объекта пользовательского интерфейса.|  
|[CCmdUI::m_pMenu](#m_pmenu)|Указывает меню, представленного `CCmdUI` объекта.|  
|[CCmdUI::m_pOther](#m_pother)|Указывает объект window, которому было отправлено уведомление.|  
|[CCmdUI::m_pSubMenu](#m_psubmenu)|Указывает на автономных подменю представленный `CCmdUI` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CCmdUI`не имеет базового класса.  
  
 Когда пользователь приложения извлекает меню, каждый меню элемента необходимо знать, является ли он должен отображаться как включенная или отключена. Целевого объекта команды меню предоставляет эти сведения, реализовав `ON_UPDATE_COMMAND_UI` обработчика. Для каждого из командных объектов пользовательского интерфейса в приложении используйте окно свойств для создания прототипа входа и функции схемы сообщений для каждого обработчика.  
  
 Когда извлекается меню, платформа ищет и вызывает каждый `ON_UPDATE_COMMAND_UI` обработчик, вызывает каждый обработчик `CCmdUI` члена функции, такие как **включить** и **проверьте**и затем framework Отображает каждый элемент меню.  
  
 Можно заменить пункта меню с кнопкой панели элементов управления или другой объект команды пользовательского интерфейса без изменения кода в `ON_UPDATE_COMMAND_UI` обработчика.  
  
 В следующей таблице перечислены эффект `CCmdUI`функции-члены имеют на различные элементы пользовательского интерфейса команд.  
  
|Элемент пользовательского интерфейса|Включить|SetCheck|SetRadio|SetText|  
|--------------------------|------------|--------------|--------------|-------------|  
|Элемент меню|Включает или отключает|И снятии флажка|Проверяет, использует точку|Наборы элементов текста|  
|Кнопки панели инструментов|Включает или отключает|Выбирает, приводит к отмене выбора, или неопределенное состояние|Аналогично `SetCheck`|(Неприменимо)|  
|Панели строки состояния|Текст становится видимым или невидимым|Границы исчезающего или обычные наборы|Аналогично `SetCheck`|Задает текст панели|  
|Обычная кнопка в`CDialogBar`|Включает или отключает|Установке или снятии флажка|Аналогично `SetCheck`|Задает кнопку текста|  
|Обычный элемент управления в`CDialogBar`|Включает или отключает|(Неприменимо)|(Неприменимо)|Задает текст окна|  
  
 Дополнительные сведения об использовании этого класса см [обновление объектов пользовательского интерфейса](../../mfc/how-to-update-user-interface-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CCmdUI`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="continuerouting"></a>CCmdUI::ContinueRouting  
 Вызовите эту функцию-член должен сообщить механизм маршрутизации команд для продолжения рассылки текущее сообщение по цепочке обработчиков.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Примечания  
 Это — это функция дополнительный член, который должен использоваться в сочетании с `ON_COMMAND_EX` обработчик, который возвращает **FALSE**. Дополнительные сведения см. в разделе [технические примечание 6](../../mfc/tn006-message-maps.md).  
  
##  <a name="enable"></a>CCmdUI::Enable  
 Вызовите эту функцию-член для включения или отключения элемента пользовательского интерфейса для этой команды.  
  
```  
virtual void Enable(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bOn`  
 **Значение TRUE,** чтобы активировать элемент, **FALSE** отключить ее.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]  
  
##  <a name="m_nid"></a>CCmdUI::m_nID  
 Идентификатор элемента меню, кнопки панели инструментов или другой объект пользовательского интерфейса, представленного `CCmdUI` объекта.  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_nindex"></a>CCmdUI::m_nIndex  
 Индекс элемента меню, кнопки панели инструментов или другой объект пользовательского интерфейса, представленного `CCmdUI` объекта.  
  
```  
UINT m_nIndex;  
```  
  
##  <a name="m_pmenu"></a>CCmdUI::m_pMenu  
 Указатель (из `CMenu` типа) в меню, представленного `CCmdUI` объекта.  
  
```  
CMenu* m_pMenu;  
```  
  
### <a name="remarks"></a>Примечания  
 **Значение NULL** Если элемент не меню.  
  
##  <a name="m_psubmenu"></a>CCmdUI::m_pSubMenu  
 Указатель (из `CMenu` типа) для автономной подменю представленный `CCmdUI` объекта.  
  
```  
CMenu* m_pSubMenu;  
```  
  
### <a name="remarks"></a>Примечания  
 **Значение NULL** Если элемент не меню. Если меню sub всплывающее окно, `m_nID` содержит идентификатор первого элемента в контекстном меню. Дополнительные сведения см. в разделе [Технические заметки 21](../../mfc/tn021-command-and-message-routing.md).  
  
##  <a name="m_pother"></a>CCmdUI::m_pOther  
 Указатель (типа `CWnd`) на объект window, например панель инструментов или состояние, которое отправлено уведомление.  
  
```  
CWnd* m_pOther;  
```  
  
### <a name="remarks"></a>Примечания  
 **Значение NULL** , является ли элемент меню или значение, отличное от `CWnd` объекта.  
  
##  <a name="setcheck"></a>CCmdUI::SetCheck  
 Вызовите эту функцию-член присвоено состояние соответствующего флажка элемента пользовательского интерфейса для этой команды.  
  
```  
virtual void SetCheck(int nCheck = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `nCheck`  
 Указывает состояние проверки для задания. Если 0, снимает; Если 1, проверяет; и если 2, задает в неопределенном состоянии.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член работает пункты меню и кнопки панели инструментов. Неопределенное состояние применяется только к кнопки панели инструментов.  
  
##  <a name="setradio"></a>CCmdUI::SetRadio  
 Вызовите эту функцию-член присвоено состояние соответствующего флажка элемента пользовательского интерфейса для этой команды.  
  
```  
virtual void SetRadio(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bOn`  
 **Значение TRUE,** чтобы активировать элемент; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член будет функционировать как `SetCheck`, за исключением того, что он работает в элементах пользовательского интерфейса, являющихся частью группы переключателей. Отмена выбора других элементов в группе не выполняется автоматически, если сами элементы однородной работы группы переключателей.  
  
##  <a name="settext"></a>CCmdUI::SetText  
 Вызовите эту функцию-член для задания текста элемента пользовательского интерфейса для этой команды.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Указатель на строку текста.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
