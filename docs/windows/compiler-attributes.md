---
title: "Атрибуты компилятора | Документы Microsoft"
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
- cl.exe compiler, attributes
- attributes [C++], compiler
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e83743859d4c4bdfb515df6008969a9cc7b56e2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-attributes"></a>Атрибуты компилятора
Атрибуты компилятора предоставляют широкий набор функциональных возможностей.  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|[emitidl](../windows/emitidl.md)|Определяет, будут обработаны и помещен в сгенерированный IDL-файл все последующие атрибуты IDL.|  
|[event_receiver](../windows/event-receiver.md)|Создает приемник событий.|  
|[event_source](../windows/event-source.md)|Создает источник событий.|  
|[export](../windows/export.md)|В результате структуру данных помещается в IDL-файл.|  
|[реализует](../windows/implements-cpp.md)|Задает интерфейсы диспетчеризации, преобразуются в качестве членов IDL coclass.|  
|[importidl](../windows/importidl.md)|Вставляет указанный IDL-файла в сгенерированный IDL-файл.|  
|[importlib](../windows/importlib.md)|Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.|  
|[includelib](../windows/includelib-cpp.md)|В результате файл IDL или .h, должны быть включены в сгенерированный IDL-файл.|  
|[library_block](../windows/library-block.md)|Помещает конструкцию внутри блока библиотеки IDL-файл.|  
|[no_injected_text](../windows/no-injected-text.md)|Запрещает компилятору встраивать код в результате использования атрибута.|  
|[satype](../windows/satype.md)|Указывает тип данных **SAFEARRAY**.|  
|[version](../windows/version-cpp.md)|Определяет конкретную версию несколькими версиями интерфейс или класс.|  
  
## <a name="see-also"></a>См. также  
 [Список атрибутов по группам](../windows/attributes-by-group.md)