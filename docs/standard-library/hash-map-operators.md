---
title: "Операторы &lt;hash_map&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- hash_map/std::operator!=
- hash_map/std::operator==
dev_langs:
- C++
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 9a1d27828908faa779101be4727e50d46a059fc2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="lthashmapgt-operators"></a>Операторы &lt;hash_map&gt;
|||  
|-|-|  
|[оператор!=](#op_neq)|[operator!= (multimap)](#op_neq_mm)|
|[оператор==](#op_eq_eq)|[оператор== (multimap)](#op_eq_eq_mm)|
  
##  <a name="op_neq"></a> operator!=  
  
> [!NOTE]
>  Этот элемент API устарел. Вместо него следует использовать [класс unordered_map](unordered-map-class.md).  
  
 Проверяет неравенство объекта hash_map слева от оператора и объекта hash_map справа от оператора.  
  
```  
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `hash_map`.  
  
 `right`  
 Объект типа `hash_map`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объекты hash_map не равны; **false**, если объекты hash_map равны.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами hash_map основывается на попарном сравнении их элементов. Два объекта hash_map равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
 Члены [< hash_map >](hash-map.md) и [< hash_set >](hash-set.md) файлы заголовков в [ пространство имен stdext](stdext-namespace.md).  
  
### <a name="example"></a>Пример  
  
```cpp  
// hash_map_op_ne.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 != hm2 )  
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm2 are equal." << endl;  
  
   if ( hm1 != hm3 )  
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm3 are equal." << endl;  
}  
```  
  
```Output  
The hash_maps hm1 and hm2 are not equal.  
The hash_maps hm1 and hm3 are equal.  
```  
  
##  <a name="op_eq_eq"></a> operator== 
  
> [!NOTE]
>  Этот элемент API устарел. Вместо него следует использовать [класс unordered_map](unordered-map-class.md).  
  
 Проверяет равенство объекта hash_map слева от оператора и объекта hash_map справа от оператора.  
  
```  
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `hash_map`.  
  
 `right`  
 Объект типа `hash_map`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объект hash_map слева от оператора равен объекту hash_map справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами hash_map основывается на попарном сравнении их элементов. Два объекта hash_map равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
    
### <a name="example"></a>Пример  
  
```cpp  
// hash_map_op_eq.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 == hm2 )  
      cout << "The hash_maps hm1 and hm2 are equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;  
  
   if ( hm1 == hm3 )  
      cout << "The hash_maps hm1 and hm3 are equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_maps hm1 and hm2 are not equal.  
The hash_maps hm1 and hm3 are equal.  
```  
  
##  <a name="op_neq_mm"></a>  оператор! = (hash_multimap) 
  
> [!NOTE]
>  Этот элемент API устарел. Вместо него следует использовать [класс unordered_multimap](unordered-multimap-class.md).  
  
 Проверяет неравенство объекта hash_multimap слева от оператора и объекта hash_multimap справа от оператора.  
  
```  
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `hash_multimap`.  
  
 `right`  
 Объект типа `hash_multimap`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объекты hash_multimap не равны; **false**, если они равны.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами hash_multimap основывается на попарном сравнении их элементов. Два объекта hash_multimap равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
   
### <a name="example"></a>Пример  
  
```cpp  
// hash_multimap_op_ne.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 != hm2 )  
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;  
  
   if ( hm1 != hm3 )  
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;  
}  
```  
  
```Output  
The hash_multimaps hm1 and hm2 are not equal.  
The hash_multimaps hm1 and hm3 are equal.  
```  
  
##  <a name="op_eq_eq_mm"></a>  оператор == (hash_multimap)
  
> [!NOTE]
>  Этот элемент API устарел. Вместо него следует использовать [класс unordered_multimap](unordered-multimap-class.md).  
  
 Проверяет равенство объекта hash_multimap слева от оператора и объекта hash_multimap справа от оператора.  
  
```  
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `hash_multimap`.  
  
 `right`  
 Объект типа `hash_multimap`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объект hash_multimap слева от оператора равен объекту hash_multimap справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами hash_multimap основывается на попарном сравнении их элементов. Два объекта hash_multimap равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
### <a name="example"></a>Пример  
  
```cpp  
// hash_multimap_op_eq.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap<int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair<int, int> Int_Pair;  
  
   for (i = 0; i < 3; i++)  
   {  
      hm1.insert(Int_Pair(i, i));  
      hm2.insert(Int_Pair(i, i*i));  
      hm3.insert(Int_Pair(i, i));  
   }  
  
   if ( hm1 == hm2 )  
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;  
  
   if ( hm1 == hm3 )  
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_multimaps hm1 and hm2 are not equal.  
The hash_multimaps hm1 and hm3 are equal.  
```  
  
## <a name="see-also"></a>См. также  
 [<hash_map>](hash-map.md)

