---
title: "Предупреждение компилятора предупреждение (уровень 1) C4678 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4678
dev_langs:
- C++
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7648101a0862aa2006feff73a5ebe32bd0f424a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4678"></a>Предупреждение компилятора (уровень 1) C4678
базовый класс "базовый_тип" менее доступен, чем "производный_тип"  
  
Открытый тип является производным от закрытого типа. Если экземпляр открытого типа создается в связанной сборке, то члены закрытого базового типа будут недоступны.  
  
Предупреждение C4678 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**. Считается ошибкой при использовании **/CLR**наличие базового класса, менее доступного, производный от него класс.  
