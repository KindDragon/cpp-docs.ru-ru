---
title: "Предупреждение (уровень 1) C4364 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4364
dev_langs:
- C++
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d532ff9cc030c92543bec898f34daf3559531f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4364"></a>Предупреждение компилятора (уровень 1) C4364
\#с помощью для сборки «файл», полученные ранее в location(line_number) без атрибута as_friend; as_friend не применяется  
  
 Объект `#using` директива была повторена для данного файла метаданных, но `as_friend` квалификатор не использовался в первом случае; компилятор игнорирует второй `as_friend`.  
  
 Дополнительные сведения см. в разделе [дружественные сборки (C++)](../../dotnet/friend-assemblies-cpp.md).  
  
## <a name="example"></a>Пример  
 В следующем примере создается компонент.  
  
```  
// C4364.cpp  
// compile with: /clr /LD  
ref class A {};  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4364.  
  
```  
// C4364_b.cpp  
// compile with: /clr /W1 /c  
#using " C4364.dll"  
#using " C4364.dll" as_friend   // C4364  
```