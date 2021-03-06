---
title: "Класс ActivationFactory | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactory class
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73690603b1be1dd74b7ae7626372e3ab6ff9101e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="activationfactory-class"></a>ActivationFactory - класс
Позволяет одному или нескольким классам быть активированными средой выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `I0`  
 Интерфейс нулевой.  
  
 `I1`  
 Первый интерфейс.  
  
 `I2`  
 Второй интерфейс.  
  
## <a name="remarks"></a>Примечания  
 ActivationFactory предоставляет методы регистрации и базовую функциональность для интерфейса представляет интерфейс IActivationFactory. ActivationFactory позволяет для реализации пользовательской фабрики.  
  
 Символически в следующем фрагменте кода показано, как использовать ActivationFactory.  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 В следующем фрагменте кода показано, как использовать [реализует](../windows/implements-structure.md) структура для указания более чем на три интерфейса идентификаторы.  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор ActivationFactory::ActivationFactory](../windows/activationfactory-activationfactory-constructor.md)|Инициализирует класс ActivationFactory.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод ActivationFactory::AddRef](../windows/activationfactory-addref-method.md)|Увеличивает значение счетчика ссылок объекта ActivationFactory.|  
|[Метод ActivationFactory::GetIids](../windows/activationfactory-getiids-method.md)|Извлекает массив идентификаторов реализованного интерфейса.|  
|[Метод ActivationFactory::GetRuntimeClassName](../windows/activationfactory-getruntimeclassname-method.md)|Возвращает имя класса среды выполнения объекта, который создает экземпляр текущего ActivationFactory.|  
|[Метод ActivationFactory::GetTrustLevel](../windows/activationfactory-gettrustlevel-method.md)|Возвращает объект, который создает экземпляр текущего ActivationFactory уровень доверия.|  
|[Метод ActivationFactory::QueryInterface](../windows/activationfactory-queryinterface-method.md)|Извлекает указатель на указанный интерфейс.|  
|[Метод ActivationFactory::Release](../windows/activationfactory-release-method.md)|Уменьшает счетчик ссылок объекта ActivationFactory.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ActivationFactory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)