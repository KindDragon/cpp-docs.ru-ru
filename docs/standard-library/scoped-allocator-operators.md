---
title: "Операторы &lt;scoped_allocator&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c8b64ba6276ecfa1078faf3b75a3cf36e9fc5072
ms.lasthandoff: 02/24/2017

---
# <a name="ltscopedallocatorgt-operators"></a>Операторы &lt;scoped_allocator&gt;
|||  
|-|-|  
|[оператор!=](#operator_neq)|[оператор==](#operator_eq_eq)|  
  
##  <a name="operator_neq"></a>  оператор!=  
 Сравнивает два объекта `scoped_allocator_adaptor`, чтобы определить их неравенство.  
  
```cpp  
template <class Outer, class... Inner>  
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,  
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;  
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Левый объект `scoped_allocator_adaptor`.  
  
 `right`  
 Правой объект `scoped_allocator_adaptor`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `!(left == right)`  
  
##  <a name="operator_eq_eq"></a>  оператор==  
 Сравнивает два объекта `scoped_allocator_adaptor`, чтобы определить, равны ли они.  
  
```cpp  
template <class Outer, class... Inner>  
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,  
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;  
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Левый объект `scoped_allocator_adaptor`.  
  
 `right`  
 Правой объект `scoped_allocator_adaptor`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`  
  
## <a name="see-also"></a>См. также  
 [<scoped_allocator>](../standard-library/scoped-allocator.md)

