---
title: "Развертывание приложения Visual C++ с помощью проекта установки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fbe75f1fd3ceb037e44716156556882f3f6d1cc1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>Пошаговое руководство. Развертывание приложения Visual C++ с помощью проекта установки
В этой статье описывается использование проекта установки для развертывания приложения Visual C++.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   Компьютер с [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] установлен.  
  
-   Дополнительный компьютер, у которого нет библиотеки Visual C++.  
  
### <a name="to-deploy-an-application-by-using-a-setup-project"></a>Чтобы развернуть приложение с помощью проекта установки  
  
1.  Используйте **MFC ApplicationWizard** для создания нового решения Visual Studio. Чтобы открыть мастер, с **новый проект** диалогового окна разверните **Visual C++** выберите **MFC**выберите **приложение MFC**, введите имя для проекта и нажмите кнопку **ОК**.  
  
2.  Изменение конфигурации активного решения для **выпуска**. Из **построения** последовательно выберите пункты **диспетчер конфигурации**. Из **Configuration Manager** выберите **выпуска** из **активная конфигурация решения** раскрывающегося списка.  
  
3.  Нажмите клавишу F7 для построения приложения. Либо выберите **построения** меню, нажмите кнопку **построить решение**. Это позволяет проект установки сможет использовать выходные данные проекта приложения MFC.  
  
4.  Если это еще не сделано, загрузите InstallShield Limited Edition (ISLE), который предоставляется бесплатно для разработчиков Visual Studio и заменяет функциональность шаблонов проектов в Visual Studio для установки и развертывания. При подключении к Интернету откройте **новый проект** диалоговое окно, выбрав **файл**, **New**, **проекта** на из строки меню, или по Щелкните правой кнопкой мыши решение в **обозревателе решений** и выбрав **добавить**, **новый проект**. Разверните **другие типы проектов** узел, выберите **Включение InstallShield Limited Edition** в **Установка и развертывание** узел и следуйте инструкциям на экране. После загрузки, установки и активации InstallShield Limited Edition, закройте Visual Studio и снова открыть его.  
  
5.  Откройте **новый проект** диалоговое окно еще раз, разверните **другие типы проектов** узел и выберите **проект InstallShield Limited Edition** в  **InstallShield Limited Edition** узла.  
  
6.  Следуйте инструкциям в разделе **Приступая к работе** узел проекта установки, созданным с помощью шаблона InstallShield Limited Edition для добавления ссылки на выходные данные в проект Visual Studio MFC.  
  
7.  Сборка проекта установки для создания файла установщика (setup.exe). Чтобы сделать это, щелкните правой кнопкой мыши узел проекта установки в **обозревателе решений** и выберите **сборки**.  
  
     InstallShield Limited Edition создает файл программы установки в дереве проекта установки (по умолчанию, он может находиться в подпапке Express\SingleImage\DiskImages\DISK1 проекта установки).  
  
8.  Запустите программу установки на втором компьютере, не установлены библиотеки Visual C++.  
  
## <a name="see-also"></a>См. также  
 [Примеры развертывания](../ide/deployment-examples.md)