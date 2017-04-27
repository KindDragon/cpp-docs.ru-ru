---
title: "Обзор универсальных типов в Visual C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "сконструированные типы"
  - "сконструированные типы, закрытые [C++]"
  - "сконструированные типы, открытые [C++]"
  - "инициализаторы по умолчанию [C++]"
  - "универсальные [C++], сведения об универсальных шаблонах"
  - "открытые сконструированные типы [C++]"
  - "аргументы типа [C++]"
  - "параметры типа [C++]"
ms.assetid: 21f10637-0fce-4916-b925-6c86a126d3aa
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обзор универсальных типов в Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Универсальные шаблоны — параметризованные типы, поддерживаемые средой CLR.  Параметризованный тип — это тип, определенный неизвестным параметром типа, уточняемым при использовании универсального шаблона.  
  
## Почему универсальные шаблоны?  
 C\+\+ поддерживает шаблоны, а шаблоны и универсальные шаблоны поддерживают параметризованные типы для создания классов типизированных коллекций.  Однако шаблоны обеспечивают параметризацию во время компиляции.  Нельзя ссылаться на сборку, содержащую определение шаблона, и создавать новые специализации шаблона.  После компиляции специализированный шаблон выглядит как любой другой класс или метод.  Напротив, универсальные шаблоны порождаются в MSIL в качестве параметризованного типа, известного среде выполнения как параметризованный тип; исходный код, который ссылается на сборку, содержащую универсальный тип, может создавать специализации универсального типа.  Дополнительные сведения о сравнении шаблонов и универсальных шаблонов Visual C\+\+ см. в разделе [Универсальные типы и шаблоны \(Visual C\+\+\)](../windows/generics-and-templates-visual-cpp.md).  
  
## Универсальные функции и типы  
 Типы классов, пока они являются управляемыми типами, могут быть универсальными.  Примером этого может быть класс `List`.  Типом объекта в списке будет параметр типа.  Если необходим класс `List` для различных типов объектов, до универсальных шаблонов возможно было использовать `List`, принимающий **System::Object** в качестве типа элемента.  Но это позволяет использовать любому объекту \(включая объекты неверного типа\) использоваться в списке.  Такой список будет называться нетипизированным классом коллекции.  В лучшем случае можно проверять тип во время выполнения и создавать исключение.  Или можно использовать шаблон, который будет терять его универсальность при компиляции в сборку.  Пользователи вашей сборки не смогут создавать собственные специализации шаблона.  Универсальные шаблоны позволяют создавать типизированный класс коллекции, например `List<int>` \(читается как «cписок типа int»\) и `List<double>` \(«список типа double»\), которые будут вызывать ошибку компиляции при попытке помещения типа в типизированную коллекцию, которая не была разработана для хранения такого типа.  Кроме того, эти типы остаются универсальными после их компиляции.  
  
 Описание синтаксиса универсальных классов может быть найдено в [Универсальные классы \(C\+\+\/CLI\)](../Topic/Generic%20Classes%20\(C++-CLI\).md)`.` Новое пространство имен, <xref:System.Collections.Generic>, представляет набор параметризованных типов коллекций, включая <xref:System.Collections.Generic.Dictionary%602>, <xref:System.Collections.Generic.List%601> и <xref:System.Collections.Generic.LinkedList%601>.  Дополнительные сведения см. в разделе [Универсальные шаблоны в библиотеке классов платформы .NET Framework](../Topic/Generics%20in%20the%20.NET%20Framework%20Class%20Library%20\(C%23%20Programming%20Guide\).md).  
  
 Экземплярные и статические функции члена класса, делегаты и глобальные функции также могут быть универсальными.  Универсальные функции могут быть необходимы, если параметры функции неизвестного типа, или если сама функция должна работать с универсальными типами.  Во многих случаях, когда **System::Object** мог использоваться в прошлом в качестве параметра для неизвестного типа объектов, вместо этого может использоваться параметр универсального типа, обеспечивая более типобезопасный код.  Любая попытка передать тип, который функция не поддерживает, может быть помечена как ошибка во время компиляции.  При использовании **System::Object** в качестве параметра функции, случайная передача объекта, который функция не была запланирована обрабатывать, не обнаруживается, и необходимо привести неизвестный тип объекта к конкретному типу в теле функции и учитывать возможность InvalidCastException.  С универсальным шаблоном код, пытаясь передать объект в функцию, вызовет конфликт типа, таким образом в тело функции будет гарантированно передан правильный тип.  
  
 Те же преимущества применяются к классам коллекций, построенным на универсальных шаблонах.  Классы коллекций в прошлом могли использовать **System::Object** для хранения элементов в коллекции.  Вставка объектов типа, для которых коллекция не была разработана, не была помечена во время компиляции, и часто даже после вставки объектов.  Как правило, объект будет приведен к другому типу, после обращения к нему в коллекции.  Неизвестный тип будет обнаружен только при ошибке приведения.  Универсальные шаблоны решают эту проблему во время компиляции с помощью обнаружения любого кода, выполняющего вставку типа, который не соответствует \(или неявно преобразован\) параметру типа универсальной коллекции.  
  
 Описание синтаксиса см. в разделе [Универсальные функции \(C\+\+\/CLI\)](../windows/generic-functions-cpp-cli.md).  
  
