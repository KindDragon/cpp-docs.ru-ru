---
title: "Класс COleDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
dev_langs:
- C++
helpviewer_keywords:
- OLE dialog boxes, base class
- dialog boxes, OLE
- COleDialog class
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 018d06ac167a8c352d9f1822b373126c4e615854
ms.lasthandoff: 02/24/2017

---
# <a name="coledialog-class"></a>Класс COleDialog
Предоставляет стандартные функции для диалоговых окон OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDialog::GetLastError](#getlasterror)|Получает код ошибки, возвращаемый диалоговым окном.|  
  
## <a name="remarks"></a>Примечания  
 Библиотеки классов Microsoft Foundation предоставляет несколько классов, производных от `COleDialog`:  
  
- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)  
  
- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)  
  
- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)  
  
- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)  
  
- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)  
  
- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)  
  
- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)  
  
- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)  
  
 Дополнительные сведения о диалоговых окнах OLE конкретных см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `COleDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="getlasterror"></a>COleDialog::GetLastError  
 Вызов `GetLastError` функции-члена для получения дополнительных сведений об ошибке при `DoModal` возвращает **IDABORT**.  
  
```  
UINT GetLastError() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Коды ошибок, возвращаемые `GetLastError` зависят от конкретного диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 В разделе `DoModal` функции-члена в производных классах, сведения о специальных сообщений об ошибках.  
  
## <a name="see-also"></a>См. также  
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



