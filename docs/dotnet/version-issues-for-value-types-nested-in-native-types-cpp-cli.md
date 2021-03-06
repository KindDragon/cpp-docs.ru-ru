---
title: "Проблемы версий, связанные с типами значений, вложенными в собственные типы (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __nogc type declarations
- __value keyword, issues when nesting
ms.assetid: 0a3b1a43-39c6-4b52-be2f-1074690188aa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 29a5eb3a085682f243f1497e56b12a0b7d760edb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="version-issues-for-value-types-nested-in-native-types-ccli"></a>Проблемы версий, связанные с типами значений, вложенными в собственные типы (C++/CLI)
Рассмотрим компонент сборки знаком (строгое имя), используемый для построения клиентской сборки. Компонент содержит тип значения, который используется в клиенте в качестве типа члена собственного объединения, класса или массива. Если будущие версии компонента изменяется размер или структура типа значения, должны быть перекомпилированы клиента.  
  
 Создание файла ключа с [sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) (`sn -k mykey.snk`).  
  
## <a name="example"></a>Пример  
 Следующий пример — это компонент.  
  
```  
// nested_value_types.cpp  
// compile with: /clr /LD  
using namespace System::Reflection;  
[assembly:AssemblyVersion("1.0.0.*"),   
assembly:AssemblyKeyFile("mykey.snk")];  
  
public value struct S {  
   int i;  
   void Test() {  
      System::Console::WriteLine("S.i = {0}", i);  
   }  
};  
```  
  
## <a name="example"></a>Пример  
 Этот образец является клиентом:  
  
```  
// nested_value_types_2.cpp  
// compile with: /clr  
#using <nested_value_types.dll>  
  
struct S2 {  
   S MyS1, MyS2;  
};  
  
int main() {  
   S2 MyS2a, MyS2b;  
   MyS2a.MyS1.i = 5;  
   MyS2a.MyS2.i = 6;  
   MyS2b.MyS1.i = 10;  
   MyS2b.MyS2.i = 11;  
  
   MyS2a.MyS1.Test();  
   MyS2a.MyS2.Test();  
   MyS2b.MyS1.Test();  
   MyS2b.MyS2.Test();  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
S.i = 5  
S.i = 6  
S.i = 10  
S.i = 11  
```  
  
### <a name="comments"></a>Комментарии  
 Тем не менее если добавить другой элемент `struct S` в nested_value_types.cpp, (например, `double d;`) и повторно откомпилировать компонент без повторной компиляции клиента, в результате необработанного исключения (типа <xref:System.IO.FileLoadException?displayProperty=fullName>).  
  
## <a name="see-also"></a>См. также  
 [Управляемые типы (C++/CLI)](../dotnet/managed-types-cpp-cli.md)