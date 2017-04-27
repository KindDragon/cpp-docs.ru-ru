---
title: "Ошибка вычислителя выражений CXX0017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0017"
  - "CXX0017"
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка вычислителя выражений CXX0017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

символ не найден  
  
 Не удалось найти символ, указанный в выражении.  
  
 Одной из возможных причин данной ошибки является несоответствие регистров в имени символа.  Так как языки C и C\+\+ чувствительны к регистру, регистр в имени символа должен совпадать с регистром, используемым в определении в исходном коде.  
  
 Эта ошибка может возникать при попытке приведения переменной в целях ее отслеживания в ходе отладки.  `typedef` объявляет новое имя типа, однако не определяет новый тип.  При использовании приведения при отладке требуется имя определенного типа.  
  
 Эта ошибка идентична ошибке CAN0017.  
  
### Возможные способы устранения данной ошибки  
  
1.  Убедитесь, что символ уже объявлен в том месте программы, где он используется.  
  
2.  При приведении переменных в отладчике используйте действительное имя типа, а не имя, определенное с помощью `typedef`