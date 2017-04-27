---
title: "/DEBUGTYPE (параметры отладочных сведений) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/debugtype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Параметр компоновщика /DEBUGTYPE"
  - "Параметр компоновщика DEBUGTYPE"
  - "Параметр компоновщика -DEBUGTYPE"
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# /DEBUGTYPE (параметры отладочных сведений)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметр \/DEBUGTYPE указывает типы отладочной информации, создаваемой при использовании параметра \/Debug.  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## Аргументы  
 CV  
 Указывает компоновщику выводить отладочную информацию для символов, номеров строк и другие сведения о компиляции объектов в PDB\-файл.  По умолчанию этот параметр включен, если **\/DEBUG** указан, а **\/DEBUGTYPE** – нет.  
  
 PDATA  
 Указывает компоновщику добавить записи PDATA и XDATA в поток отладочной информации в PDB\-файле.  По умолчанию этот параметр включен, когда указан как параметр **\/DEBUG**, так и параметр **\/DRIVER**.  Если **\/DEBUGTYPE:PDATA** указан сам по себе, компоновщик автоматически включает символы отладки в PDB\-файл.  Если указан **\/DEBUGTYPE:PDATA,FIXUP**, компоновщик не включает символы отладки в PDB\-файл.  
  
 FIXUP  
 Указывает компоновщику добавить записи таблицы перемещений в поток отладочной информации в PDB\-файле.  По умолчанию этот параметр включен, когда указан как параметр **\/DEBUG**, так и параметр **\/PROFILE**.  Если указан **\/DEBUGTYPE:FIXUP** или **\/DEBUGTYPE:FIXUP,PDATA**, компоновщик не включает символы отладки в PDB\-файл.  
  
 Аргументы для **\/DEBUGTYPE** можно объединять в любом порядке, разделив их запятой.  Параметр **\/DEBUGTYPE** и его аргументы задаются без учета регистра.  
  
## Заметки  
 Используйте параметр **\/DEBUGTYPE**, чтобы указать включение данных таблицы перемещений или сведения о заголовках PDATA и XDATA в потоке отладки.  В этом случае компоновщик включает сведения о коде пользовательского режима, который видим в отладчике ядра при остановке в коде режима ядра.  Чтобы сделать символы отладки доступными при указанном **FIXUP**, включите аргумент **CV**.  
  
 Для отладки кода в пользовательском режиме, который является типичным для приложений, параметр **\/DEBUGTYPE** не требуется.  По умолчанию выходные параметры компилятора, задающие выходные данные отладки \([\/Z7, \/ Zi, \/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)\) выводят все сведения, необходимые отладчику Visual Studio.  Используйте **\/DEBUGTYPE:PDATA** или **\/DEBUGTYPE:CV,PDATA,FIXUP** для отладки кода, который сочетает в себе компоненты пользовательского режима и режима ядра, например приложения настройки для драйвера устройства.  Дополнительные сведения об отладчиках режима ядра см. в разделе [Средства отладки для Windows \(WinDbg, KD, CDB, NTSD\)](http://go.microsoft.com/fwlink/p?LinkID=285651)  
  
## См. также  
 [\/DEBUG \(создать отладочную информацию\)](../../build/reference/debug-generate-debug-info.md)   
 [\/DRIVER \(драйвер режима ядра Windows NT\)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [\/PROFILE \(профилировщик средств обеспечения производительности\)](../../build/reference/profile-performance-tools-profiler.md)   
 [Средства отладки для Windows \(WinDbg, KD, CDB, NTSD\)](http://go.microsoft.com/fwlink/p?LinkID=285651)