---
title: "Ошибка компилятора C2144 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2144
dev_langs:
- C++
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e682f0665d3d89853d3927d6bb32ad9217be496
ms.sourcegitcommit: 1e367a5f5c5a6fd0b6018f4fb5edcdf2f1a8085c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="compiler-error-c2144"></a>Ошибка компилятора C2144

> Синтаксическая ошибка: "*тип*«должно предшествовать»*маркера*"

Компилятор ожидал *маркера* и найти *тип* вместо него.

Эта ошибка может быть вызвана отсутствует закрывающая фигурная скобка, правая круглая скобка или точка с запятой.

C2144 также может возникнуть при попытке создать макрос из ключевого слова среды CLR, который содержит символ пробела.

Может также появиться C2144 при попытке передачи типа. В разделе [переадресации типов (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md) для получения дополнительной информации.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2144 и показывает способ по ее устранению.

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

Следующий пример приводит к возникновению ошибки C2144 и показывает способ по ее устранению.

```cpp
// C2144_2.cpp
// compile with: /clr /c
ref struct X {

   property double MultiDimProp[,,] {   // C2144
   // try the following line instead
   // property double MultiDimProp[int , int, int] {
      double get(int, int, int) { return 1; }
      void set(int i, int j, int k, double l) {}
   }

   property double MultiDimProp2[] {   // C2144
   // try the following line instead
   // property double MultiDimProp2[int] {
      double get(int) { return 1; }
      void set(int i, double l) {}
   }
};
```