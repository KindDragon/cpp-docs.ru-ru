---
title: "Класс critical_section | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
dev_langs:
- C++
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
caps.latest.revision: 23
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 58821589a4b7596b80179a77dfd6a5772531f053
ms.lasthandoff: 03/17/2017

---
# <a name="criticalsection-class"></a>Класс critical_section
Не допускающий повторные входы мьютекс, который явно учитывает среду выполнения с параллелизмом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class critical_section;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`native_handle_type`|Ссылка на объект `critical_section`.|  
  
### <a name="public-classes"></a>Открытые классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс critical_section::scoped_lock](#critical_section__scoped_lock_class)|Исключение безопасный программой-оболочкой RAII для `critical_section` объекта.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[critical_section](#ctor)|Создает новый критический раздел.|  
|[~ critical_section деструктор](#dtor)|Уничтожает критический раздел.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[lock](#lock)|Получает данную критическую секцию.|  
|[native_handle](#native_handle)|Возвращает определенного собственного дескриптора платформы, если он существует.|  
|[try_lock](#try_lock)|Пытается получить блокировку без блокировки.|  
|[try_lock_for](#try_lock_for)|Пытается получить блокировку без блокировки в течение указанного числа миллисекунд.|  
|[unlock](#unlock)|Снимает блокировку критической секции.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `critical_section`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>critical_section 

 Создает новый критический раздел.  
  
```
critical_section();
```  
  
##  <a name="dtor"></a>~ critical_section 

 Уничтожает критический раздел.  
  
```
~critical_section();
```  
  
### <a name="remarks"></a>Примечания  
 Ожидается, что больше не блокировку при выполнении деструктора. По-прежнему уничтожение критического раздела приводит к неопределенному блокировка удерживается результатов к неопределенному поведению.  
  
##  <a name="lock"></a>Блокировка 

 Получает данную критическую секцию.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Примечания  
 Часто безопаснее использовать [scoped_lock](#critical_section__scoped_lock_class) конструкцию, чтобы получить и освободить `critical_section` объекта к исключению безопасным способом.  
  
 Если блокировка уже захвачена вызывающий контекст [improper_lock](improper-lock-class.md) будет создано исключение.  
  
##  <a name="native_handle"></a>native_handle 

 Возвращает определенного собственного дескриптора платформы, если он существует.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на критический раздел.  
  
### <a name="remarks"></a>Примечания  
 Объект `critical_section` объект не связан с платформы собственный дескриптор операционной системы Windows. Метод просто возвращает ссылку на сам объект.  
  
##  <a name="critical_section__scoped_lock_class"></a>Класс critical_section::scoped_lock  
 Исключение безопасный программой-оболочкой RAII для `critical_section` объекта.  
  
```
class scoped_lock;
```  
  
##  <a name="critical_section__scoped_lock_ctor"></a>scoped_lock::scoped_lock 

 Создает `scoped_lock` объекта и получает `critical_section` объект, передаваемый в `_Critical_section` параметр. Если критический раздел удерживается другим потоком, этот вызов блокируется.  
  
```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```  
  
### <a name="parameters"></a>Параметры  
 `_Critical_section`  
 Критический раздел для блокировки.  
  
##  <a name="critical_section__scoped_lock_dtor"></a>scoped_lock:: ~ scoped_lock 

 Уничтожает `scoped_lock` объекта и освобождает критический раздел, переданную в конструкторе.  
  
```
~scoped_lock();
```  
  
##  <a name="try_lock"></a>try_lock 

 Пытается получить блокировку без блокировки.  
  
```
bool try_lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если блокировка была получена, значение `true`; в противном случае — значение `false`.  
  
##  <a name="try_lock_for"></a>try_lock_for 

 Пытается получить блокировку без блокировки в течение указанного числа миллисекунд.  
  
```
bool try_lock_for(unsigned int _Timeout);
```  
  
### <a name="parameters"></a>Параметры  
 `_Timeout`  
 Количество миллисекунд перед истечением времени ожидания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если блокировка была получена, значение `true`; в противном случае — значение `false`.  
  
##  <a name="unlock"></a>разблокировать 

 Снимает блокировку критической секции.  
  
```
void unlock();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс reader_writer_lock](reader-writer-lock-class.md)
