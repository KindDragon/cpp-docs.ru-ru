---
title: "Класс CDefaultCompareTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13c8bfd8ac02979f82e205ec86269b7ac40c8b08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdefaultcomparetraits-class"></a>Класс CDefaultCompareTraits
Этот класс предоставляет по умолчанию элемент функции сравнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>  
class CDefaultCompareTraits
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Статический) Вызывайте эту функцию для сравнения на равенство двух элементов.|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Статический) Эта функция вызывается для определения элемента больше и меньше.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс содержит два статические функции для сравнения элементов, хранящихся в объекте класса коллекции. Этот класс используется [CDefaultElementTraits класса](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="compareelements"></a>CDefaultCompareTraits::CompareElements  
 Вызывайте эту функцию для сравнения на равенство двух элементов.  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Параметры  
 `element1`  
 Первый элемент  
  
 `element2`  
 Второй элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если элементы равны false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция является равенства ( `==`) оператор. Для объектов, отличных от простых типов данных эта функция может потребоваться переопределить.  
  
##  <a name="compareelementsordered"></a>CDefaultCompareTraits::CompareElementsOrdered  
 Эта функция вызывается для определения элемента больше и меньше.  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Параметры  
 `element1`  
 Первый элемент  
  
 `element2`  
 Второй элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение типа integer, зависимости в следующей таблице:  
  
|Условие|Возвращаемое значение|  
|---------------|------------------|  
|`element1` < `element2`|<0|  
|`element1` == `element2`|0|  
|`element1` > `element2`|>0|  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция использует `==`,  **\<** , и  **>**  операторы. Для объектов, отличных от простых типов данных эта функция может потребоваться переопределить.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
