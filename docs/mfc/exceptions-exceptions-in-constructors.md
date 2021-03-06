---
title: "Исключения: Исключения в конструкторах | Документы Microsoft"
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
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc17821e2dd358a4b8f596492fa46c2b7412feed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-exceptions-in-constructors"></a>Исключения. Исключения в конструкторах
При создании исключения в конструкторе, очистить все объекты и выделения памяти внесенные до возникновения исключения, как описано в статье [исключения: создание исключений из свои собственные функции](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).  
  
 При создании исключения в конструкторе, для самого объекта уже выделена память к моменту вызова конструктора. Таким образом компилятор автоматически будет освобождать память, занятую объекта после исключения.  
  
 Дополнительные сведения см. в разделе [исключения: освобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

