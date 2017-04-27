---
title: "Класс unique_lock | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::unique_lock
dev_langs:
- C++
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
caps.latest.revision: 10
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 27145bb5aab7087ddf9dd7d56d51f242062268ff
ms.lasthandoff: 02/24/2017

---
# <a name="uniquelock-class"></a>Класс unique_lock
Представляет шаблон, для которого можно создать экземпляры и объекты, управляющие блокировкой и разблокировкой `mutex`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Mutex>
class unique_lock;
```  
  
## <a name="remarks"></a>Примечания  
 В аргументе шаблона `Mutex` должно быть указано имя *типа мьютекс*.  
  
 На внутреннем уровне `unique_lock` содержит указатель на связанный с ним объект `mutex` и `bool`, который указывает, владеет ли текущий поток `mutex`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`mutex_type`|Синоним для аргумента шаблона `Mutex`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор unique_lock](#unique_lock__unique_lock_constructor)|Создает объект `unique_lock`.|  
|[Деструктор ~unique_lock](#unique_lock___dtorunique_lock_destructor)|Освобождает все ресурсы, связанные с объектом `unique_lock`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[lock](#unique_lock__lock_method)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца соответствующего объекта `mutex`.|  
|[mutex](#unique_lock__mutex_method)|Извлекает сохраненный указатель на соответствующий объект `mutex`.|  
|[owns_lock](#unique_lock__owns_lock_method)|Указывает, является ли вызывающий поток владельцем соответствующего объекта `mutex`.|  
|[release](#unique_lock__release_method)|Отменяет связь объекта `unique_lock` с объектом `mutex`.|  
|[swap](#unique_lock__swap_method)|Меняет местами соответствующий `mutex` и статус владения с аналогичными свойствами указанного объекта.|  
|[try_lock](#unique_lock__try_lock_method)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|  
|[try_lock_for](#unique_lock__try_lock_for_method)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|  
|[try_lock_until](#unique_lock__try_lock_until_method)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|  
|[unlock](#unique_lock__unlock_method)|Освобождает права владения для соответствующего объекта `mutex`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[operator bool](#unique_lock__operator_bool)|Указывает, является ли вызывающий поток владельцем соответствующего объекта `mutex`.|  
|[оператор=](#unique_lock__operator_eq)|Копирует сохраненный указатель `mutex` и соответствующее состояние владения из указанного объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `unique_lock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** mutex  
  
 **Пространство имен:** std  
  
##  <a name="a-nameuniquelocklockmethoda--lock"></a><a name="unique_lock__lock_method"></a>  lock  
 Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца соответствующего объекта `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Примечания  
 Если сохраненный указатель `mutex` имеет значение `null`, то этот метод выбрасывает ошибку [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.  
  
 Если вызывающий поток уже является владельцем соответствующего объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.  
  
 В противном случае этот метод вызывает метод `lock` соответствующего объекта `mutex` и устанавливает внутренний флаг владения для потока в значение `true`.  
  
##  <a name="a-nameuniquelockmutexmethoda--mutex"></a><a name="unique_lock__mutex_method"></a>  mutex  
 Извлекает сохраненный указатель на соответствующий объект `mutex`.  
  
```cpp  
mutex_type *mutex() const noexcept;
```  
  
##  <a name="a-nameuniquelockoperatorboola--operator-bool"></a><a name="unique_lock__operator_bool"></a>  operator bool  
 Указывает, является ли вызывающий поток владельцем соответствующего мьютекса.  
  
```cpp  
explicit operator bool() noexcept
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` если поток является владельцем мьютекса; в противном случае `false`.  
  
##  <a name="a-nameuniquelockoperatoreqa--operator"></a><a name="unique_lock__operator_eq"></a>  оператор=  
 Копирует сохраненный указатель `mutex` и соответствующее состояние владения из указанного объекта.  
  
```cpp  
unique_lock& operator=(unique_lock&& Other) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Other`  
 Объект `unique_lock`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `*this`  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток является владельцем ранее назначенного объекта `mutex`, то перед вызовом `unlock` на `mutex` этот метод назначает новые значения.  
  
 После копирования этот метод устанавливает `Other` в состояние конструктора по умолчанию.  
  
##  <a name="a-nameuniquelockownslockmethoda--ownslock"></a><a name="unique_lock__owns_lock_method"></a>  owns_lock  
 Указывает, является ли вызывающий поток владельцем соответствующего объекта `mutex`.  
  
```cpp  
bool owns_lock() const noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` если поток является владельцем `mutex`; в противном случае `false`.  
  
##  <a name="a-nameuniquelockreleasemethoda--release"></a><a name="unique_lock__release_method"></a>  release  
 Отменяет связь объекта `unique_lock` с объектом `mutex`.  
  
```cpp  
mutex_type *release() noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее значение сохраненного указателя `mutex`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод устанавливает значение сохраненного указателя `mutex` в 0 и устанавливает внутренний флаг владения `mutex` в `false`.  
  
##  <a name="a-nameuniquelockswapmethoda--swap"></a><a name="unique_lock__swap_method"></a>  swap  
 Меняет местами соответствующий `mutex` и статус владения с аналогичными свойствами указанного объекта.  
  
```
void swap(unique_lock& Other) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Other`  
 Объект `unique_lock`.  
  
