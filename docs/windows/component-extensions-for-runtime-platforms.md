---
title: "Расширения компонентов для платформ среды выполнения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- what's new [C++], keywords
- what's new [C++], language features
- Visual C++, keywords
- keywords [C++]
- Managed Extensions for C++, replacement syntax
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e32057e17614da98c78d877fe95180dd02500909
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="component-extensions-for-runtime-platforms"></a>Расширения компонентов для платформ среды выполнения
Visual C++ предоставляет расширения языка, помогающие при программировании для различных платформ. С помощью C + +/ CX, вы можете программировать приложений универсальной платформы Windows и компонентов, которые компилируются в машинный код. Несмотря на то, что можно создавать приложения универсальной платформы Windows путем программирования непосредственно для интерфейсов COM среды выполнения Windows, с помощью C + +/ CX, можно работать с конструкторами, исключениями и другими современными идиомами программирования C++. Чтобы включить программирования на языке C++ в управляемой среде выполнения на платформе .NET, можно использовать C + +/ CLI.  
  
 **Две среды выполнения, один набор расширений**  
  
 C + +/ CX является подмножеством C + +/ CLI. Для расширений, которые являются общими для C + +/ CX и C + +/ CLI, семантика зависит от ориентации общеязыковой среды выполнения (CLR) или среды выполнения Windows. Чтобы скомпилировать приложение будет работать в среде выполнения Windows, укажите **/zw** параметр компилятора. Чтобы скомпилировать приложение для запуска в среде CLR, укажите **/CLR** параметр компилятора. Если для создания проекта используется Visual Studio, эти параметры устанавливаются автоматически.  
  
 Дополнительные сведения о создании приложений универсальной платформы Windows в C++ см. в разделе [стратегия для приложений среды выполнения Windows с помощью C++](http://msdn.microsoft.com/library/windows/apps/hh700360.aspx).  
  
 C + +/ CLI расширяет стандарт ISO/ANSI C++ и определяется в разделе Ecma C + +/ CLI Standard. Дополнительные сведения см. в разделе [программирование .NET с использованием C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
## <a name="data-type-keywords"></a>Ключевые слова типов данных  
 Расширения языка содержат *агрегатные ключевые слова*, это ключевые слова, состоящие из двух токенов, разделенных пробелом. Когда токены используются отдельно, они могут иметь одно значение, а при использовании вместе — другое значение. Например, ключевое слово "ref" — это обычный идентификатор, а слово "class" — ключевое слово, объявляющее собственный класс. Но при объединении этих слов форму `ref class`, полученное агрегатное ключевое слово объявляет сущность, которая называется *класса среды выполнения*.  
  
 Расширения также содержат *контекстно-зависимые* ключевые слова. Ключевое слово рассматривается как контекстно-зависимое на основе типа содержащего его оператора и размещения в нем. Например, токен "property" может быть идентификатором или может объявлять специальный тип открытого члена класса.  
  
 В следующей таблице перечислены ключевые слова в расширении языка C++.  
  
|Ключевое слово|Контекстно-зависимое?|Цель|Ссылка|  
|-------------|-----------------------|-------------|---------------|  
|`ref class`<br /><br /> `ref struct`|Нет|Объявляет класс.|[Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`value class`<br /><br /> `value struct`|Нет|Объявляет класс значения.|[Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`interface class`<br /><br /> `interface struct`|Нет|Объявляет интерфейс.|[класс интерфейса](../windows/interface-class-cpp-component-extensions.md)|  
|`enum class`<br /><br /> `enum struct`|Нет|Объявляет перечисление.|[Класс перечисления](../windows/enum-class-cpp-component-extensions.md)|  
|`property`|Да|Объявляет свойство.|[свойство](../windows/property-cpp-component-extensions.md)|  
|`delegate`|Да|Объявляет делегат.|[delegate (расширения компонентов C++)](../windows/delegate-cpp-component-extensions.md)|  
|`event`|Да|Объявление события.|[event](../windows/event-cpp-component-extensions.md)|  
  
## <a name="override-specifiers"></a>Спецификаторы переопределения  
 Для указания поведения переопределения при наследовании можно использовать указанные ниже ключевые слова. Хотя ключевое слово `new` не является расширением C++, оно перечислено ниже, поскольку его можно использовать в дополнительном контексте. Некоторые спецификаторы также допустимы для машинного программирования. Дополнительные сведения см. в разделе [как: объявление спецификаторов переопределения в компиляциях машинного кода (C + +/ CLI)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
|Ключевое слово|Контекстно-зависимое?|Цель|Ссылка|  
|-------------|-----------------------|-------------|---------------|  
|`abstract`|Да|Указывает, что функции или классы являются абстрактными.|[abstract](../windows/abstract-cpp-component-extensions.md)|  
|`new`|Нет|Указывает, что функция не является переопределением версии базового класса.|[New (новый слот в vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|  
|`override`|Да|Указывает, что метод должен быть переопределением версии базового класса.|[override](../windows/override-cpp-component-extensions.md)|  
|`sealed`|Да|Предотвращает использование классов в качестве базовых классов.|[sealed](../windows/sealed-cpp-component-extensions.md)|  
  
## <a name="keywords-for-generics"></a>Ключевые слова для универсальных шаблонов  
 Указанные ниже ключевые слова добавлены для поддержки универсальных типов. Дополнительные сведения см. в статье [Универсальные шаблоны](../windows/generics-cpp-component-extensions.md).  
  
|Ключевое слово|Контекстно-зависимое?|Цель|  
|-------------|-----------------------|-------------|  
|`generic`|Нет|Объявляет универсальный тип.|  
|`where`|Да|Определяет ограничения, применяемые к параметру универсального типа.|  
  
## <a name="miscellaneous-keywords"></a>Прочие ключевые слова  
 В расширения C++ добавлены следующие ключевые слова.  
  
|Ключевое слово|Контекстно-зависимое?|Цель|Ссылка|  
|-------------|-----------------------|-------------|---------------|  
|`finally`|Да|Указывает поведение обработки исключений по умолчанию.|[Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)|  
|`for each, in`|Нет|Перечисляет элементы коллекции.|[for each, in](../dotnet/for-each-in.md)|  
|`gcnew`|Нет|Выделяет типы в куче со сбором мусора. Используйте вместо `new` и `delete`.|[новые возможности, gcnew ref](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`ref new`|Да|Выделяет тип среды выполнения Windows. Используйте вместо `new` и `delete`.|[новые возможности, gcnew ref](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`initonly`|Да|Указывает, что член можно инициализировать только в объявлении или в статическом конструкторе.|[initonly (C++/CLI)](../dotnet/initonly-cpp-cli.md)|  
|`literal`|Да|Создает переменную литерала.|[литерал](../windows/literal-cpp-component-extensions.md)|  
|`nullptr`|Нет|Означает, что обработчик или указатель не указывает на объект.|[nullptr](../windows/nullptr-cpp-component-extensions.md)|  
  
## <a name="template-constructs"></a>Конструкции шаблонов  
 Перечисленные ниже языковые конструкции реализуются в виде шаблонов, а не ключевых слов. При указании **/ZW** параметр компилятора они определены в `lang` пространства имен. При указании **/CLR** параметр компилятора они определены в `cli` пространства имен.  
  
|Ключевое слово|Цель|Ссылка|  
|-------------|-------------|---------------|  
|`array`|Объявляет массив.|[Массивы](../windows/arrays-cpp-component-extensions.md)|  
|`interior_ptr`|(Только для среды CLR). Указывает на данные в ссылочном типе.|[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)|  
|`pin_ptr`|(Только для среды CLR). Указывает на ссылочные типы среды CLR, чтобы временно отключить систему сборки мусора.|[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)|  
|`safe_cast`|Определяет и выполняет оптимальный метод приведения для типа среды выполнения.|[safe_cast](../windows/safe-cast-cpp-component-extensions.md)|  
|`typeid`|(Только для среды CLR). Извлекает объект <xref:System.Type?displayProperty=fullName>, описывающий заданный тип или объект.|[typeid](../windows/typeid-cpp-component-extensions.md)|  
  
## <a name="declarators"></a>Деклараторы  
 Следующие деклараторы типа указывают среде выполнения на необходимость автоматически управлять временем существования и удалением выделенных объектов.  
  
|Оператор|Цель|Ссылка|  
|--------------|-------------|---------------|  
|`^`|Объявляет дескриптор объекта. то есть, указатель на объект среды выполнения Windows или среды CLR, который автоматически удаляется, если он больше не используется.|[Оператор дескриптора объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|  
|`%`|Объявляет отслеживаемую ссылку; который является ссылкой на объект среды выполнения Windows или среды CLR, который автоматически удаляется, если он больше не используется.|[Оператор отслеживания ссылок](../windows/tracking-reference-operator-cpp-component-extensions.md)|  
  
## <a name="additional-constructs-and-related-topics"></a>Дополнительные конструкции и связанные разделы  
 В этом разделе перечислены дополнительные программные конструкции и разделы, относящиеся к среде CLR.  
  
|Раздел|Описание:|  
|-----------|-----------------|  
|[__identifier (C++/CLI)](../windows/identifier-cpp-cli.md)|(Среды выполнения Windows и среды CLR) Позволяет использовать ключевые слова в качестве идентификаторов.|  
|[Списки аргументов переменной длины (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|(Среды выполнения Windows и среды CLR) Разрешает функции принимать переменное число аргументов.|  
|[Эквиваленты собственным типам C++ в .NET Framework (C++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|Перечисляет типы среды CLR, используемые вместо целочисленных типов C++.|  
|[AppDomain](../cpp/appdomain.md) `__declspec` модификатор|Модификатор `__declspec`, требующий, чтобы статические и глобальные переменные существовали для каждого домена приложений.|  
|[C-стиль приведения с параметром/CLR (C + +/ CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)|Описывается интерпретация приведений в стиле C.|  
|[__clrcall](../cpp/clrcall.md) соглашение о вызовах|Указывается соглашение о вызовах, совместимое со средой CLR.|  
|`__cplusplus_cli`|[Предопределенные макросы](../preprocessor/predefined-macros.md)|  
|[Настраиваемые атрибуты](../windows/custom-attributes-cpp.md)|Описывается определение собственных атрибутов среды CLR.|  
|[Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)|Общие сведения об обработке исключений.|  
|[Явные переопределения](../windows/explicit-overrides-cpp-component-extensions.md)|Демонстрируется переопределение произвольных членов функциями-членами.|  
|[Дружественные сборки (C++)](../dotnet/friend-assemblies-cpp.md)|Описывается доступ клиентской сборки ко всем типам в компоненте сборки.|  
|[Упаковка-преобразование](../windows/boxing-cpp-component-extensions.md)|Описываются условия, при которых упаковываются типы значений.|  
|[Поддержка характеристик типов компилятором](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|Описывается выявление характеристик типов во время компиляции.|  
|[управляемые, неуправляемые](../preprocessor/managed-unmanaged.md) директивы pragma|Демонстрируется сосуществование управляемых и неуправляемых функций в одном модуле.|  
|[процесс](../cpp/process.md) `__declspec` модификатор|Модификатор `__declspec`, требующий, чтобы статические и глобальные переменные существовали для каждого процесса.|  
|[Отражение (C++/CLI)](../dotnet/reflection-cpp-cli.md)|Демонстрируется CLR-версия данных типа во время выполнения.|  
|[String](../windows/string-cpp-component-extensions.md)|Описывается преобразование компилятором строковых литералов в объект <xref:System.String>.|  
|[Перенаправление типов (C++/CLI)](../windows/type-forwarding-cpp-cli.md)|Разрешает перемещение типа из поставляемой сборки в другую сборку, чтобы исключить необходимость повторной компиляции клиентского кода.|  
|[Пользовательские атрибуты](../windows/user-defined-attributes-cpp-component-extensions.md)|Демонстрируются атрибуты, определяемые пользователем.|  
|[Директива #using](../preprocessor/hash-using-directive-cpp.md)|Импортирует внешние сборки.|  
|[Документация XML](../ide/xml-documentation-visual-cpp.md)|Пояснения к документации в XML-коду с помощью  [ /doc (обработка комментариев документации) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
  
## <a name="see-also"></a>См. также  
 [Программирование .NET с использованием C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)