## Терминология, используемая с универсальными шаблонами  
  
##### Параметры типа  
 Универсальное объявление содержит один или более неизвестных типов *\(параметров типа\)*.  Имя параметра типа означает тип в теле универсального объявления.  Параметр типа используется как тип в теле универсального объявления.  Универсальное объявление для List\<T\> содержит параметр типа T.  
  
##### Аргументы типа  
 *Аргумент типа* — фактический тип, используемый вместо параметра типа, когда универсальный шаблон специализирован для определенного типа или типов.  Например, `int` — аргумент типа в `List<int>`.  Типы значений и типы дескрипторов являются единственными типами, разрешенными в качестве аргумента универсального типа.  
  
##### Сконструированный тип.  
 Тип, созданный из универсального типа — *сконструированный тип*.  Тип может быть не полностью определен, например `List<T>` — это *открытый сконструированный тип*; полностью определенный тип, например `List<double>,` — это *закрытый сконструированный тип* или *специализированный тип*.  Открытые сконструированные типы могут использоваться в определении других универсальных типов или методов и полностью не могут быть указаны до тех пор, пока включающий универсальный шаблон сам не определен.  Например, использование открытого сконструированного типа в качестве базового класса для универсального шаблона:  
  
 `// generics_overview.cpp`  
  
 `// compile with: /clr /c`  
  
 `generic <typename T>`  
  
 `ref class List {};`  
  
 `generic <typename T>`  
  
 `ref class Queue : public List<T> {};`  
  
##### Ограничение  
 Ограничение — это ограничение для типов, которые могут использоваться в качестве параметра типа.  Например, заданный универсальный класс может принимать только классы, производные от указанного класса или реализующие указанный интерфейс.  Для получения дополнительной информации см. [Ограничения, применяемые к параметрам универсальных типов \(C\+\+\/CLI\)](../Topic/Constraints%20on%20Generic%20Type%20Parameters%20\(C++-CLI\).md).  
  
## Ссылочные типы и типы значений  
 Типы дескриптора и типы значений могут использоваться в качестве аргументов типа.  В универсальном определении, в котором может быть использован любой тип, используется синтаксис ссылочных типов.  Например, оператор **\-\>** используется для доступа к членам типа или параметра типа, независимо от того, используется ли в конечном итоге тип как ссылочный тип или тип значения.  Если тип значения используется в качестве аргумента типа, среда выполнения создает код, который использует типы значений напрямую, без упаковки.  
  
 При использовании ссылочного типа в качестве аргумента универсального типа необходимо использовать синтаксис дескриптора.  При использовании типа значения в качестве аргумента универсального типа необходимо использовать имя типа напрямую.  
  
 `// generics_overview_2.cpp`  
  
 `// compile with: /clr`  
  
 `generic <typename T>`  
  
 `ref class GenericType {};`  
  
 `ref class ReferenceType {};`  
  
 `value struct ValueType {};`  
  
 `int main() {`  
  
 `GenericType<ReferenceType^> x;`  
  
 `GenericType<ValueType> y;`  
  
 `}`  
  
## Параметры типа  
 Параметры типа в универсальном классе обрабатываются так же, как и другие идентификаторы.  Однако поскольку тип не известен, существуют ограничения на их использование.  Например, нельзя использовать члены и методы класса параметра типа, если неизвестно, что параметр типа поддерживает эти члены.  Это значит, что для доступа к члену через параметр типа, необходимо добавить тип, содержащий член, в список ограничений параметров типа.  
  
 `// generics_overview_3.cpp`  
  
 `// compile with: /clr`  
  
```  
interface class I {  
   void f1();  
   void f2();  
};  
  
ref struct R : public I {  
   virtual void f1() {}  
   virtual void f2() {}   
   virtual void f3() {}   
};  
  
generic <typename T>  
where T : I  
void f(T t) {  
   t->f1();  
   t->f2();  
   safe_cast<R^>(t)->f3();  
}  
  
int main() {  
   f(gcnew R());  
}  
```  
  
 Эти ограничения также применяются в операторах.  Произвольный параметр универсального типа не может использовать операторы `==` и `!=` для сравнения двух экземпляров параметра типа, на случай, если тип не поддерживает эти операторы.  Эти проверки необходимы для универсальных шаблонов, но не для шаблонов, поскольку универсальные шаблоны могут быть специализированы во время выполнения любым другим классом, удовлетворяющим ограничениям, когда слишком поздно для проверки использования недопустимых членов.  
  
 Экземпляр по умолчанию параметра типа может быть создан с помощью оператора `()`.  Примеры.  
  
 `T t = T();`  
  
 , где `T` является параметром типа в определении универсального класса или метода, инициализирует переменную значением по умолчанию.  Если `T` является ссылочным классом, то это будет пустым указателем; если `T` является классом значений, объект инициализируется нулем.  Это называется *инициализатор по умолчанию*.  
  
## См. также  
 [Универсальные шаблоны](../windows/generics-cpp-component-extensions.md)