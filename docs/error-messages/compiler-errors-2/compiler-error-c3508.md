---
title: "Ошибка компилятора C3508 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3508
dev_langs:
- C++
helpviewer_keywords:
- C3508
ms.assetid: 16d08f89-2f32-44eb-9421-68acecddf49b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63586ffd3157aa91ddf7ccb1ec47b6f1c45bc5d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3508"></a>Ошибка компилятора C3508
«Тип»: не является допустимым типом автоматизации  
  
 Указан недопустимый тип.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3508:  
  
```  
// C3508.cpp  
#define _ATL_DEBUG_QI  
  
#define WIN32_LEAN_AND_MEAN  
#define STRICT  
#ifndef _WIN32_WINNT  
#define _WIN32_WINNT 0x0400  
#endif  
  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
extern CComModule _Module;  
#include <atlcom.h>  
#include <atlctl.h>  
#include <atlstr.h>  
  
extern "C" int printf_s(const char*, ...);  
  
[module(name=oso)];  
  
union U  
// try the following two lines instead  
// [export]  
// struct U  
{  
   int i, j;  
};  
  
[dispinterface]  
__interface I  
{  
   [id(1)] HRESULT func(U* u);  
};  
  
[coclass]  
struct C : I  
{  
   HRESULT func(U*)   // C3508  
   {  
      return E_FAIL;  
   }  
};  
  
int main()  
{  
}  
```