---
title: "устаревшие (C/C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
dev_langs:
- C++
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5df80fffb5b9cdeabfe19d5a5de6eb771d35d3d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="deprecated-cc"></a>deprecated (C/C++)
**Устаревшими** директивы pragma можно указать, что функции, тип и другие идентификаторы могут не поддерживаться в будущем выпуске или больше не может использоваться.  
> [!NOTE]
> Сведения о C ++ 14 `[[deprecated]]` атрибут и рекомендации по использованию, vs Microsoft declspec или pragma см. в разделе [стандартные атрибуты C++](../cpp/attributes2.md) атрибута.
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma deprecated( identifier1 [,identifier2, ...] )  
```  
  
## <a name="remarks"></a>Примечания  
 Когда компилятор встречает идентификатора, указанного **устаревшими** pragma, он выдает предупреждение компилятора [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md).   
  
 Имена макросов можно объявить нерекомендуемыми. Поместите имя макроса в кавычки; в противном случае произойдет расширение макроса.  
  
 Поскольку **устаревшими** директивы pragma и работает на всех сопоставления идентификаторов, учитывает подписи, он не является лучшим вариантом для исключения устаревшего конкретных версий перегруженных функций. Все сопоставления имени функции добавлены в область действия срабатывает предупреждение.

  Мы рекомендуем использовать C ++ 14 `[[deprecated]]` атрибут, по возможности вместо **устаревшими** pragma. Майкрософт [__declspec(deprecated)](../cpp/deprecated-cpp.md) модификатора объявления также является более предпочтительной, во многих случаях, чем **устаревшими** pragma. `[[deprecated]]` Атрибута и `__declspec(deprecated)` модификатор позволяют определить нерекомендуемое состояние для отдельных форм перегруженных функций. Предупреждение диагностики отображается только для ссылок на конкретных перегруженной функции атрибут или модификатор применяется к.  
  
## <a name="example"></a>Пример  
  
```  
// pragma_directive_deprecated.cpp  
// compile with: /W3  
#include <stdio.h>  
void func1(void) {  
}  
  
void func2(void) {  
}  
  
int main() {  
   func1();  
   func2();  
   #pragma deprecated(func1, func2)  
   func1();   // C4995  
   func2();   // C4995  
}  
```  
  
 В следующем примере показано, как объявить класс устаревшим.  
  
```  
// pragma_directive_deprecated2.cpp  
// compile with: /W3  
#pragma deprecated(X)  
class X {  // C4995  
public:  
   void f(){}  
};  
  
int main() {  
   X x;   // C4995  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)