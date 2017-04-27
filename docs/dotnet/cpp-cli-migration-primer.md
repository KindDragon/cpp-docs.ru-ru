---
title: "Основы миграции C++/CLI | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++/CLI версия 2"
  - "C++/CLI версия 2, ManagedExtensions"
  - "Управляемые расширения для C++, обновление синтаксиса"
  - "перенос [C++], C++/CLI версия 2"
  - "обновление приложений Visual C++, Синтаксис управляемых расширений для C++ к Visual C++ 2005"
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Основы миграции C++/CLI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот раздел является руководством по переносу ваших программ, написанных на Visual C\+\+, из управляемых расширений C\+\+ в [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  Перечень изменений в синтаксисе представлен в разделе [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](http://msdn.microsoft.com/ru-ru/edbded88-7ef3-4757-bd9d-b8f48ac2aada).  
  
 C\+\+\/CLI является расширением парадигмы программирования динамических компонентов до уровня стандартного языка ISO\-C\+\+.  По сравнению с управляемыми расширениями, в этом новом языке представлен целый рад существенных усовершенствований.  В этом разделе представлен нумерованный перечень управляемых расширений функций языка C\+\+ и их соответствие на [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], если такое отображение существует, а также даны указания на конструкции, для которых соответствия не существует.  
  
## Содержание  
 [Обзор изменений \(C\+\+\/CLI\)](../dotnet/outline-of-changes-cpp-cli.md)  
 Общий краткий обзор изменений по пяти основным категориям.  
  
 [Ключевые слова языка \(C\+\+\/CLI\)](../Topic/Language%20Keywords%20\(C++-CLI\).md)  
 Рассматриваются изменения в ключевых словах языка, в частности исключение символа двойного подчеркивания, а также введение контекстных ключевых слов и ключевых слов с символом пробела.  
  
 [Управляемые типы \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)  
 Рассматриваются изменения в синтаксисе объявления Системы общих типов \(CTS\), в частности, изменения в объявлении классов, массивов \(включая массивы параметров\), перечислений и т. д.  
  
 [Объявления членов в пределах класса или интерфейса \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)  
 Описание изменений, касающихся членов классов, таких как скалярные свойства, свойства индексов, операторы, делегаты и события.  
  
 [Типы значений и их режимы работы \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 Описание типов значений и нового семейства внутренних и закрепляющих указателей.  Также обсуждается целый ряд существенных изменений в семантике, например, внедрение неявной упаковки, неизменность упакованных типов значений, а также исключение поддержки конструкторов по умолчанию внутри классов значений.  
  
 [Общие изменения в языке](../Topic/General%20Language%20Changes%20\(C++-CLI\).md)  
 Подробно рассматриваются изменения в семантике, такие как поддержка приведения к типу, поведение строковых литералов, а также изменения в семантике между ISO\-C\+\+ и C\+\+\/CLI.  
  
## См. также  
 [Смешанные \(собственные и управляемые\) сборки](../Topic/Mixed%20\(Native%20and%20Managed\)%20Assemblies.md)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)