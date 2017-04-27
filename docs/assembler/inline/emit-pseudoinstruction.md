---
title: "Псевдоинструкция _emit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_emit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_emit - псевдоконструкция"
  - "определение байта (встроенная сборка)"
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Псевдоинструкция _emit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Майкрософт  
 Псевдокоманда **\_emit** задает один байт в текущем положении в текущем сегменте текста.  Псевдокоманда **\_emit** отчасти похожа на директиву [DB](../../assembler/masm/db.md) в MASM.  
  
 В следующем примере в код помещаются байты 0x4A, 0x43 и 0x4B:  
  
```  
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B  
 .  
 .  
 .  
__asm {  
     randasm  
     }  
```  
  
> [!CAUTION]
>  Если псевдокоманда `_emit` создает инструкции, которые изменяют регистры, а приложение компилируется с включенными оптимизациями, то компилятор не в состоянии определить, на какие регистры она действует.  Например, если псевдокоманда `_emit` создает инструкцию, которая меняет регистр **rax**, то компилятору не будет известно, что регистр **rax** был изменен.  Затем компилятор может сделать неверное допущение о значении этого регистра после выполнения встроенного кода на языке ассемблера.  Поэтому запущенное приложение может работать непредсказуемым образом.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## См. также  
 [Использование языка ассемблера в блоках \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)