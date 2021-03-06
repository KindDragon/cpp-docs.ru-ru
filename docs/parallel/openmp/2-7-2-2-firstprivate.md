---
title: "2.7.2.2 firstprivate | Документы Microsoft"
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
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e4f73b3cb418204008fda9962cf67797c8182f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="2722-firstprivate"></a>2.7.2.2 firstprivate
**Firstprivate** предложение предоставляет надмножество функциональные возможности, предоставляемые **закрытый** предложения. Синтаксис **firstprivate** предложение является следующим образом:  
  
```  
firstprivate(variable-list)  
```  
  
 Переменные, указанные в *списка переменной* имеют **закрытый** предложение семантику, как описано в [раздел 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) на странице 25. Инициализация или построение происходит, как если бы оно было выполнить один раз каждого потока, до выполнения потока конструкции. Для **firstprivate** предложение на параллельной конструкции начальное значение нового закрытого объекта — исходный объект, расположенный непосредственно перед параллельной конструкции потока, который встречает значение. Для **firstprivate** предложение на конструкции совместной работы, начальное значение нового закрытого объекта для каждого потока, выполняющего конструкции совместной работы — значение исходный объект, который уже существует до точки времени, тот же поток обнаруживает конструкции совместной работы. Кроме того для объектов C++, новый закрытый объект для каждого потока является копии, созданные из исходного объекта.  
  
 Ограничения, **firstprivate** предложение, следующим образом:  
  
-   Переменная, указанная в **firstprivate** предложение не должны иметь неполный тип или ссылочный тип.  
  
-   Переменная с типом класса, который указан как **firstprivate** должен иметь конструктор копирования, доступный и однозначный.  
  
-   Переменные, которые закрытый внутри параллельной области или, входящие в **сокращения** предложения **параллельных** директива не может быть указана в **firstprivate** предложение на Директива, совместной работы, которая привязывается к параллельной конструкции.