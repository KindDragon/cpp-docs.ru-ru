---
title: "Обмен данными с полями записей: Использование RFX | Microsoft Docs"
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
  - "RFX (ODBC), реализация"
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Обмен данными с полями записей: Использование RFX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В данном разделе описано использование RFX в зависимости от потребностей среды.  
  
> [!NOTE]
>  Этот раздел относится к классам, производным от класса [CRecordset](../Topic/CRecordset%20Class.md), в котором групповая выборка строк не реализована.  При использовании групповой выборки строк реализуется групповой обмен данными с полями записей \(групповой RFX\).  Групповой RFX и обычный RFX похожи.  Описание различий см. в разделе [Набор записей: групповая выборка записей ODBC](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md).  
  
 Следующие разделы содержат связанные сведения:  
  
-   [Обмен данными с полями записей \(RFX\): работа с кодом мастера](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) содержит сведения об основных компонентах RFX и описывает код, создаваемый мастером приложения MFC и **Добавить класс** \(как описано в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\) для поддержки RFX и способы изменения кода мастера.  
  
-   [Обмен данными с полями записей: использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) описывает написание вызовов функций RFX в переопределении `DoFieldExchange`.  
  
 В следующей таблице показана роль разработчика и среды.  
  
### Использование RFX: разработчик и среда  
  
||.NET Framework|  
|-|--------------------|  
|Объявление классов набора записей в мастере.  Указание имени и типов данных в члене поля данных.|Мастер создает производный класс `CRecordset` и создает член функции [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) для переопределения разработчиком, включая вызов функции RFX для каждого члена поля данных.|  
|\(Дополнительно\) Добавление вручную требуемого члена\-параметра данных в класс.  Создание вручную вызова функции\-члена RFX `DoFieldExchange` для каждого члена\-параметра данных, добавление вызова [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md) для группировки параметров и указания общего числа параметров в член данных [m\_nParams](../Topic/CRecordset::m_nParams.md).  См. раздел [Набор записей: параметризация набора записей \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).||  
|\(Дополнительно\) Дополнительные столбцы вручную привязываются к членам полей данных.  Вручную увеличивается значение [m\_nFields](../Topic/CRecordset::m_nFields.md).  См. раздел [Набор записей: динамическая привязка столбцов данных \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||  
|Создание объекта класса набора записей.  Перед использованием объекта задает значения членов\-параметров данных.|Для повышения эффективности среда повторно связывает параметры с помощью ODBC.  Когда разработчик передает значения параметра, среда передает их в источник данных.  Если строки сортировки или строки фильтров не изменялись, то при повторном запросе отправляются только значения параметров.|  
|Открывает объект набора записей с помощью функции\-члена [CRecordset::Open](../Topic/CRecordset::Open.md).|Выполняет запрос набора записей, связывает столбцы с членами полей данных набора записей и вызывает функцию\-член `DoFieldExchange` для обмена данными между первой выбранной записью и членом полей данных набора записей.|  
|Прокручивает набор записей с помощью [CRecordset::Move](../Topic/CRecordset::Move.md) или команд меню или панели инструментов.|Вызывает `DoFieldExchange` для передачи данных члену поля данных от новой текущей записи.|  
|Добавление, обновление и удаление записей.|Вызывает функцию\-член `DoFieldExchange` для передачи данных источнику данных.|  
  
## См. также  
 [Обмен данными полями записей \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [Обмен данными с полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Набор записей. Определение сумм и других статистических результатов \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [CRecordset Class](../Topic/CRecordset%20Class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [Макросы, глобальные функции и глобальные переменные](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)