---
title: "Ошибка BSCMAKE BK1506 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK1506
dev_langs:
- C++
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f553646689fd1e703e10f100bca6d989c8f767d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1506"></a>Ошибка BSCMAKE BK1506
не удается открыть файл «имя_файла» [: причина]  
  
 BSCMAKE не удается открыть файл.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Файл заблокирован другим процессом. Если `reason` говорит **отказано в разрешении**, браузер, использует этот файл. Закройте окно «Обзор» и повторите попытку сборки.  
  
2.  Диск переполнен.  
  
3.  Аппаратная ошибка.  
  
4.  Указанный выходной файл имеет имя, совпадающее с именем существующий подкаталог.