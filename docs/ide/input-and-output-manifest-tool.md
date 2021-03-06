---
title: "Манифест средства Свойства входов и выходов (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.DependencyInformationFile
- VC.Project.VCManifestTool.OutputResourceManifest
- VC.Project.VCManifestTool.GenerateCatalogFiles
dev_langs:
- C++
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 77137e9bc0a4af60080234aac85afa59034d2c6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Вход и выход, инструмент, свойства конфигурации манифеста &lt;Projectname&gt; диалоговое окно страниц свойств
Используйте это диалоговое окно предназначено для указания входных и выходных параметров [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Чтобы открыть это диалоговое окно страницы свойств, откройте страницы свойств для проекта или вкладку свойств. Разверните **инструмент манифеста** в узле **свойства конфигурации**, а затем выберите **входных и выходных**.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Дополнительные файлы манифеста**  
 Использует **/manifest** параметр, чтобы указать полные пути к дополнительным файлам манифеста, обрабатываемых инструмента манифеста или слияния. Полные пути разделяются точкой с запятой.  
  
 **Манифесты входных ресурсов**  
 Использует **/inputresource** параметр, чтобы указать полный путь ресурса типа RT_MANIFEST для входа в инструмент манифеста. Путь может следовать заданный идентификатор ресурса. Пример:  
  
 `dll_with_manifest.dll;#1`  
  
 Идентификатор ресурса является необязательным и по умолчанию обязательно в winuser.h.  
  
 **Внедрить манифест**  
 **Да** указывает, что система проектов встроит файл манифеста приложения в сборку.  
  
 **Не** указывает, что система проектов создаст файл манифеста приложения в виде отдельного файла.  
  
 **Выходной файл манифеста**  
 Задает имя выходного файла манифеста. Это свойство является необязательным, если инструментом манифеста работает только с одним файлом манифеста.  
  
 **Файл ресурсов манифеста**  
 Задает выходные файлы ресурсов, используемые для внедрения манифеста в выходные данные проекта.  
  
 **Создавать файлы каталогов**  
 Использует **/makecdfs** параметр, чтобы указать, что инструмент манифеста будет создавать файлы определений каталогов (CDF-файлы), которые используются для создания каталогов.  
  
 **Создать манифест из ManagedAssembly**  
 Создает манифест из управляемой сборки. (**- managedassemblyname:***файл*).  
  
 **Отключение элемента зависимости**  
 При использовании **- managedassembly** параметр. Этот тег отменяет создание элементов зависимости в итоговом манифесте.  
  
 **Создание тегов категории**  
 При использовании **- managedassembly** параметр. Этот тег вызывает создаваться тегов категорий.  
  
 **Включить осведомленности точек на ДЮЙМ**  
 Указывает, является ли приложение как поддерживающее DPI. По умолчанию значение — **Да** для проектов MFC и **нет** в противном случае, поскольку только проекты MFC строятся с поддержкой точек на ДЮЙМ. Можно переопределить параметр **Да** при добавлении кода к различным Разрешением экрана. Приложение может отображаться нечеткое или небольшой, если установить его как поддерживающее DPI, если она не.  
  
## <a name="see-also"></a>См. также  
 [Манифест приложения ClickOnce](/visualstudio/deployment/clickonce-application-manifest)   
 [Страницы свойств средства манифестов](../ide/manifest-tool-property-pages.md)   
 [Работа со свойствами проектов](../ide/working-with-project-properties.md)   