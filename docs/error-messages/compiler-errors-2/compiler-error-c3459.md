---
title: "Ошибка компилятора C3459 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3459
dev_langs:
- C++
helpviewer_keywords:
- C3459
ms.assetid: 3d290a20-d313-4c07-9bd8-c5c159cb169f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8eaf50c263fdcfbb5c04dc1a92aa0282948f0add
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3459"></a>Ошибка компилятора C3459
"атрибут": атрибут допустим только в индексаторе класса (индексированное свойство по умолчанию)  
  
Атрибут, создаваемый для применения к свойству индексатора класса, использован неправильно.  
  
Дополнительные сведения см. в разделе [как: используйте свойства в C + +/ CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3459.  
  
```  
// C3459.cpp  
// compile with: /clr /c  
public ref class MyString {  
public:  
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3459  
   property int Prop;  
};  
  
// OK  
public ref class MyString2 {  
   array<int>^ MyArr;  
public:  
   MyString2() {  
      MyArr = gcnew array<int>(5);  
   }  
  
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // OK  
   property int default[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
};  
```