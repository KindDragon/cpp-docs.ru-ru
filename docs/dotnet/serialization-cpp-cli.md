---
title: "Сериализация (C + +/ CLI) | Документы Microsoft"
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
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6efd56655cb5b262eab7d7f14c197e11466fb8bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="serialization-ccli"></a>Сериализация (C++/CLI)
Сериализация (процесс сохранения состояния объекта или элемента на постоянный носитель) управляемых классов (в том числе отдельных полей или свойств) поддерживается <xref:System.SerializableAttribute> и <xref:System.NonSerializedAttribute> классы.  
  
## <a name="remarks"></a>Примечания  
 Применить **SerializableAttribute** настраиваемого атрибута для управляемого класса, чтобы сериализовать весь класс, или только к определенным полям или свойствам, чтобы сериализовать части управляемого класса. Используйте **NonSerializedAttribute** настраиваемого атрибута для освобождения поля или свойства управляемого класса из сериализации.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем примере класс `MyClass` (и свойство `m_nCount`) помечен как сериализуемый. Тем не менее `m_nData` свойство не является сериализуемым, как обозначается **NonSerialized** настраиваемых атрибутов:  
  
### <a name="code"></a>Код  
  
```  
// serialization_and_mcpp.cpp  
// compile with: /LD /clr  
using namespace System;  
  
[ Serializable ]  
public ref class MyClass {  
public:  
   int m_nCount;  
private:  
   [ NonSerialized ]  
   int m_nData;  
};  
```  
  
### <a name="comments"></a>Комментарии  
 Обратите внимание, что оба атрибута можно ссылаться с помощью их «краткое имя» (**Serializable** и **NonSerialized**). Далее приведено [применение атрибутов](/dotnet/standard/attributes/applying-attributes).  
  
## <a name="see-also"></a>См. также  
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)