---
title: "Класс codecvt_base | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b3d1ae1c2bae5c4ce0ab4c7cb6ecadec194f5f9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="codecvtbase-class"></a>Класс codecvt_base
Базовый класс для класса codecvt, используемый для определения типа перечисления с именем **result**, который применяется в качестве типа возвращаемого значения для функций-членов аспекта, чтобы показать результат преобразования.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```  
  
## <a name="remarks"></a>Примечания  
 Данный класс описывает перечисление, общее для всех специализаций класса-шаблона [codecvt](../standard-library/codecvt-class.md). Результат перечисления описывает возможные возвращаемые значения из [do_in](../standard-library/codecvt-class.md#do_in) или [do_out](../standard-library/codecvt-class.md#do_out):  
  
- **ОК**, если преобразование между внутренней и внешней кодировками символов выполняется успешно.  
  
- **partial**, если целевой объект недостаточно велик для успешного преобразования.  
  
- **error**, если исходная последовательность имеет неправильную форму.  
  
- **noconv**, если функция не выполняет преобразование.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



