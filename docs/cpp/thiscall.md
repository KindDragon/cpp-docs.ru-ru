---
title: "__thiscall | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __thiscall
- __thiscall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a55f7d288758b345dfc4f182f2153e0d39a1b349
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="thiscall"></a>__thiscall
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Соглашение о вызовах `__thiscall` используется для функций-членов. Оно по умолчанию используется функциями членами C++, в которых не используются переменные-аргументы. В соглашении о вызовах `__thiscall` вызываемый метод очищает стек, что невозможно для функций `vararg`. В архитектуре x86 аргументы отправляются в стек справа налево, причем указатель `this` передается через регистр ECX, а не помещается в стек.  
  
 Соглашение о вызовах `__thiscall`, в частности, может использоваться в классах, чьи функции-члены по умолчанию используют `__clrcall`. В этом случае `__thiscall` может использоваться для того, чтобы отдельные функции-члены можно было вызывать из машинного кода.  
  
 При компиляции с параметром [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), все функции и указатели на функции, `__clrcall` Если не указано иное. Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 В версиях до Visual C++ 2005 соглашение о вызовах thiscall не могло быть явным образом указано в программе, поскольку `thiscall` не являлось ключевым словом.  
  
 Функции-члены `vararg` используют соглашение о вызовах `__cdecl`. Все аргументы функции передаются в стеке, причем указатель `this` помещается в стек последним.  
  
 Поскольку это соглашение о вызовах применяется только к C++, схема оформления имени C отсутствует.  
  
 На устройствах ARM и [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] машин `__thiscall` принимается и игнорируется компилятором.  
  
 Если используется внестрочное определение нестатической функции класса, то модификатор соглашения о вызовах не должен быть задан во внестрочном определении. То есть для нестатических методов-членов считается, что соглашение о вызовах, указанное во время объявления, было сделано в точке определения.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md)