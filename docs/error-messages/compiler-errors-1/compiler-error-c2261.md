---
title: "Ошибка компилятора C2261 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3907a1d270de11af82462815ce87398e10c50513
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2261"></a>Ошибка компилятора C2261
«Строка»: ссылка на сборку, является недопустимым и не может быть разрешена  
  
 Значение не является допустимым.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>используется для указания дружественной сборки. Например, если указать в качестве дружественной сборки b.dll a.dll, следует указать (в a.dll): InternalsVisibleTo("b"). Затем среда выполнения позволяет b.dll полный доступ к a.dll (за исключением частных типов).  
  
 Дополнительные сведения об использовании правильного синтаксиса при указании дружественных сборок см [дружественные сборки (C++)](../../dotnet/friend-assemblies-cpp.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2261.  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```