---
title: "Ошибка BSCMAKE BK1509 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK1509
dev_langs:
- C++
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4d5fe0a83c5fbc3c4793699975d2045df5fbd8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1509"></a>Ошибка BSCMAKE BK1509
хватает размера кучи  
  
 BSCMAKE не хватило памяти, включая виртуальной памяти.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Освободите место на диске.  
  
2.  Увеличьте размер файла подкачки.  
  
3.  Увеличьте размер файла подкачки Windows.  
  
4.  Уменьшить размер памяти, требуемой BSCMAKE, с помощью параметров /Ei или/ES, чтобы исключить некоторые входные файлы или /Em, чтобы удалить тело макроса.