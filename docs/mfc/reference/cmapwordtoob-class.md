---
title: "Класс CMapWordToOb | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapWordToOb
- AFXCOLL/CMapWordToOb
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 9c9bcd76-456f-4cf9-b03c-dd28b49d5e4f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7166fd1b0ce0f8e9152c617979d0ec80bfb2b57
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmapwordtoob-class"></a>Класс CMapWordToOb
Поддерживает сопоставления указателей `CObject` , зашифрованных 16-разрядными словами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMapWordToOb : public CObject  
```  
  
## <a name="members"></a>Участники  
 Функции-члены `CMapWordToOb` похожи на функции-члены класса [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Если вы видите `CString` или **const** указатель `char` как параметр функции или возвращаемого значения, замените **WORD**.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 , например, преобразуется в  
  
 `BOOL CMapWordToOb::Lookup( WORD <key>, CObject*& <rValue> ) const;`  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Возвращает количество элементов в этой схеме.|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Определяет текущее число элементов в хэш-таблице.|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Получает следующий элемент для выполнения итерации.|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Возвращает количество элементов в этой схеме.|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Возвращает позицию первого элемента.|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Вычисляет хэш-значение указанного ключа.|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Инициализирует хэш-таблицы.|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Проверяет условие пустой карты (нет элементов).|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Находит указатель void на основе ключа указателя void. Значение указателя не сущности, которую он указывает, используется для сравнения ключей.|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы из этой карты.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент, указанный с помощью ключа.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент в сопоставление; заменяет существующий элемент, если найден соответствующий ключ.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в сопоставление — оператор подстановки для `SetAt`.|  
  
## <a name="remarks"></a>Примечания  
 `CMapWordToOb` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Каждый элемент сериализуется в свою очередь, если карта хранится в архив с помощью перегруженных вставки (  **<<** ) оператор или с `Serialize` функции-члена.  
  
 Если вам требуется дамп отдельных **WORD** -  `CObject` элементов, необходимо задать глубины контекста дампа 1 или больше.  
  
 Когда `CMapWordToOb` объект удаляется или когда его элементы будут удалены, `CObject` указатели удаляются. Объекты, упоминаемые `CObject` указатели, не удаляются.  
  
 Дополнительные сведения о `CMapWordToOb`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapWordToOb`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



