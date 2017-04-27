---
title: "Поддержка OLE. Реализация MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IMarshall"
  - "IMoniker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IMarshall - класс"
  - "IMoniker - интерфейс, MFC - библиотека"
  - "MFC - библиотеки, реализация"
  - "OLE IMarshal - интерфейс"
  - "OLE IMoniker - интерфейс"
  - "OLE IUnknown"
  - "реализация библиотеки OLE MFC"
  - "OLE, составные файлы"
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Поддержка OLE. Реализация MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Из\-за размера и сложности начального OLE, вызов API напрямую для создания приложений OLE может быть без очень много времени.  Цель реализации библиотеки Microsoft Foundation Class OLE снизить объем работы необходимо выполнить для создания полнофункциональных, OLE\-; приложения.  
  
 В этой статье описывается части OLE API, не реализован внутренний MFC.  Обсуждение также говорится, что они сопоставления OLE раздел [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> Части не OLE, предоставляемые библиотекой классов  
 Несколько интерфейсов и функций MFC OLE, непосредственно не предоставляются.  Если необходимо использовать эти функции можно вызывать API OLE напрямую.  
  
 Интерфейс IMoniker  
 Интерфейс `IMoniker` реализован библиотекой классов \(например, класс `COleServerItem` \), но еще не были предоставлены программисту.  Дополнительные сведения см. в разделе о этот интерфейс OLE реализации моникера OLE в разделе [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Однако см. также классы [CMonikerFile](../Topic/CMonikerFile%20Class.md) и [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
 IUnknown и интерфейсы IMarshal  
 Интерфейс **IUnknown** реализуется библиотекой классов, но не предоставляется программисту.  Интерфейс **IMarshal** не реализован библиотекой классов и используемый для внутреннего использования.  Серверы автоматизации, построенные с помощью библиотеки классов уже имеют встроенные возможности маршалинга.  
  
 Docfiles \(составные файлы\)  
 Составные файлы частично поддерживаются библиотекой классов.  Ни один из функций, которые напрямую управлять созданием составные файлы, поддерживаются.  MFC использует класс **COleFileStream** для поддержки обработку потоков с функциями стандартного файла.  Дополнительные сведения см. в статье [Контейнеры: Составные файлы](../mfc/containers-compound-files.md).  
  
 Внутрипроцессные серверов и обработчики объекта  
 Внутрипроцессные серверов и обработчики объекта позволяют реализация визуального редактирования полные данные или объекты \(COM\) COM в библиотеку динамической компоновки \(DLL\).  Для этого можно реализовать библиотеки DLL с помощью вызова OLE API напрямую.  Однако при создании сервера автоматизации и сервер не предусмотрен интерфейс пользователя, можно использовать AppWizard внести в сервером внутрипроцессный сервер и поместить его полностью в библиотеке DLL.  Дополнительные сведения о эти разделы см. в разделе [Серверы автоматизации](../mfc/automation-servers.md).  
  
> [!TIP]
>  Самый простой способ реализации сервер автоматизации разместить его в библиотеку DLL.  MFC поддерживает этот подход.  
  
 Дополнительные сведения об использовании класс OLE Microsoft Foundation реализации интерфейсов OLE технические заметки см. в разделах [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md) и [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md) библиотеки MFC.  
  
## См. также  
 [Поддержка OLE](../mfc/ole-background.md)   
 [Поддержка OLE. Стратегии реализации](../mfc/ole-background-implementation-strategies.md)