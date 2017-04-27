---
title: "Класс scoped_allocator_adaptor | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.scoped_allocator_adaptor
- scoped_allocator_adaptor
- scoped_allocator/std::scoped_allocator_adaptor
- std::scoped_allocator_adaptor
dev_langs:
- C++
helpviewer_keywords:
- scoped_allocator_adaptor Class
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: f4c343592c2c767d52a66091ecca5b1bd4ae9e88
ms.lasthandoff: 02/24/2017

---
# <a name="scopedallocatoradaptor-class"></a>Класс scoped_allocator_adaptor
Представляет вложенные распределители.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <class Outer, class... Inner>  
class scoped_allocator_adaptor;  
```  
  
## <a name="remarks"></a>Примечания  
 Класс шаблонов инкапсулирует вложение одного или нескольких распределителей. Каждый из этих классов имеет внешний распределитель типа `outer_allocator_type`, синоним `Outer`, который представляет собой общедоступную базу объекта `scoped_allocator_adaptor`. `Outer` используется для выделения памяти, которая будет использоваться контейнером. Можно получить ссылку на этот базовый объект распределителя, вызвав метод `outer_allocator`.  
  
 Остальная часть вложения имеет тип `inner_allocator_type`. Внутренний распределитель используется для выделения памяти для элементов в контейнере. Для получения ссылки на сохраненный объект этого типа вызовите `inner_allocator`. Если `Inner...` не пустой, `inner_allocator_type` имеет тип `scoped_allocator_adaptor<Inner...>`, а `inner_allocator` назначает объект-член. В противном случае `inner_allocator_type` имеет тип `scoped_allocator_adaptor<Outer>`, а `inner_allocator` назначает целый объект.  
  
 Вложение ведет себя так, как будто имеет произвольную глубину, реплицируя свой самый внутренний инкапсулированный распределитель так, как нужно.  
  
 Некоторые понятия, которые не являются частью видимого интерфейса, облегчают описание поведения этого класса шаблонов. *Внешний распределитель* преобразует все вызовы, адресованные методам construct и destroy. Он эффективно определяется рекурсивной функцией `OUTERMOST(X)`, где `OUTERMOST(X)` — один из следующих объектов.  
  
-   Если `X.outer_allocator()` имеет правильный формат, `OUTERMOST(X)` равен `OUTERMOST(X.outer_allocator())`.  
  
-   В противном случае `OUTERMOST(X)` является `X`.  
  
 В целях демонстрации определено три типа:  
  
|Тип|Описание|  
|----------|-----------------|  
|`Outermost`|Тип параметра `OUTERMOST(*this)`.|  
|`Outermost_traits`|`allocator_traits<Outermost>`|  
|`Outer_traits`|`allocator_traits<Outer>`|  
  
### <a name="constructors"></a>Конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор scoped_allocator_adaptor::scoped_allocator_adaptor](#scoped_allocator_adaptor__scoped_allocator_adaptor_constructor)|Создает объект `scoped_allocator_adaptor`.|  
  
### <a name="typedefs"></a>Определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`const_pointer`|Этот тип является синонимом `const_pointer`, связанного с распределителем `Outer`.|  
|`const_void_pointer`|Этот тип является синонимом `const_void_pointer`, связанного с распределителем `Outer`.|  
|`difference_type`|Этот тип является синонимом `difference_type`, связанного с распределителем `Outer`.|  
|`inner_allocator_type`|Этот тип является синонимом типа вложенного адаптера `scoped_allocator_adaptor<Inner...>`.|  
|`outer_allocator_type`|Этот тип является синонимом типа базового распределителя `Outer`.|  
|`pointer`|Этот тип является синонимом `pointer`, связанного с распределителем `Outer`.|  
|`propagate_on_container_copy_assignment`|Тип содержит значение true только в том случае, если `Outer_traits::propagate_on_container_copy_assignment` или `inner_allocator_type::propagate_on_container_copy_assignment` имеет значение true.|  
|`propagate_on_container_move_assignment`|Тип содержит значение true только в том случае, если `Outer_traits::propagate_on_container_move_assignment` или `inner_allocator_type::propagate_on_container_move_assignment` имеет значение true.|  
|`propagate_on_container_swap`|Тип содержит значение true только в том случае, если `Outer_traits::propagate_on_container_swap` или `inner_allocator_type::propagate_on_container_swap` имеет значение true.|  
|`size_type`|Этот тип является синонимом `size_type`, связанного с распределителем `Outer`.|  
|`value_type`|Этот тип является синонимом `value_type`, связанного с распределителем `Outer`.|  
|`void_pointer`|Этот тип является синонимом `void_pointer`, связанного с распределителем `Outer`.|  
  
### <a name="structs"></a>структурам;  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура scoped_allocator_adaptor::rebind](#scoped_allocator_adaptor__rebind_struct)|Определяет тип `Outer::rebind\<Other>::other` как синоним для `scoped_allocator_adaptor\<Other, Inner...>`.|  
  
### <a name="methods"></a>Методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод scoped_allocator_adaptor::allocate](#scoped_allocator_adaptor__allocate_method)|Выделяет память, используя распределитель `Outer`.|  
|[Метод scoped_allocator_adaptor::construct](#scoped_allocator_adaptor__construct_method)|Создает объект.|  
|[Метод scoped_allocator_adaptor::deallocate](#scoped_allocator_adaptor__deallocate_method)|Освобождает объекты, используя внешний распределитель.|  
|[Метод scoped_allocator_adaptor::destroy](#scoped_allocator_adaptor__destroy_method)|Удаляет указанный объект.|  
|[Метод scoped_allocator_adaptor::inner_allocator](#scoped_allocator_adaptor__inner_allocator_method)|Извлекает ссылку на сохраненный объект типа `inner_allocator_type`.|  
|[Метод scoped_allocator_adaptor::max_size](#scoped_allocator_adaptor__max_size_method)|Определяет максимальное число объектов, которые могут быть распределены внешним распределителем.|  
|[Метод scoped_allocator_adaptor::outer_allocator](#scoped_allocator_adaptor__outer_allocator_method)|Извлекает ссылку на сохраненный объект типа `outer_allocator_type`.|  
|[Метод scoped_allocator_adaptor::select_on_container_copy_construction](#scoped_allocator_adaptor__select_on_container_copy_construction_method)|Создает новый объект `scoped_allocator_adaptor` с каждым сохраненным объектом распределителя, который инициализируется вызовом метода `select_on_container_copy_construction` для каждого соответствующего распределителя.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<scoped_allocator>  
  
 **Пространство имен:** std  
  
##  <a name="a-namescopedallocatoradaptorallocatemethoda--scopedallocatoradaptorallocate-method"></a><a name="scoped_allocator_adaptor__allocate_method"></a> Метод scoped_allocator_adaptor::allocate  
 Выделяет память, используя распределитель `Outer`.  
  
```cpp  
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```  
  
### <a name="parameters"></a>Параметры  
 `count`  
 Количество элементов, для которых необходимо выделить достаточный объем памяти.  
  
 `hint`  
 Указатель, который может помочь объекту распределителя, найдя адрес объекта, который был выделен до этого запроса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая функция-член возвращает значение `Outer_traits::allocate(outer_allocator(), count)`. Вторая функция-член возвращает значение `Outer_traits::allocate(outer_allocator(), count, hint)`.  
  
##  <a name="a-namescopedallocatoradaptorconstructmethoda--scopedallocatoradaptorconstruct-method"></a><a name="scoped_allocator_adaptor__construct_method"></a> Метод scoped_allocator_adaptor::construct  
 Создает объект.  
  
```cpp  
template <class Ty, class... Atypes>  
void construct(Ty* ptr, Atypes&&... args);

