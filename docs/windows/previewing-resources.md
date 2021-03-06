---
title: "Предварительный просмотр ресурсов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- resource previews
- code, viewing
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0eca56e607c916e28afc7bf513d853bcf6d94b81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="previewing-resources"></a>Предварительный просмотр ресурсов
Предварительный просмотр ресурсов позволяет просматривать графические ресурсы, не открывая их. Предварительный просмотр также полезна для исполняемых файлов после компиляции, так как идентификаторы ресурсов меняются на цифры. Поскольку эти числовые идентификаторы часто не предоставляет достаточно сведений, предварительный просмотр ресурсов помогает быстро определять их.  
  
 Можно просмотреть визуальное расположение ресурсы следующих типов:  
  
-   Bitmap  
  
-   Диалоговое окно  
  
-   Значок  
  
-   Меню  
  
-   Курсор  
  
-   Toolbar  
  
 Функцию предварительного просмотра не применяется к ресурсам сочетаний клавиш, манифест, таблица строк и сведения о версии.  
  
### <a name="to-preview-resources"></a>Предварительный просмотр ресурсов  
  
1.  В [представление ресурсов](../windows/resource-view-window.md) или в окне документа, выберите ресурс, например IDD_ABOUTBOX.  
  
     **Примечание** Если проект еще не содержит RC-файл, см. статью [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В [окно свойств](/visualstudio/ide/reference/properties-window), нажмите кнопку **страницы свойств** кнопки.  
  
     \- или -  
  
3.  На **представление** меню, нажмите кнопку **страницы свойств**.  
  
     При открытии страницы свойств, для ресурса отображение для предварительного просмотра этого ресурса. Можно использовать вверх и вниз со стрелками для перемещения в структуре дерева в представлении ресурсов или окно документа. На странице свойств останется открытым и Показать любой ресурс, который имеет фокус и возможность предварительного просмотра.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Как: открытие файла описания ресурсов за пределами проекта (автономный)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)

