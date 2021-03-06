---
title: "Вопросы производительности взаимодействия (C++) | Документы Microsoft"
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
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 25d098ebb52809a36735f71eecedcc4c2a186225
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="performance-considerations-for-interop-c"></a>Вопросы производительности взаимодействия (C++)
В этом разделе описаны рекомендации по уменьшении влияния управляемых и неуправляемых переходов взаимодействия на производительность во время выполнения.  
  
 Visual C++ поддерживает тот же механизм взаимодействия, как в других языках .NET, например Visual Basic и C# (P/Invoke), но он также предоставляет поддержку взаимодействия, относящиеся к Visual C++ (взаимодействие C++). Для приложений с критической производительностью важно понимать влияние на производительность каждого метода взаимодействия.  
  
 Независимо от используемого метода взаимодействия специальные последовательности передачи, называемые преобразователями, требуются при каждом вызове управляемой функцией неуправляемой функции и наоборот. Эти преобразователи автоматически вставляются компилятором Visual C++, но важно помнить, что Суммарно, переходах может быть затратными с точки зрения производительности.  
  
## <a name="reducing-transitions"></a>Уменьшение количества передач  
 Один из способов снижения влияния преобразователей взаимодействия является оптимизация интерфейсов, используемых для минимизации управляемых и неуправляемых переходов. Можно сделать ускоряется обработав активно используемые интерфейсы, которые вовлеченные частые вызовы между неуправляемым и управляемым кодом. Например, управляемой функции, которая вызывает неуправляемую функцию в непрерывном цикле, является хорошим кандидатом для оптимизации кода. Если цикл переместить на неуправляемую сторону или если управляемую альтернативу создается неуправляемый вызов (возможно постановки данных на управляемой стороне и затем маршалинга в неуправляемый API после цикла), количество переходов, может быть уменьшен входа ificantly.  
  
## <a name="pinvoke-vs-c-interop"></a>Vs P/Invoke. взаимодействие C++  
 Для языков .NET, таких как Visual Basic и C# назначенные метод для взаимодействия с собственными компонентами является P/Invoke. Поскольку P/Invoke поддерживается платформой .NET Framework, она также поддерживается Visual C++, но Visual C++ также представлена поддержка взаимодействия, которую называют взаимодействия C++. Взаимодействие C++ предпочтительнее P/Invoke, так как P/Invoke не является строго типизированным. В результате возникают ошибки во время выполнения, но взаимодействие C++ также имеет преимущество в производительности перед P/Invoke.  
  
 Для обоих методов требуется несколько действий при вызове управляемой функцией неуправляемой функции:  
  
-   Аргументы функции маршалируются из среды CLR в собственные типы.  
  
-   Преобразователь управляемый в неуправляемый выполняется.  
  
-   Неуправляемая функция вызывается (с помощью собственных версий аргументов).  
  
-   Выполняется неуправляемого к управляемому преобразованию.  
  
-   Тип возвращаемого значения и любые «out» или «в, out» аргументы маршалируются из собственных — в типы среды CLR.  
  
 Преобразователи управляемого и неуправляемого требуются для взаимодействия работы, но маршалинга данных, который требуется зависит от используемых типов данных, в сигнатуре функции и как эти данные будут использоваться.  
  
 Маршалинг данных с помощью взаимодействия C++ является самым простым: параметры просто копируются через границы управляемого и неуправляемого побитовое образом; преобразование не выполняется вообще. Для вызова P/Invoke, это только значение true, если все параметры являются простыми, преобразуемые типы. В противном случае P/Invoke выполняет очень сложные действия для преобразования каждого управляемого параметра в соответствующий собственный тип и наоборот, если аргументы помечены как «out» или «в, out».  
  
 Другими словами взаимодействия C++ использует быстрый из возможных методов маршалинга данных, в то время как P/Invoke использует наиболее надежный метод. Это означает, что взаимодействие C++ (обычным для C++ способом) по умолчанию, обеспечивает оптимальную производительность и программист несет ответственность за определение случаев, где это поведение не является безопасным или подходящим.  
  
 Таким образом, взаимодействия C++ требует, что маршалинг данных должен быть предоставлен явно, но преимущество, программист может решить, выберите наиболее подходящий для конкретного вида данных и как он будет использоваться. Кроме того несмотря на то, что поведение маршалинга данных P/Invoke можно изменить в степени, взаимодействие C++ позволяет настраивать на основе вызова по вызову маршалинг данных. Это невозможно, с помощью P/Invoke.  
  
 Дополнительные сведения о взаимодействии C++ см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## <a name="see-also"></a>См. также  
 [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)