##  <a name="a-nameuniquelocktrylockmethoda--trylock"></a><a name="unique_lock__try_lock_method"></a>  try_lock  
 Попытки получить права владельца связанного объекта `mutex` без блокировки.  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод успешно получает права владельца `mutex`; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Если сохраненный указатель `mutex` имеет значение `null`, этот метод выбрасывает ошибку [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.  
  
 Если вызывающий поток уже является владельцем объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.  
  
##  <a name="a-nameuniquelocktrylockformethoda--trylockfor"></a><a name="unique_lock__try_lock_for_method"></a>  try_lock_for  
 Попытки получить права владельца связанного объекта `mutex` без блокировки.  
  
```
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Параметры  
 `Rel_time`  
 Объект [chrono::duration](../standard-library/duration-class.md), который указывает максимальный интервал времени, в течение которого метод пытается получить права владельца объекта `mutex`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод успешно получает права владельца `mutex`; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Если сохраненный указатель `mutex` имеет значение `null`, этот метод выбрасывает ошибку [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.  
  
 Если вызывающий поток уже является владельцем объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.  
  
##  <a name="a-nameuniquelocktrylockuntilmethoda--trylockuntil"></a><a name="unique_lock__try_lock_until_method"></a>  try_lock_until  
 Попытки получить права владельца связанного объекта `mutex` без блокировки.  
  
```cpp  
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```  
  
### <a name="parameters"></a>Параметры  
 `Abs_time`  
 Момент времени, определяющий порог, после которого метод больше не пытается получить права владельца объекта `mutex`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если метод успешно получает права владельца `mutex`; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Если сохраненный указатель `mutex` имеет значение `null`, этот метод выбрасывает ошибку [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.  
  
 Если вызывающий поток уже является владельцем объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.  
  
##  <a name="a-nameuniquelockuniquelockconstructora--uniquelock-constructor"></a><a name="unique_lock__unique_lock_constructor"></a>  Конструктор unique_lock  
 Создает объект `unique_lock`.  
  
```cpp  
unique_lock() noexcept;
unique_lock(unique_lock&& Other) noexcept;
explicit unique_lock(mutex_type& Mtx);

unique_lock(mutex_type& Mtx, adopt_lock_t Adopt);

unique_lock(mutex_type& Mtx, defer_lock_t Defer) noexcept;
unique_lock(mutex_type& Mtx, try_to_lock_t Try);

template <class Rep, class Period>
unique_lock(mutex_type& Mtx,
    const chrono::duration<Rep, Period>  
Rel_time);

template <class Clock, class Duration>
unique_lock(mutex_type& Mtx,
    const chrono::time_point<Clock, Duration>  
Abs_time);

unique_lock(mutex_type& Mtx,
    const xtime* Abs_time) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Mtx`  
 Тип объекта мьютекса.  
  
 `Rel_time`  
 Объект [chrono::duration](../standard-library/duration-class.md), который указывает максимальный интервал времени, в течение которого метод пытается получить права владельца объекта `mutex`.  
  
 `Abs_time`  
 Момент времени, определяющий порог, после которого метод больше не пытается получить права владельца объекта `mutex`.  
  
 `Other`  
 Объект `unique_lock`.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает объект, у которого значение соответствующего указателя мьютекса равно 0.  
  
 Второй конструктор перемещает соответствующее состояние мьютекса из `Other`. После перемещения объект `Other` больше не связан с мьютексом.  
  
 В оставшихся конструкторах в качестве сохраненного указателя `mutex` используется значение &`Mtx`. Состояние владения `mutex` определяется с помощью второго аргумента, если он существует.  
  
|||  
|-|-|  
|`No argument`|Для получения состояния владения вызывается метод `lock` соответствующего объекта `mutex`.|  
|`Adopt`|Предполагается, что состояние владения есть. `Mtx` должен быть заблокирован при вызове конструктора.|  
|`Defer`|Предполагается, что вызывающий поток не является владельцем объекта `mutex`. `Mtx` не должен быть заблокирован при вызове конструктора.|  
|`Try`|Для получения состояния владения вызывается метод `try_lock` соответствующего объекта `mutex`. Конструктор не выбрасывает никаких исключений.|  
|`Rel_time`|Для получения состояния владения вызывается метод `try_lock_for(Rel_time)`.|  
|`Abs_time`|Для получения состояния владения вызывается метод `try_lock_until(Abs_time)`.|  
  
##  <a name="a-nameuniquelockdtoruniquelockdestructora--uniquelock-destructor"></a><a name="unique_lock___dtorunique_lock_destructor"></a> Деструктор ~unique_lock  
 Освобождает все ресурсы, связанные с объектом `unique_lock`.  
  
```cpp  
~unique_lock() noexcept;
```  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток является владельцем соответствующего объекта `mutex`, деструктор освобождает права владения, вызывая метод unlock для объекта `mutex`.  
  
##  <a name="a-nameuniquelockunlockmethoda--unlock"></a><a name="unique_lock__unlock_method"></a>  unlock  
 Освобождает права владения для соответствующего объекта `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток не является владельцем соответствующего объекта `mutex`, этот метод создает исключение [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.  
  
 В противном случае этот метод вызывает метод `unlock` соответствующего объекта `mutex` и устанавливает внутренний флаг владения для потока в значение `false`.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



