---
title: "Переопределяемые CWinApp функции-члены | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 64775ad9f44c55529107b50d0695e95e2b9c3a2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="overridable-cwinapp-member-functions"></a>Переопределяемые функции-члены CWinApp
[CWinApp](../mfc/reference/cwinapp-class.md) предоставляет несколько ключевых функций переопределяемый член (`CWinApp` переопределяет эти члены из класса [CWinThread](../mfc/reference/cwinthread-class.md), из которого `CWinApp` производный):  
  
-   [InitInstance](../mfc/initinstance-member-function.md)  
  
-   [Выполнить](../mfc/run-member-function.md)  
  
-   [ExitInstance](../mfc/exitinstance-member-function.md)  
  
-   [OnIdle](../mfc/onidle-member-function.md)  
  
 Единственным `CWinApp` , необходимо переопределить функцию-член `InitInstance`.  
  
## <a name="see-also"></a>См. также  
 [CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
