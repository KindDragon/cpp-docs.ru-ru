---
title: "Класс unchecked_array_iterator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- stdext::unchecked_array_iterator
dev_langs:
- C++
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02d95c517f6e4af3cd519f05b0ab9c1469c63241
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="uncheckedarrayiterator-class"></a>Класс unchecked_array_iterator
Класс `unchecked_array_iterator` позволяет заключить массив или указатель в оболочку из непроверенного итератора. Используйте этот класс в качестве оболочки (с функцией [make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator)) для необработанных указателей или массивов с целью проверки предупреждений об указателях и управления этими предупреждениями вместо того, чтобы глобально отключать эти предупреждения. Если возможно, используйте проверенную версию этого класса, [checked_array_iterator](../standard-library/checked-array-iterator-class.md).  
  
> [!NOTE]
>  Этот класс является расширением стандартной библиотеки C++, которое предоставляется Майкрософт. Код, реализованный с помощью этой функции, нельзя перенести в стандартные среды сборки C, не поддерживающие это расширение Microsoft.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Iterator>  
class unchecked_array_iterator;
```  
  
## <a name="remarks"></a>Примечания  
 Этот класс определяется в пространстве имен [stdext](../standard-library/stdext-namespace.md).  
  
 Это непроверенная версия [класса checked_array_iterator](../standard-library/checked-array-iterator-class.md), и она поддерживает те же перегрузки и члены. Дополнительные сведения о функции проверяемого итератора с примерами кода см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<iterator>  
  
 **Пространство имен:** stdext  
  
## <a name="see-also"></a>См. также  
 [\<iterator>](../standard-library/iterator.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)



