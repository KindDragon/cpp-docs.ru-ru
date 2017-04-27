---
title: "Операторы &lt;regex&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex/std::operator!=
- regex/std::operator>
- regex/std::operator>=
- regex/std::operator<
- regex/std::operator<=
- regex/std::operator==
- regex/std::operator<<
dev_langs:
- C++
ms.assetid: ec623e65-c186-491f-aa18-6b12b47e1127
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 254eee6065dfc4b11c6eadf82d07fcfb5a7cf4e3
ms.lasthandoff: 02/24/2017

---
# <a name="ltregexgt-operators"></a>Операторы &lt;regex&gt;
||||  
|-|-|-|  
|[оператор!=](#operator_neq)|[оператор&gt;](#operator_gt_)|[оператор&gt;=](#operator_gt__eq)|  
|[оператор&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|[оператор&lt;=](#operator_lt__eq)|  
|[оператор==](#operator_eq_eq)|  
  
##  <a name="operator_neq"></a>  оператор!=  
 Сравнение различных объектов на неравенство.  
  
```  
template <class BidIt>  
bool operator!=(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator!=(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator!=(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator!=(const typename iterator_traits<BidIt>::value_type *left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator!=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type *right);

template <class BidIt>  
bool operator!=(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator!=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);

template <class BidIt, class Alloc>  
bool operator!=(const match_results<BidIt, Alloc>& left,  
    const match_results<BidIt, Alloc>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `BidIt`  
 Тип итератора.  
  
 `IOtraits`  
 Класс характеристик строки.  
  
 `Alloc`  
 Класс распределителя.  
  
 `left`  
 Левый из сравниваемых объектов.  
  
 `right`  
 Правый из сравниваемых объектов.  
  
### <a name="remarks"></a>Примечания  
 Каждый оператор-шаблон возвращает `!(left == right)`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__operator_ne.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "match == " << mr.str() << std::endl;   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "match != match == " << std::boolalpha   
        << (mr != mr) << std::endl;   
    std::cout << "sub != sub == " << std::boolalpha   
        << (sub != sub) << std::endl;   
  
    std::cout << "string(\"aab\") != sub == " << std::boolalpha   
        << (Mystr("aab") != sub) << std::endl;   
    std::cout << "sub != string(\"aab\") == " << std::boolalpha   
        << (sub != Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" != sub == " << std::boolalpha   
        << ("aab" != sub) << std::endl;   
    std::cout << "sub != \"aab\" == " << std::boolalpha   
        << (sub != "aab") << std::endl;   
  
    std::cout << "'a' != sub == " << std::boolalpha   
        << ('a' != sub) << std::endl;   
    std::cout << "sub != 'a' == " << std::boolalpha   
        << (sub != 'a') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == caaa  
sub == aaa  
  
match != match == false  
sub != sub == false  
string("aab") != sub == true  
sub != string("aab") == true  
"aab" != sub == true  
sub != "aab" == true  
'a' != sub == true  
sub != 'a' == true  
```  
  
##  <a name="operator_lt_"></a>  оператор&lt;  
 Сравнение "меньше, чем" для различных объектов.  
  
```  
template <class BidIt>  
bool operator<(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator<(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator<(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator<(const typename iterator_traits<BidIt>::value_type *left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator<(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type *right);

template <class BidIt>  
bool operator<(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator<(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);
```  
  
### <a name="parameters"></a>Параметры  
 `BidIt`  
 Тип итератора.  
  
 `IOtraits`  
 Класс характеристик строки.  
  
 `Alloc`  
 Класс распределителя.  
  
 `left`  
 Левый из сравниваемых объектов.  
  
 `right`  
 Правый из сравниваемых объектов.  
  
### <a name="remarks"></a>Примечания  
 Каждый оператор-шаблон преобразует свои аргументы в тип string и возвращает значение true только в случае, если преобразованное значение `left` оказывается меньше преобразованного значения `right`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__operator_lt.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "sub < sub == " << std::boolalpha   
        << (sub < sub) << std::endl;   
  
    std::cout << "string(\"aab\") < sub == " << std::boolalpha   
        << (Mystr("aab") < sub) << std::endl;   
    std::cout << "sub < string(\"aab\") == " << std::boolalpha   
        << (sub < Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" < sub == " << std::boolalpha   
        << ("aab" < sub) << std::endl;   
    std::cout << "sub < \"aab\" == " << std::boolalpha   
        << (sub < "aab") << std::endl;   
  
    std::cout << "'a' < sub == " << std::boolalpha   
        << ('a' < sub) << std::endl;   
    std::cout << "sub < 'a' == " << std::boolalpha   
        << (sub < 'a') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sub == aaa  
  
sub < sub == false  
string("aab") < sub == false  
sub < string("aab") == true  
"aab" < sub == false  
sub < "aab" == true  
'a' < sub == true  
sub < 'a' == false  
```  
  
##  <a name="operator_lt__lt_"></a>  оператор&lt;&lt;  
 Вставляет в поток sub_match.  
  
```  
template <class Elem, class IOtraits, class Alloc, class BidIt>  
basic_ostream<Elem, IOtraits>& operator<<(basic_ostream<Elem, IOtraits>& os,  
    const sub_match<BidIt>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `Elem`  
 Тип элемента.  
  
 `IOtraits`  
 Класс характеристик строки.  
  
 `Alloc`  
 Класс распределителя.  
  
 `BidIt`  
 Тип итератора.  
  
 `os`  
 Выходной поток.  
  
 `right`  
 Вставляемый объект.  
  
### <a name="remarks"></a>Примечания  
 Оператор-шаблон возвращает `os << right.str()`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__operator_ins.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[0];   
    std::cout << "whole match: " << sub << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
whole match: caaa  
```  
  
##  <a name="operator_lt__eq"></a>  оператор&lt;=  
 Сравнение "меньше или равно" для различных объектов.  
  
```  
template <class BidIt>  
bool operator<=(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator<=(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator<=(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator<=(const typename iterator_traits<BidIt>::value_type *left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator<=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type *right);

template <class BidIt>  
bool operator<=(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator<=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);
```  
  
### <a name="parameters"></a>Параметры  
 `BidIt`  
 Тип итератора.  
  
 `IOtraits`  
 Класс характеристик строки.  
  
 `Alloc`  
 Класс распределителя.  
  
 `left`  
 Левый из сравниваемых объектов.  
  
 `right`  
 Правый из сравниваемых объектов.  
  
### <a name="remarks"></a>Примечания  
 Каждый оператор-шаблон возвращает `!(right < left)`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__operator_le.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "sub <= sub == " << std::boolalpha   
        << (sub <= sub) << std::endl;   
  
    std::cout << "string(\"aab\") <= sub == " << std::boolalpha   
        << (Mystr("aab") <= sub) << std::endl;   
    std::cout << "sub <= string(\"aab\") == " << std::boolalpha   
        << (sub <= Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" <= sub == " << std::boolalpha   
        << ("aab" <= sub) << std::endl;   
    std::cout << "sub <= \"aab\" == " << std::boolalpha   
        << (sub <= "aab") << std::endl;   
  
    std::cout << "'a' <= sub == " << std::boolalpha   
        << ('a' <= sub) << std::endl;   
    std::cout << "sub <= 'a' == " << std::boolalpha   
        << (sub <= 'a') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sub == aaa  
  
sub <= sub == true  
string("aab") <= sub == false  
sub <= string("aab") == true  
"aab" <= sub == false  
sub <= "aab" == true  
'a' <= sub == true  
sub <= 'a' == false  
```  
  
##  <a name="operator_eq_eq"></a>  оператор==  
 Сравнение различных объектов на равенство.  
  
```  
template <class BidIt>  
bool operator==(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator==(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator==(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator==(const typename iterator_traits<BidIt>::value_type* left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator==(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type* right);

template <class BidIt>  
bool operator==(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator==(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);

template <class BidIt, class Alloc>  
bool operator==(const match_results<BidIt, Alloc>& left,  
    const match_results<BidIt, Alloc>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `BidIt`  
 Тип итератора.  
  
 `IOtraits`  
 Класс характеристик строки.  
  
 `Alloc`  
 Класс распределителя.  
  
 `left`  
 Левый из сравниваемых объектов.  
  
 `right`  
 Правый из сравниваемых объектов.  
  
### <a name="remarks"></a>Примечания  
 Каждый оператор-шаблон преобразует каждый из своих аргументов в тип string и возвращает результат сравнения преобразованных объектов на равенство.  
  
 При преобразовании аргументов в тип string оператор-шаблон использует первое из следующего списка преобразований, которое можно применить:  
  
 аргументы, типы которых — специализация класса-шаблона `match_results` или `sub_match`, преобразуются вызовом функции-члена `str`;  
  
 аргументы, типы которых — специализация класса-шаблона `basic_string`, остаются без изменений;  
  
 все остальные типы аргументов преобразуются путем передачи значения аргумента в конструктор для подходящей специализации класса-шаблона `basic_string`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__operator_eq.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "match == " << mr.str() << std::endl;   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "match == match == " << std::boolalpha   
        << (mr == mr) << std::endl;   
    std::cout << "sub == sub == " << std::boolalpha   
        << (sub == sub) << std::endl;   
  
    std::cout << "string(\"aab\") == sub == " << std::boolalpha   
        << (Mystr("aab") == sub) << std::endl;   
    std::cout << "sub == string(\"aab\") == " << std::boolalpha   
        << (sub == Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" == sub == " << std::boolalpha   
        << ("aab" == sub) << std::endl;   
    std::cout << "sub == \"aab\" == " << std::boolalpha   
        << (sub == "aab") << std::endl;   
  
    std::cout << "'a' == sub == " << std::boolalpha   
        << ('a' == sub) << std::endl;   
    std::cout << "sub == 'a' == " << std::boolalpha   
        << (sub == 'a') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == caaa  
sub == aaa  
  
match == match == true  
sub == sub == true  
string("aab") == sub == false  
sub == string("aab") == false  
"aab" == sub == false  
sub == "aab" == false  
'a' == sub == false  
sub == 'a' == false  
```  
  
##  <a name="operator_gt_"></a>  оператор&gt;  
 Сравнение "больше, чем" для различных объектов.  
  
```  
template <class BidIt>  
bool operator>(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator>(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator>(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator>(const typename iterator_traits<BidIt>::value_type *left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator>(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type *right);

template <class BidIt>  
bool operator>(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator>(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);
```  
  
### <a name="parameters"></a>Параметры  
 `BidIt`  
 Тип итератора.  
  
 `IOtraits`  
 Класс характеристик строки.  
  
 `Alloc`  
 Класс распределителя.  
  
 `left`  
 Левый из сравниваемых объектов.  
  
 `right`  
 Правый из сравниваемых объектов.  
  
### <a name="remarks"></a>Примечания  
 Каждый оператор-шаблон возвращает `right < left`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__operator_gt.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "sub > sub == " << std::boolalpha   
        << (sub > sub) << std::endl;   
  
    std::cout << "string(\"aab\") > sub == " << std::boolalpha   
        << (Mystr("aab") > sub) << std::endl;   
    std::cout << "sub > string(\"aab\") == " << std::boolalpha   
        << (sub > Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" > sub == " << std::boolalpha   
        << ("aab" > sub) << std::endl;   
    std::cout << "sub > \"aab\" == " << std::boolalpha   
        << (sub > "aab") << std::endl;   
  
    std::cout << "'a' > sub == " << std::boolalpha   
        << ('a' > sub) << std::endl;   
    std::cout << "sub > 'a' == " << std::boolalpha   
        << (sub > 'a') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sub == aaa  
  
sub > sub == false  
string("aab") > sub == true  
sub > string("aab") == false  
"aab" > sub == true  
sub > "aab" == false  
'a' > sub == false  
sub > 'a' == true  
```  
  
##  <a name="operator_gt__eq"></a>  оператор&gt;=  
 Сравнение "больше или равно" для различных объектов.  
  
```  
template <class BidIt>  
bool operator>=(const sub_match<BidIt>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator>=(
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& left,  
    const sub_match<BidIt>& right);

template <class BidIt, class IOtraits, class Alloc>  
bool operator>=(const sub_match<BidIt>& left,  
    const basic_string<typename iterator_traits<BidIt>::value_type, IOtraits, Alloc>& right);

template <class BidIt>  
bool operator>=(const typename iterator_traits<BidIt>::value_type *left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator>=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type *right);

template <class BidIt>  
bool operator>=(const typename iterator_traits<BidIt>::value_type& left,  
    const sub_match<BidIt>& right);

template <class BidIt>  
bool operator>=(const sub_match<BidIt>& left,  
    const typename iterator_traits<BidIt>::value_type& right);
```  
  
### <a name="parameters"></a>Параметры  
 `BidIt`  
 Тип итератора.  
  
 `IOtraits`  
 Класс характеристик строки.  
  
 `Alloc`  
 Класс распределителя.  
  
 `left`  
 Левый из сравниваемых объектов.  
  
 `right`  
 Правый из сравниваемых объектов.  
  
### <a name="remarks"></a>Примечания  
 Каждый оператор-шаблон возвращает `!(left < right)`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__operator_ge.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::cmatch::string_type Mystr;   
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "sub == " << sub << std::endl;   
    std::cout << std::endl;   
  
    std::cout << "sub >= sub == " << std::boolalpha   
        << (sub >= sub) << std::endl;   
  
    std::cout << "string(\"aab\") >= sub == " << std::boolalpha   
        << (Mystr("aab") >= sub) << std::endl;   
    std::cout << "sub >= string(\"aab\") == " << std::boolalpha   
        << (sub >= Mystr("aab")) << std::endl;   
  
    std::cout << "\"aab\" >= sub == " << std::boolalpha   
        << ("aab" >= sub) << std::endl;   
    std::cout << "sub >= \"aab\" == " << std::boolalpha   
        << (sub >= "aab") << std::endl;   
  
    std::cout << "'a' >= sub == " << std::boolalpha   
        << ('a' >= sub) << std::endl;   
    std::cout << "sub >= 'a' == " << std::boolalpha   
        << (sub >= 'a') << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
sub == aaa  
  
sub >= sub == true  
string("aab") >= sub == true  
sub >= string("aab") == false  
"aab" >= sub == true  
sub >= "aab" == false  
'a' >= sub == false  
sub >= 'a' == true  
```  
  
## <a name="see-also"></a>См. также  
[\<regex>](../standard-library/regex.md)  
[Класс regex_constants](../standard-library/regex-constants-class.md)  
[Класс regex_error](../standard-library/regex-error-class.md)  
[Функции \<regex>](../standard-library/regex-functions.md)  
[Класс regex_iterator](../standard-library/regex-iterator-class.md)  
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)  
[Класс regex_traits](../standard-library/regex-traits-class.md)  
[Определения типов \<regex>](../standard-library/regex-typedefs.md)  


