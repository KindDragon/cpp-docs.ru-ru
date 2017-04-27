---
title: "Элементы управления ActiveX в MFC. Добавление пользовательских свойств | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC ActiveX - элементы управления, свойства"
  - "свойства [MFC], пользовательский"
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Элементы управления ActiveX в MFC. Добавление пользовательских свойств
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Пользовательские свойства отличаются от стандартных свойств в том, что пользовательские свойства еще не реализуемые классом `COleControl`.  Пользовательское свойство используется для предоставления некоторые состояния или внешний вид элемента управления ActiveX программистам с помощью элемента управления.  
  
 В этом разделе описываются способы добавления пользовательского свойства в элемент управления ActiveX с помощью мастера добавления свойства и объясняет полученную изменения кода.  Ниже приведен список разделов.  
  
-   [С помощью мастера добавления свойства для добавления пользовательского свойства](#_core_using_classwizard_to_add_a_custom_property)  
  
-   [Добавьте мастера изменения свойства для пользовательских свойств](#_core_classwizard_changes_for_custom_properties)  
  
 Пользовательские свойства только в 4 возможности реализации: Переменную\-член, переменную\-член с уведомлением, получает или задает методы и параметризованные.  
  
-   Реализация переменной\-члена  
  
     Эта реализация представляет состояние свойства как переменную\-член в классе элемента управления.  Используйте реализацию переменной\-члена, когда не важно знать при изменении значения свойства.  3 Типов, эта реализация создает наименьшая объем кода поддержки для свойства.  Макрос записи схемы подготовки к отправке переменную\-член для реализации [DISP\_PROPERTY](../Topic/DISP_PROPERTY.md).  
  
-   Переменную\-член с реализацией уведомления  
  
     Эта реализация содержит переменную\-член и функции уведомления создаются с помощью мастера добавления свойства.  Функция уведомления автоматически вызывается платформой после значения свойств.  Используйте переменную\-член с реализацией уведомления при необходимости уведомления после значение свойства было изменено.  Эта реализация требует больше времени, поскольку она требует вызова функции.  Макрос записи схемы подготовки к отправке этой реализации [DISP\_PROPERTY\_NOTIFY](../Topic/DISP_PROPERTY_NOTIFY.md).  
  
-   Get\/set реализацию методов  
  
     Эта реализация состоит из пары функции\-члены класса элемента управления.  Реализация методов get " и set автоматически вызывает функцию\-член получение при первом запросе элемента управления текущее значение свойства и задать функцию\-член при первом запросе элемента управления, свойству изменилось.  Используйте это поведение, если необходимо вычислить значение свойства во время выполнения, чтобы проверить значение переданного пользователем элемента управления перед изменением фактическое свойство, или реализовать чтение или доступные только на запись тип свойства.  Макрос записи схемы подготовки к отправке этой реализации [DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md).  В следующем разделе, [С помощью мастера добавления свойства для добавления пользовательского свойства](#_core_using_classwizard_to_add_a_custom_property) использует пользовательское свойство CircleOffset для демонстрации это поведение.  
  
-   Реализация параметризованный  
  
     Параметризованный поддерживается реализацией мастера добавления свойства.  Параметризованное свойство \(иногда называемое массив свойств\) можно использовать для получения набора значений через отдельное свойство элемента управления.  Макрос записи схемы подготовки к отправке этой реализации `DISP_PROPERTY_PARAM`.  Дополнительные сведения о реализации этого типа см. в разделе [Реализация параметризованное свойство](../mfc/mfc-activex-controls-advanced-topics.md) в элементах управления ActiveX статьи: Дополнительные разделы.  
  
##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> С помощью мастера добавления свойства для добавления пользовательского свойства  
 В следующей процедуре показано добавление пользовательского свойства, CircleOffset, который использует реализацию методов get " и set.  Пользовательское свойство CircleOffset позволяет пользователю элемента управления для компенсации circle из центра ограничивающего прямоугольника элемента управления.  Процедуры для добавления пользовательских свойств с реализацией, кроме получает\/присваивается методы похожа.  
  
 Эту одной процедуры можно также использовать для добавления дополнительных пользовательских свойств требуется.  Замените имя пользовательского свойства для имени свойства и параметров CircleOffset.  
  
#### Добавление пользовательского свойства CircleOffset с помощью мастера добавления свойства.  
  
1.  Загрузите проект элемента управления.  
  
2.  В представлении классов разверните узел библиотеки элемента управления.  
  
3.  Щелкните правой кнопкой мыши узел интерфейса для элемента управления \(второго узла узла библиотеки\), чтобы открыть контекстное меню.  
  
4.  В контекстном меню щелкните **Добавить**, а затем щелкните **Добавить свойство**.  
  
     Это окно [Мастер добавления свойства](../ide/names-add-property-wizard.md).  
  
5.  В поле **Имя свойства** введите `CircleOffset`.  
  
6.  В поле **Тип реализации**, щелкните **Get\/set методы**.  
  
7.  В поле **свойство Type**, выберите **short**.  
  
8.  Введите уникальное имя для своего получение и установка функции или примите имя по умолчанию.  
  
9. Нажмите кнопку **Готово**.  
  
##  <a name="_core_classwizard_changes_for_custom_properties"></a> Добавьте мастера изменения свойства для пользовательских свойств  
 При добавлении пользовательского свойства, CircleOffset мастера добавления свойства вносит изменения в качестве заголовка \(. H\) и файлы реализации \(CPP\) класса элемента управления.  
  
 Следующие линии добавляются в. Файл H для объявления функции 2, `GetCircleOffset` и `SetCircleOffset`:  
  
 [!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_1.h)]  
  
 В следующей линия добавляется в файл .IDL элемента управления:  
  
 [!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_2.idl)]  
  
 Эта линия присвоить свойству CircleOffset определенный идентификатор, используемой в позиции метода в методах и списке свойств мастера добавления свойства.  
  
 Кроме того, следующая линия добавляется в схеме подготовки к отправке \(в cpp\-файле класса элемента управления\) для сопоставления свойства CircleOffset к функциям обработчика элемента управления 2:  
  
 [!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_3.cpp)]  
  
 Наконец, реализации `GetCircleOffset` и функции `SetCircleOffset` добавляются в конец файла .cpp элемента управления.  В большинстве случаев следует изменить функции получения для возврата значения свойства.  Указывает функция обычно содержит код, который должен быть выполнен этот до или после изменения свойств.  
  
 [!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_4.cpp)]  
  
 Обратите внимание, что мастера добавления свойства автоматически добавляет вызов, в [SetModifiedFlag](../Topic/COleControl::SetModifiedFlag.md), установленной в тело функции.  При вызове этого функцией помечается как измененный элемент управления.  Если элемент управления был изменен, то его новое состояние будет сохранено при сохранении контейнер.  Эта функция должна вызываться, когда свойство, сохраненное как часть состояния элемента управления постоянного, изменяет значение.  
  
## См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Элементы управления ActiveX в MFC. Свойства](../mfc/mfc-activex-controls-properties.md)   
 [Элементы управления ActiveX в MFC. Методы](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)