template <class Ty1, class Ty2, class... Atypes1, class... Atypes2>  
void construct(pair<Ty1, Ty2>* ptr, piecewise_construct_t,  
    tuple<Atypes1&&...>  
first, tuple<Atypes1&&...> second);

template <class Ty1, class Ty2>  
void construct(pair<Ty1, Ty2>* ptr);

template <class Ty1, class Ty2, class Uy1, class Uy2>  
void construct(pair<Ty1, Ty2>* ptr,  
    class Uy1&& first, class Uy2&& second);

template <class Ty1, class Ty2, class Uy1, class Uy2>  
void construct(pair<Ty1, Ty2>* ptr, const pair<Uy1, Uy2>& right);

template <class Ty1, class Ty2, class Uy1, class Uy2>  
void construct(pair<Ty1, Ty2>* ptr, pair<Uy1, Uy2>&& right);
```  
  
### <a name="parameters"></a>Параметры  
 `ptr`  
 Указатель на место в памяти, где необходимо создать объект.  
  
 `args`  
 Список аргументов.  
  
 `first`  
 Объект первого типа в паре.  
  
 `second`  
 Объект второго типа в паре.  
  
 `right`  
 Существующий объект, который необходимо переместить или копировать.  
  
### <a name="remarks"></a>Примечания  
 Первый метод создает объект в `ptr`, вызывая `Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)`, где `xargs...` — один из следующих объектов.  
  
-   Если `uses_allocator<Ty, inner_allocator_type>` имеет значение false, то `xargs...` равно `args...`.  
  
-   Если `uses_allocator<Ty, inner_allocator_type>` имеет значение true и `is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` имеет значение true, то `xargs...` равно `allocator_arg, inner_allocator(), args...`.  
  
-   Если `uses_allocator<Ty, inner_allocator_type>` имеет значение true и `is_constructible<Ty, args..., inner_allocator()>` имеет значение true, то `xargs...` равно `args..., inner_allocator()`.  
  
 Второй метод создает объект-пару в `ptr`, вызывая `Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)`, где `xargs...` — это `first...`, измененный как в списке выше, и `Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)`, где `xargs...` — это `second...`, измененный как в списке выше.  
  
 Третий метод работает так же, как `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)`.  
  
 Четвертый метод работает так же, как `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))`.  
  
 Пятый метод работает так же, как `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))`.  
  
 Шестой метод работает так же, как `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))`.  
  
##  <a name="a-namescopedallocatoradaptordeallocatemethoda--scopedallocatoradaptordeallocate-method"></a><a name="scoped_allocator_adaptor__deallocate_method"></a> Метод scoped_allocator_adaptor::deallocate  
 Освобождает объекты, используя внешний распределитель.  
  
```cpp  
void deallocate(pointer ptr, size_type count);
```  
  
### <a name="parameters"></a>Параметры  
 `ptr`  
 Указатель на начальное расположение освобождаемых объектов.  
  
 `count`  
 Количество освобождаемых объектов.  
  
##  <a name="a-namescopedallocatoradaptordestroymethoda--scopedallocatoradaptordestroy-method"></a><a name="scoped_allocator_adaptor__destroy_method"></a> Метод scoped_allocator_adaptor::destroy  
 Удаляет указанный объект.  
  
```cpp  
template <class Ty>  
void destroy(Ty* ptr)  
```  
  
### <a name="parameters"></a>Параметры  
 `ptr`  
 Указатель на уничтожаемый объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `Outermost_traits::destroy(OUTERMOST(*this), ptr)`  
  
##  <a name="a-namescopedallocatoradaptorinnerallocatormethoda--scopedallocatoradaptorinnerallocator-method"></a><a name="scoped_allocator_adaptor__inner_allocator_method"></a> Метод scoped_allocator_adaptor::inner_allocator  
 Извлекает ссылку на сохраненный объект типа `inner_allocator_type`.  
  
```cpp  
inner_allocator_type& inner_allocator() noexcept;  
const inner_allocator_type& inner_allocator() const noexcept;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на сохраненный объект типа `inner_allocator_type`.  
  
