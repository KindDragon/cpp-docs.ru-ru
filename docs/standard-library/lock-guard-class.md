---
title: "Класс lock_guard | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
dev_langs:
- C++
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60643375742ef02ef1ba8ea08e614d12c504c573
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="lockguard-class"></a>Класс lock_guard
Представляет шаблон, для которого можно создать экземпляры и объект, деструктор которого разблокирует `mutex`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Mutex>
class lock_guard;
```  
  
## <a name="remarks"></a>Примечания  
 В аргументе шаблона `Mutex` должно быть указано имя *типа мьютекс*.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`lock_guard::mutex_type`|Синоним для аргумента шаблона `Mutex`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[lock_guard](#lock_guard)|Создает объект `lock_guard`.|  
|[Деструктор lock_guard::~lock_guard](#dtorlock_guard_destructor)|Снимает блокировку `mutex`, переданного в конструктор.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<мьютекс >  
  
 **Пространство имен:** std  
  
##  <a name="lock_guard"></a>  Конструктор lock_guard::lock_guard  
 Создает объект `lock_guard`.  
  
```cpp  
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```  
  
### <a name="parameters"></a>Параметры  
 `Mtx`  
 Объект *типа мьютекс*.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает объект типа `lock_guard` и блокирует `Mtx`. Если `Mtx` не является рекурсивным мьютексом, его необходимо разблокировать при вызове этого конструктора.  
  
 Второй конструктор не блокирует `Mtx`. `Mtx` должен быть заблокирован при вызове этого конструктора. Конструктор не выдает никаких исключений.  
  
##  <a name="dtorlock_guard_destructor"></a>  Деструктор lock_guard::~lock_guard  
 Снимает блокировку `mutex`, переданного в конструктор.  
  
```
~lock_guard() noexcept;
```  
  
### <a name="remarks"></a>Примечания  
 Если `mutex` не существует при выполнении деструктора, поведение не определено.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



