---
title: "Ошибка компилятора C3510 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3510
dev_langs:
- C++
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dddfa1ed7c21f36bebdbefb0049e356bba9cdc8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3510"></a>Ошибка компилятора C3510
не удалось найти библиотеку зависимых типов «библиотека_типов»  
  
 [no_registry](../../preprocessor/no-registry.md) и [auto_search](../../preprocessor/auto-search.md) были переданы `#import` , но компилятор не удалось найти библиотеку типов, на которую указывает ссылка.  
  
 Чтобы устранить эту ошибку, убедитесь, что все библиотеки типов и библиотеках типов доступны в компилятор.  
  
 Следующий пример приводит к возникновению ошибки C3510:  
  
 Предположим, что были созданы следующие два типа библиотеки и что C3510a.tlb был удален или не по пути.  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 И исходный код для второй библиотеки типов:  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 И код клиента:  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```