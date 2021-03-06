---
title: "Класс Platform::Object | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Object::Object
- VCCORLIB/Platform::Object::Equals
- VCCORLIB/Platform::Object::GetHashCode
- VCCORLIB/Platform::Object::ReferenceEquals
- VCCORLIB/Platform::ToString
- VCCORLIB/Platform::GetType
dev_langs:
- C++
helpviewer_keywords:
- Object class
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aa882c22aab21fe82abb2884305bc314997f36a4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="platformobject-class"></a>Класс Platform::Object
Определяет общее поведение для классов и структур ссылок в приложениях среды выполнения Windows. Все экземпляры классов ссылок и структур ссылок могут неявно преобразовываться в Platform::Object^ и переопределять его виртуальный метод ToString.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public ref class Object : Object  
```  
  
### <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Object::Object](#ctor)|Инициализирует новый экземпляр класса Object.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Object::Equals](#equals)|Определяет, равен ли заданный объект текущему объекту.|  
|[Object::GetHashCode](#gethashcode)|Возвращает хэш-код данного экземпляра.|  
|[Object::ReferenceEquals](#referenceequals)|Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.|  
|[ToString](#tostring)|Возвращает строку, представляющую текущий объект. Может быть переопределен.|  
|[GetType](#gettype)|Получает объект [Platform::Type](../cppcx/platform-type-class.md) , описывающий текущий экземпляр.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Object`  
  
 `Object`  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  

  
## <a name="equals"></a> Метод Object::Equals
Определяет, равен ли заданный объект текущему объекту.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
bool Equals(  
    Object^ obj  
)  
```  
  
### <a name="parameters"></a>Параметры  
 obj  
 Объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение`true` , если объекты равны; в противном случае — значение `false`.  
  


## <a name="gethashcode"></a>  Object::GetHashCode Method
Возвращает значение идентификатора `IUnknown`* для этого экземпляра, если это COM-объект, или вычисляемое хэш-значение, если это не COM-объект.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Числовое значение, которое однозначно идентифицирует этот объект.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать GetHashCode для создание ключей объектов в сопоставлениях. Хэш-коды можно сравнивать с помощью [Object::Equals](#equals). Если эта ветвь выполнения кода очень важна, а `GetHashCode` и `Equals` работают недостаточно быстро, можно перейти вниз на соответствующий уровень COM и выполнять сравнение указателей `IUnknown` в неуправляемом коде.  
  


## <a name="gettype"></a>  Метод Object::GetType
Возвращает [Platform::Type](../cppcx/platform-type-class.md) объекта, который описывает тип среды выполнения объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Object::GetType()  
```  

  
### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 Объект [Platform::Type](../cppcx/platform-type-class.md) объекта, который описывает тип среды выполнения объекта.  
  
### <a name="remarks"></a>Примечания  
 Статический [Type::GetTypeCode](../cppcx/platform-type-class.md#gettypecode) можно использовать для получения [перечисление Platform::TypeCode](../cppcx/platform-typecode-enumeration.md) значение, которое представляет текущий тип. Это наиболее полезно для встроенных типов. Код типа для любого класса ссылок помимо [Platform::String](../cppcx/platform-string-class.md) — объект (1).  
  
 [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) класс используется в API Windows как независимый от языка способ передачи сведений о типе между компонентами и приложениями Windows. T[класса Platform::Type](../cppcx/platform-type-class.md) содержит операторы для преобразования между `Type` и `TypeName`.  
  
 Используйте [typeid](../windows/typeid-cpp-component-extensions.md) оператора, возвращающего `Platform::Type` объект для имени класса, например при переходе между страницами XAML:  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## <a name="see-also"></a>См. также  
 [Класс Platform::Type](../cppcx/platform-type-class.md)   
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)   
 [Тип System] (.. /cppcx/Type-System-c-CX.md
  
## <a name="ctor"></a>  Конструктор Object::Object
Инициализирует новый экземпляр класса Object.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
public:Object()  
```  

## <a name="referenceequals"></a>  Метод Object::ReferenceEquals
Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2)  
```  
  
### <a name="parameters"></a>Параметры  
 obj1  
 Первый из сравниваемых объектов.  
  
 obj2  
 Второй из сравниваемых объектов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объекты совпадают; в противном случае — значение `false`.  
 
## <a name="tostring"></a>  Метод Object::ToString (C + +/ CX)
Возвращает строку, представляющую текущий объект.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
public:  
virtual String^ ToString()  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, представляющая текущий объект. Этот метод можно переопределить, чтобы ссылочный класс или структура содержали пользовательскую строку сообщения:  
  
```cpp  
public ref class Tree sealed  
{  
public:  
    Tree(){}  
    virtual Platform::String^ ToString() override  
    {  
      return "I’m a Tree";  
    };  
};  
```  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](platform-namespace-c-cx.md)