##  <a name="a-namescopedallocatoradaptormaxsizemethoda--scopedallocatoradaptormaxsize-method"></a><a name="scoped_allocator_adaptor__max_size_method"></a> Метод scoped_allocator_adaptor::max_size  
 Определяет максимальное число объектов, которые могут быть распределены внешним распределителем.  
  
```cpp  
size_type max_size();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `Outer_traits::max_size(outer_allocator())`  
  
##  <a name="a-namescopedallocatoradaptorouterallocatormethoda--scopedallocatoradaptorouterallocator-method"></a><a name="scoped_allocator_adaptor__outer_allocator_method"></a> Метод scoped_allocator_adaptor::outer_allocator  
 Извлекает ссылку на сохраненный объект типа `outer_allocator_type`.  
  
```cpp  
outer_allocator_type& outer_allocator() noexcept;  
const outer_allocator_type& outer_allocator() const noexcept;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на сохраненный объект типа `outer_allocator_type`.  
  
##  <a name="a-namescopedallocatoradaptorrebindstructa--scopedallocatoradaptorrebind-struct"></a><a name="scoped_allocator_adaptor__rebind_struct"></a> Структура scoped_allocator_adaptor::rebind  
 Определяет тип `Outer::rebind\<Other>::other` как синоним для `scoped_allocator_adaptor\<Other, Inner...>`.  
  
