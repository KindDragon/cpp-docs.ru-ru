---
title: "Страница &quot;Строки шаблонов документов&quot;, мастер добавления классов MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.mfc.simple.doctemp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Мастер добавления класса MFC, строки элементов управления документов"
ms.assetid: 14e1c834-5e79-4dbd-811f-ec8f0a9cdcb2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Страница &quot;Строки шаблонов документов&quot;, мастер добавления классов MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Эта страница мастера доступна только для классов, отвечающих следующим критериям:  
  
-   Проект MFC поддерживает архитектуру документ\/представление.  
  
-   Базовым классом для нового класса является [CFormView](../../mfc/reference/cformview-class.md).  
  
-   Флажок **Генерировать ресурсы DocTemplate** установлен в разделе **Имена** [мастера классов MFC](../../mfc/reference/mfc-add-class-wizard.md).  
  
 Мастер задает по умолчанию следующие значения, помогающие при проектировании и локализации представлений форм, а также управлении ими.  Поскольку большая часть шаблонов строк документов видимы пользователям формы и используются ими, они переводятся на **язык ресурса**, заданный на странице [Типы приложений](../Topic/Application%20Type,%20MFC%20Application%20Wizard.md) мастера приложений MFC при создании проекта.  
  
> [!NOTE]
>  Мастер не обеспечивает автоматическую поддержку печати для классов, производных от `CFormView`.  
  
 Дополнительные сведения см. в разделе [Шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Нелокализованные строки  
 Этот раздел относится к приложениям, создающим пользовательские документы.  Пользователям будет легче открывать и сохранять документы, если типу документа сопоставлены расширение файла и идентификатор типа файла.  Эти элементы не локализуются, поскольку используются системой, а не пользователем.  
  
 **Расширение файла**  
 Задает расширение файла, связанное типом документа данного приложения Windows Forms.  По умолчанию за основу для расширения файла берется имя класса.  Например, если новый класс MFC называется **CWidget**, то по умолчанию файлам будет присваиваться расширение WID.  Расширение файла используется в файловых фильтрах и в диалоговых окнах **Открытие файла** и **Сохранение файла**.  
  
 Если изменить расширение файла, это изменение отразится в поле **Имя фильтра**.  
  
> [!NOTE]
>  При изменении заданного по умолчанию расширения файла не указывайте точку.  
  
 **ИД типа файла**  
 Задает метку для данного типа документа в реестре системы.  
  
## Локализованные строки  
 Создает строки, связанные с формами и документами, которые видны пользователям приложения и используются ими, и в этой связи локализуются.  
  
 **Имя типа документа**  
 Задает имя типа документа, по которому могут группироваться документы данного приложения.  По умолчанию за основу для него берется имя класса.  Например, если новый класс MFC называется **CWidget**, то по умолчанию имя типа документа будет Widget.  Изменение значения по умолчанию не меняет какие\-либо другие параметры в этом диалоговом окне.  
  
 **Имя фильтра**  
 Задает имя, которое пользователи смогут указывать для поиска файлов заданного типа  Этот параметр доступен в полях **Тип файла** и **Тип файлов** стандартных диалоговых окон Windows **Открыть** и **Сохранить как**.  По умолчанию это слово "файлы" и имя проекта, за которым следует расширение файла, указанное в поле **Расширение файла**.  Например, если проект называется Widget, а файлы имеют расширение WID, поле **Имя фильтра** будет по умолчанию содержать текст "Файлы Widget \(\*.wid\)".  
  
 **Короткое имя создаваемого файла**  
 Задает имя, отображаемое в стандартном диалоговом окне Windows `New`, если проект имеет более одного шаблона.  Если приложение является [сервером автоматизации](../../mfc/automation-servers.md), это имя используется в качестве краткого имени объекта автоматизации.  По умолчанию за основу для него берется имя класса.  
  
 **Длинное имя типа файла**  
 Задает имя типа файла в системном реестре.  Если приложение является сервером автоматизации, это имя используется в качестве длинного имени объекта автоматизации.  По умолчанию оно образуется из слова "Документ" и имени класса.  Например, для класса с именем **CWidget** поле **Длинное имя типа файла** будет содержать текст "Документ Widget".  
  
 **Класс документа**  
 Указывает класс документа проекта.  По умолчанию это основной класс документа приложения, указанный на странице [Обзор созданных классов](../../mfc/reference/generated-classes-mfc-application-wizard.md) мастера приложений MFC.  Можно выбрать из списка другой класс, если вы добавляли в проект другие классы документов.  
  
## См. также  
 [Мастер добавления классов MFC](../../mfc/reference/mfc-add-class-wizard.md)   
 [Класс MFC](../../mfc/reference/adding-an-mfc-class.md)   
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)