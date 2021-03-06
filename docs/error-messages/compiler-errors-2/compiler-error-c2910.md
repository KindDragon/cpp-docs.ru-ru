---
title: "Ошибка компилятора C2910 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2910
dev_langs:
- C++
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 202593b506fc957fb98cc390c1874312509ea481
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2910"></a>Ошибка компилятора C2910
«функция»: явная специализация невозможна  
  
 Компилятор обнаружил попытку явно специализации функции.  
  
 Следующий пример приводит к возникновению ошибки C2910:  
  
```  
// C2910.cpp  
// compile with: /c  
template <class T>  
struct S;  
  
template <> struct S<int> { void f() {} };  
template <> void S<int>::f() {}   // C2910 delete this specialization  
```  
  
 C2910 также может возникать при попытке явной специализации нешаблонного элемента. То есть можно только явно специализировать шаблон функции.  
  
 Следующий пример приводит к возникновению ошибки C2910:  
  
```  
// C2910b.cpp  
// compile with: /c  
template <class T> struct A {  
   A(T* p);  
};  
  
template <> struct A<void> {  
   A(void* p);  
};  
  
template <class T>  
inline A<T>::A(T* p) {}  
  
template <> A<void>::A(void* p){}   // C2910  
// try the following line instead  
// A<void>::A(void* p){}  
```  
  
 Эта ошибка может также возникать в результате изменений работы компилятора в Visual Studio .NET 2003:.  
  
 Код будет допустим в версиях Visual C++ для Visual Studio .NET 2003 и Visual Studio .NET, удалите `template <>`.  
  
 Следующий пример приводит к возникновению ошибки C2910:  
  
```  
// C2910c.cpp  
// compile with: /c  
template <class T> class A {  
   void f();  
};  
  
template <> class A<int> {  
   void f();  
};  
  
template <> void A<int>::f() {}   // C2910  
// try the following line instead  
// void A<int>::f(){}   // OK  
```