struct rebind{  
   typedef Other_traits::rebind\<Other>  
   Other_alloc;  
   typedef scoped_allocator_adaptor\<Other_alloc, Inner...> other;  
   };  
  
##  <a name="a-namescopedallocatoradaptorscopedallocatoradaptorconstructora--scopedallocatoradaptorscopedallocatoradaptor-constructor"></a><a name="scoped_allocator_adaptor__scoped_allocator_adaptor_constructor"></a> Конструктор scoped_allocator_adaptor::scoped_allocator_adaptor  
 Создает объект `scoped_allocator_adaptor`.  
  
```cpp  
scoped_allocator_adaptor();

scoped_allocator_adaptor(const scoped_allocator_adaptor& right) noexcept;  
template <class Outer2>  
scoped_allocator_adaptor(
 const scoped_allocator_adaptor<Outer2, Inner...>& right) noexcept;  
template <class Outer2>  
scoped_allocator_adaptor(
 scoped_allocator_adaptor<Outer2, Inner...>&& right) noexcept;  
template <class Outer2>  
scoped_allocator_adaptor(Outer2&& al,  
    const Inner&... rest) noexcept;  
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Существующий `scoped_allocator_adaptor`.  
  
 `al`  
 Существующий распределитель, который следует использовать как внешний распределитель.  
  
 `rest`  
 Список распределителей, которые следует использовать как внутренние распределители.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор по умолчанию создает сохраненные объекты распределителя. Каждый из трех следующих конструкторов создает сохраненные объекты распределителя из соответствующих объектов в `right`. Последний конструктор создает сохраненные объекты распределителя из соответствующих аргументов в списке.  
  
##  <a name="a-namescopedallocatoradaptorselectoncontainercopyconstructionmethoda--scopedallocatoradaptorselectoncontainercopyconstruction-method"></a><a name="scoped_allocator_adaptor__select_on_container_copy_construction_method"></a> Метод scoped_allocator_adaptor::select_on_container_copy_construction  
 Создает новый объект `scoped_allocator_adaptor` с каждым сохраненным объектом распределителя, который инициализируется вызовом метода `select_on_container_copy_construction` для каждого соответствующего распределителя.  
  
```cpp  
scoped_allocator_adaptor select_on_container_copy_construction();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод фактически возвращает `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())`. В результате создается новый объект `scoped_allocator_adaptor` с каждым сохраненным объектом распределителя, который инициализируется вызовом метода `al.select_on_container_copy_construction()` для соответствующего распределителя `al`.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)



