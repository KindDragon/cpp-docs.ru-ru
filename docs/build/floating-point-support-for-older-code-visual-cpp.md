---
title: "Поддержка плавающей запятой для устаревшего кода (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 130b6efb1c05775cd7859144d91a30051fb4ca53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="floating-point-support-for-older-code-visual-c"></a>Поддержка плавающей запятой для устаревшего кода (Visual C++)
MMX и регистры с плавающей запятой стека (MM0-MM7/ST0-ST7) сохраняются между переключений контекста.  Нет явного соглашение о вызовах для этих регистров.  Запрещено использование этих регистров в коде режима ядра.  
  
## <a name="see-also"></a>См. также  
 [Соглашение о вызовах](../build/calling-convention.md)