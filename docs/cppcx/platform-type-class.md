---
title: "Класс Platform::Type | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
dev_langs:
- C++
helpviewer_keywords:
- Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cabfa3d382d44448b2c06d0a16864a4fdd0e66bf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="platformtype-class"></a>Класс Platform::Type
Содержит сведения среды выполнения о типе — в частности, имя строки и код типа. Получается вызовом [Object::GetType](../cppcx/platform-object-class.md#gettype) в любом объекте или или с помощью [typeid](../windows/typeid-cpp-component-extensions.md) оператора в имени класса или структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public ref class Platform::Type :      
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable  
```  
  
### <a name="remarks"></a>Примечания  
 Класс `Type` удобен в приложениях, где должна выполняться непосредственная обработка с использованием оператора `if` или `switch` , образующего ветви на основе типа объекта времени выполнения. Код типа, описывающий категорию типа, извлекается с помощью [Type::GetTypeCode](#gettypecode) функции-члена.  
  
## <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|[Метод Type::GetTypeCode](#gettypecode)|Возвращает значение [Перечисление Platform::TypeCode](../cppcx/platform-typecode-enumeration.md) для объекта.| 
|[Метод Type::ToString](#tostring)|Возвращает имя типа, указанного в метаданных.| 

 
## <a name="public-properties"></a>Открытые свойства  
  
|||  
|-|-|  
|[Type::FullName](#fullname)|Возвращает [Класс Platform::String](../cppcx/platform-string-class.md)^, который представляет полное имя типа и использует . (точка) в качестве разделителя, не:: (двойное двоеточие) — например, `MyNamespace.MyClass`.|  
  
## <a name="conversion-operators"></a>Операторы преобразования  
  
|||  
|-|-|  
|[оператор Type^](../cppcx/operator-subtracttype-hat.md)|Обеспечивает преобразование `Windows::UI::Xaml::Interop::TypeName` в `Platform::Type`.|  
|[оператор Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)|Обеспечивает преобразование `Platform::Type` в `Windows::UI::Xaml::Interop::TypeName`.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  

 
## <a name="fullname"></a> Свойство Type::FullName
Получает полное имя текущего типа в виде `Namespace.Type`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
String^ FullName();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя типа.  
### <a name="example"></a>Пример  
  
```  
  
//  namespace is TestApp  
MainPage::MainPage()  
{  
    InitializeComponent();  
    Type^ t = this->GetType();  
    auto s = t->FullName; // returns "TestApp.MainPage"  
    auto s2 = t->ToString(); //also returns "TestApp.MainPage"  
}  
```  
  


## <a name="gettypecode"></a> Метод Type::GetTypeCode
Возвращает числовой тип категории встроенных типов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Platform::TypeCode GetTypeCode();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из значений перечисления Platform::TypeCode.  
  
### <a name="remarks"></a>Примечания  
 Эквивалентом метода-члена GetTypeCode() является `typeid` свойства.

## <a name="tostring">Метод Type::ToString</a>
Получает имя типа.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Platform::String^ ToString();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя типа, указанного в метаданных.    
  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)