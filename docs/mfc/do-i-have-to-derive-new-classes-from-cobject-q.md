---
title: "Необходимо ли создавать новые классы как производные от CObject? | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c485bba4d62d279b0f17b887080284940a8bbdd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Необходимо ли создавать новые классы как производные от CObject?
Нет, не.  
  
 Производный класс [CObject](../mfc/reference/cobject-class.md) при необходимости помещениях, он предоставляет, например сериализации или динамических creatability. Множество классов данных необходимо сериализовать в файлы, поэтому часто рекомендуется наследовать их из `CObject`. Для примера класса, производного от `CObject`, в разделе [пример Scribble](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>См. также  
 [Класс CObject. Часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)
