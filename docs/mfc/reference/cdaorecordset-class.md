---
title: "CDaoRecordset-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoRecordset
- AFXDAO/CDaoRecordset
- AFXDAO/CDaoRecordset::CDaoRecordset
- AFXDAO/CDaoRecordset::AddNew
- AFXDAO/CDaoRecordset::CanAppend
- AFXDAO/CDaoRecordset::CanBookmark
- AFXDAO/CDaoRecordset::CancelUpdate
- AFXDAO/CDaoRecordset::CanRestart
- AFXDAO/CDaoRecordset::CanScroll
- AFXDAO/CDaoRecordset::CanTransact
- AFXDAO/CDaoRecordset::CanUpdate
- AFXDAO/CDaoRecordset::Close
- AFXDAO/CDaoRecordset::Delete
- AFXDAO/CDaoRecordset::DoFieldExchange
- AFXDAO/CDaoRecordset::Edit
- AFXDAO/CDaoRecordset::FillCache
- AFXDAO/CDaoRecordset::Find
- AFXDAO/CDaoRecordset::FindFirst
- AFXDAO/CDaoRecordset::FindLast
- AFXDAO/CDaoRecordset::FindNext
- AFXDAO/CDaoRecordset::FindPrev
- AFXDAO/CDaoRecordset::GetAbsolutePosition
- AFXDAO/CDaoRecordset::GetBookmark
- AFXDAO/CDaoRecordset::GetCacheSize
- AFXDAO/CDaoRecordset::GetCacheStart
- AFXDAO/CDaoRecordset::GetCurrentIndex
- AFXDAO/CDaoRecordset::GetDateCreated
- AFXDAO/CDaoRecordset::GetDateLastUpdated
- AFXDAO/CDaoRecordset::GetDefaultDBName
- AFXDAO/CDaoRecordset::GetDefaultSQL
- AFXDAO/CDaoRecordset::GetEditMode
- AFXDAO/CDaoRecordset::GetFieldCount
- AFXDAO/CDaoRecordset::GetFieldInfo
- AFXDAO/CDaoRecordset::GetFieldValue
- AFXDAO/CDaoRecordset::GetIndexCount
- AFXDAO/CDaoRecordset::GetIndexInfo
- AFXDAO/CDaoRecordset::GetLastModifiedBookmark
- AFXDAO/CDaoRecordset::GetLockingMode
- AFXDAO/CDaoRecordset::GetName
- AFXDAO/CDaoRecordset::GetParamValue
- AFXDAO/CDaoRecordset::GetPercentPosition
- AFXDAO/CDaoRecordset::GetRecordCount
- AFXDAO/CDaoRecordset::GetSQL
- AFXDAO/CDaoRecordset::GetType
- AFXDAO/CDaoRecordset::GetValidationRule
- AFXDAO/CDaoRecordset::GetValidationText
- AFXDAO/CDaoRecordset::IsBOF
- AFXDAO/CDaoRecordset::IsDeleted
- AFXDAO/CDaoRecordset::IsEOF
- AFXDAO/CDaoRecordset::IsFieldDirty
- AFXDAO/CDaoRecordset::IsFieldNull
- AFXDAO/CDaoRecordset::IsFieldNullable
- AFXDAO/CDaoRecordset::IsOpen
- AFXDAO/CDaoRecordset::Move
- AFXDAO/CDaoRecordset::MoveFirst
- AFXDAO/CDaoRecordset::MoveLast
- AFXDAO/CDaoRecordset::MoveNext
- AFXDAO/CDaoRecordset::MovePrev
- AFXDAO/CDaoRecordset::Open
- AFXDAO/CDaoRecordset::Requery
- AFXDAO/CDaoRecordset::Seek
- AFXDAO/CDaoRecordset::SetAbsolutePosition
- AFXDAO/CDaoRecordset::SetBookmark
- AFXDAO/CDaoRecordset::SetCacheSize
- AFXDAO/CDaoRecordset::SetCacheStart
- AFXDAO/CDaoRecordset::SetCurrentIndex
- AFXDAO/CDaoRecordset::SetFieldDirty
- AFXDAO/CDaoRecordset::SetFieldNull
- AFXDAO/CDaoRecordset::SetFieldValue
- AFXDAO/CDaoRecordset::SetFieldValueNull
- AFXDAO/CDaoRecordset::SetLockingMode
- AFXDAO/CDaoRecordset::SetParamValue
- AFXDAO/CDaoRecordset::SetParamValueNull
- AFXDAO/CDaoRecordset::SetPercentPosition
- AFXDAO/CDaoRecordset::Update
- AFXDAO/CDaoRecordset::m_bCheckCacheForDirtyFields
- AFXDAO/CDaoRecordset::m_nFields
- AFXDAO/CDaoRecordset::m_nParams
- AFXDAO/CDaoRecordset::m_pDAORecordset
- AFXDAO/CDaoRecordset::m_pDatabase
- AFXDAO/CDaoRecordset::m_strFilter
- AFXDAO/CDaoRecordset::m_strSort
dev_langs:
- C++
helpviewer_keywords:
- CDaoRecordset [MFC], CDaoRecordset
- CDaoRecordset [MFC], AddNew
- CDaoRecordset [MFC], CanAppend
- CDaoRecordset [MFC], CanBookmark
- CDaoRecordset [MFC], CancelUpdate
- CDaoRecordset [MFC], CanRestart
- CDaoRecordset [MFC], CanScroll
- CDaoRecordset [MFC], CanTransact
- CDaoRecordset [MFC], CanUpdate
- CDaoRecordset [MFC], Close
- CDaoRecordset [MFC], Delete
- CDaoRecordset [MFC], DoFieldExchange
- CDaoRecordset [MFC], Edit
- CDaoRecordset [MFC], FillCache
- CDaoRecordset [MFC], Find
- CDaoRecordset [MFC], FindFirst
- CDaoRecordset [MFC], FindLast
- CDaoRecordset [MFC], FindNext
- CDaoRecordset [MFC], FindPrev
- CDaoRecordset [MFC], GetAbsolutePosition
- CDaoRecordset [MFC], GetBookmark
- CDaoRecordset [MFC], GetCacheSize
- CDaoRecordset [MFC], GetCacheStart
- CDaoRecordset [MFC], GetCurrentIndex
- CDaoRecordset [MFC], GetDateCreated
- CDaoRecordset [MFC], GetDateLastUpdated
- CDaoRecordset [MFC], GetDefaultDBName
- CDaoRecordset [MFC], GetDefaultSQL
- CDaoRecordset [MFC], GetEditMode
- CDaoRecordset [MFC], GetFieldCount
- CDaoRecordset [MFC], GetFieldInfo
- CDaoRecordset [MFC], GetFieldValue
- CDaoRecordset [MFC], GetIndexCount
- CDaoRecordset [MFC], GetIndexInfo
- CDaoRecordset [MFC], GetLastModifiedBookmark
- CDaoRecordset [MFC], GetLockingMode
- CDaoRecordset [MFC], GetName
- CDaoRecordset [MFC], GetParamValue
- CDaoRecordset [MFC], GetPercentPosition
- CDaoRecordset [MFC], GetRecordCount
- CDaoRecordset [MFC], GetSQL
- CDaoRecordset [MFC], GetType
- CDaoRecordset [MFC], GetValidationRule
- CDaoRecordset [MFC], GetValidationText
- CDaoRecordset [MFC], IsBOF
- CDaoRecordset [MFC], IsDeleted
- CDaoRecordset [MFC], IsEOF
- CDaoRecordset [MFC], IsFieldDirty
- CDaoRecordset [MFC], IsFieldNull
- CDaoRecordset [MFC], IsFieldNullable
- CDaoRecordset [MFC], IsOpen
- CDaoRecordset [MFC], Move
- CDaoRecordset [MFC], MoveFirst
- CDaoRecordset [MFC], MoveLast
- CDaoRecordset [MFC], MoveNext
- CDaoRecordset [MFC], MovePrev
- CDaoRecordset [MFC], Open
- CDaoRecordset [MFC], Requery
- CDaoRecordset [MFC], Seek
- CDaoRecordset [MFC], SetAbsolutePosition
- CDaoRecordset [MFC], SetBookmark
- CDaoRecordset [MFC], SetCacheSize
- CDaoRecordset [MFC], SetCacheStart
- CDaoRecordset [MFC], SetCurrentIndex
- CDaoRecordset [MFC], SetFieldDirty
- CDaoRecordset [MFC], SetFieldNull
- CDaoRecordset [MFC], SetFieldValue
- CDaoRecordset [MFC], SetFieldValueNull
- CDaoRecordset [MFC], SetLockingMode
- CDaoRecordset [MFC], SetParamValue
- CDaoRecordset [MFC], SetParamValueNull
- CDaoRecordset [MFC], SetPercentPosition
- CDaoRecordset [MFC], Update
- CDaoRecordset [MFC], m_bCheckCacheForDirtyFields
- CDaoRecordset [MFC], m_nFields
- CDaoRecordset [MFC], m_nParams
- CDaoRecordset [MFC], m_pDAORecordset
- CDaoRecordset [MFC], m_pDatabase
- CDaoRecordset [MFC], m_strFilter
- CDaoRecordset [MFC], m_strSort
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e50e83a2d52567d30901cea33cfccec3e236fe67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdaorecordset-class"></a>CDaoRecordset-класс
Представляет набор записей, выбранных из источника данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDaoRecordset : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|Создает объект `CDaoRecordset`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoRecordset::AddNew](#addnew)|Подготавливает для добавления новой записи. Вызовите [обновление](#update) для завершения добавления.|  
|[CDaoRecordset::CanAppend](#canappend)|Возвращает ненулевое значение, если новые записи могут быть добавлены в набор записей через [AddNew](#addnew) функции-члена.|  
|[CDaoRecordset::CanBookmark](#canbookmark)|Возвращает ненулевое значение, если набор записей поддерживает закладки.|  
|[CDaoRecordset::CancelUpdate](#cancelupdate)|Отменяет все имеющиеся обновления из-за [изменить](#edit) или [AddNew](#addnew) операции.|  
|[CDaoRecordset::CanRestart](#canrestart)|Возвращает ненулевое значение, если [Requery](#requery) может вызываться для выполнения запроса набора записей еще раз.|  
|[CDaoRecordset::CanScroll](#canscroll)|Возвращает ненулевое значение, если можно прокручивать записи.|  
|[CDaoRecordset::CanTransact](#cantransact)|Возвращает ненулевое значение, если источник данных поддерживает транзакции.|  
|[CDaoRecordset::CanUpdate](#canupdate)|Возвращает ненулевое значение, если можно обновить набор записей (можно добавить, обновить или удалить записи).|  
|[CDaoRecordset::Close](#close)|Закрытие набора записей.|  
|[CDaoRecordset::Delete](#delete)|Удаляет текущую запись из набора записей. Явным образом, необходимо перейти к другой записи после удаления.|  
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|Вызывается для обмена данными (в обоих направлениях) между элементами данных полей набора записей и соответствующая запись в источнике данных. Реализует DAO обмен полями записей (DFX).|  
|[CDaoRecordset::Edit](#edit)|Подготавливает для изменения текущей записи. Вызовите **обновление** для завершения редактирования.|  
|[CDaoRecordset::FillCache](#fillcache)|Заполняет все или часть локального кэша для объекта набора записей, содержащий данные из источника данных ODBC.|  
|[CDaoRecordset::Find](#find)|Находит первый, следующего предыдущей, или последний расположения определенной строки в наборе записей динамического типа, удовлетворяющей указанным критериям и делает, записывающие текущей записи.|  
|[CDaoRecordset::FindFirst](#findfirst)|Находит первой записи в наборе или записей статического типа, который удовлетворяет указанным критериям и делает этот запись текущей записи.|  
|[CDaoRecordset::FindLast](#findlast)|Находит последнюю запись типа динамического или набора записей типа моментального снимка, удовлетворяющей указанным критериям и делает, записывающие текущей записи.|  
|[CDaoRecordset::FindNext](#findnext)|Находит следующей записи в наборе или записей статического типа, который удовлетворяет указанным критериям и делает этот запись текущей записи.|  
|[CDaoRecordset::FindPrev](#findprev)|Находит предыдущей записи типа динамического или набора записей типа моментального снимка, удовлетворяющей указанным критериям и делает, записывающие текущей записи.|  
|[CDaoRecordset::GetAbsolutePosition](#getabsoluteposition)|Возвращает номер текущей записи объекта набора записей.|  
|[CDaoRecordset::GetBookmark](#getbookmark)|Возвращает значение, представляющее закладку на запись.|  
|[CDaoRecordset::GetCacheSize](#getcachesize)|Возвращает значение, указывающее количество записей в наборе записей, с данными, кэшироваться локально из источника данных ODBC.|  
|[CDaoRecordset::GetCacheStart](#getcachestart)|Возвращает значение, указывающее закладки первой записи в наборе записей для кэширования.|  
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|Возвращает `CString` содержит имя индекса наиболее недавно использовать индексированные табличному типу `CDaoRecordset`.|  
|[CDaoRecordset::GetDateCreated](#getdatecreated)|Возвращает дату и время в базовой таблице базовый `CDaoRecordset` был создан объект|  
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату и время последнего изменения в структуре базовой таблицы, расположенных `CDaoRecordset` объекта.|  
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|Возвращает имя источника данных по умолчанию.|  
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|Вызывается для получения строки SQL по умолчанию для выполнения.|  
|[CDaoRecordset::GetEditMode](#geteditmode)|Возвращает значение, указывающее состояние редактирования для текущей записи.|  
|[CDaoRecordset::GetFieldCount](#getfieldcount)|Возвращает значение, представляющее число полей в наборе записей.|  
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|Возвращает определенные виды информации о поля в наборе записей.|  
|[CDaoRecordset::GetFieldValue](#getfieldvalue)|Возвращает значение поля в наборе записей.|  
|[CDaoRecordset::GetIndexCount](#getindexcount)|Возвращает число индексов в таблице базовый набор записей.|  
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|Возвращает различные сведения об индексе.|  
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|Используется для определения наиболее недавно добавленные или обновленные записи.|  
|[CDaoRecordset::GetLockingMode](#getlockingmode)|Возвращает значение, указывающее тип блокировки, которая действует во время редактирования.|  
|[CDaoRecordset::GetName](#getname)|Возвращает `CString` содержащее имя набора записей.|  
|[CDaoRecordset::GetParamValue](#getparamvalue)|Извлекает текущее значение указанного параметра, сохраненного в базовый объект DAOParameter.|  
|[CDaoRecordset::GetPercentPosition](#getpercentposition)|Возвращает позицию текущей записи в процентах от общего количества записей.|  
|[CDaoRecordset::GetRecordCount](#getrecordcount)|Возвращает число записей в объекте recordset.|  
|[CDaoRecordset::GetSQL](#getsql)|Возвращает строку SQL, используемую для выбора записей для набора записей.|  
|[CDaoRecordset::GetType](#gettype)|Вызывается для определения типа набор записей: тип таблицы, добавляющий или статического типа.|  
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|Возвращает `CString` содержащий значение, которое проверяет данные, вводимые в поле.|  
|[CDaoRecordset::GetValidationText](#getvalidationtext)|Получает текст, отображаемый, когда правило проверки не выполняется.|  
|[CDaoRecordset::IsBOF](#isbof)|Возвращает ненулевое значение, если набор записей был позиционирован перед первой записи. Отсутствует текущая запись.|  
|[CDaoRecordset::IsDeleted](#isdeleted)|Возвращает ненулевое значение, если набор записей располагается на удаленную запись.|  
|[CDaoRecordset::IsEOF](#iseof)|Возвращает ненулевое значение, если набор записей был помещен после последней записи. Отсутствует текущая запись.|  
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|Возвращает ненулевое значение, если указанное поле в текущей записи был изменен.|  
|[CDaoRecordset::IsFieldNull](#isfieldnull)|Возвращает ненулевое значение, если указанное поле в текущей записи имеет значение Null, (имеющая значение отсутствует).|  
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|Возвращает ненулевое значение, если указанное поле в текущей записи может иметь значение Null (значение не имеющая).|  
|[CDaoRecordset::IsOpen](#isopen)|Возвращает ненулевое значение, если [откройте](#open) был вызван ранее.|  
|[CDaoRecordset::Move](#move)|Устанавливает набор записей с заданным числом записей в текущей записи в любом направлении.|  
|[CDaoRecordset::MoveFirst](#movefirst)|Помещает текущей записи на первой записи в наборе записей.|  
|[CDaoRecordset::MoveLast](#movelast)|Помещает текущей записи на последней записи в наборе записей.|  
|[CDaoRecordset::MoveNext](#movenext)|Помещает текущей записи к следующей записи в наборе записей.|  
|[CDaoRecordset::MovePrev](#moveprev)|Помещает текущей записи на предыдущие записи в наборе записей.|  
|[CDaoRecordset::Open](#open)|Создает новый набор записей из таблицы, динамический или статический.|  
|[CDaoRecordset::Requery](#requery)|Выполнение запроса набора записей еще раз, чтобы обновить выбранные записи.|  
|[CDaoRecordset::Seek](#seek)|Поиск записи в объект recordset индексированных тип таблицы, удовлетворяющий указанному условию для текущего индекса и делает этот запись текущей записи.|  
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|Задает номер текущей записи объекта набора записей.|  
|[CDaoRecordset::SetBookmark](#setbookmark)|Устанавливает набор записей на запись, содержащую указанную закладку.|  
|[CDaoRecordset::SetCacheSize](#setcachesize)|Задает значение, указывающее количество записей в наборе записей, с данными, кэшироваться локально из источника данных ODBC.|  
|[CDaoRecordset::SetCacheStart](#setcachestart)|Задает значение, указывающее закладки первой записи в наборе записей для кэширования.|  
|[CDaoRecordset::SetCurrentIndex](#setcurrentindex)|Вызывается для задания индекса на набор записей типа таблицы.|  
|[CDaoRecordset::SetFieldDirty](#setfielddirty)|Помечает указанного поля текущей записи, как измененный.|  
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Задает значение указанного поля текущей записи в значение Null (значение не имеющая).|  
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|Задает значение поля в наборе записей.|  
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Задает значение поля в наборе записей, значение Null. (имеющая значение отсутствует).|  
|[CDaoRecordset::SetLockingMode](#setlockingmode)|Задает значение, указывающее тип блокировки, чтобы вступили в силу во время редактирования.|  
|[CDaoRecordset::SetParamValue](#setparamvalue)|Задает текущее значение указанного параметра, сохраненного в базовый объект DAOParameter|  
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|Задает текущее значение указанного параметра в значение Null (значение не имеющая).|  
|[CDaoRecordset::SetPercentPosition](#setpercentposition)|Задает позицию текущей записи в расположении, соответствующий процент от общего количества записей в наборе записей.|  
|[CDaoRecordset::Update](#update)|Завершает `AddNew` или **изменить** операции путем сохранения новых или измененных данных в источнике данных.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoRecordset::m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|Содержит флаг, указывающий ли поля автоматически помечаются как измененный.|  
|[CDaoRecordset::m_nFields](#m_nfields)|Содержит число элементов данных полей в классе записей и число столбцов, выбранных в наборе записей из источника данных.|  
|[CDaoRecordset::m_nParams](#m_nparams)|Содержит количество элементов данных параметров в классе записей — количество параметров, переданных с запросом набора записей|  
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|Указатель на интерфейс DAO основного объекта набора записей.|  
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|База данных-источник для этого результирующего набора. Содержит указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.|  
|[CDaoRecordset::m_strFilter](#m_strfilter)|Содержит строку, используемую для создания SQL **ГДЕ** инструкции.|  
|[CDaoRecordset::m_strSort](#m_strsort)|Содержит строку, используемую для создания SQL **ORDER BY** инструкции.|  
  
## <a name="remarks"></a>Примечания  
 Известный как «наборы данных», `CDaoRecordset` объекты доступны в трех следующих форм:  
  
-   Наборы записей табличный тип представления базовой таблицы, можно использовать для проверки, добавить, изменить или удалить записи из одной таблицы базы данных.  
  
-   Наборы записей динамического типа являются результатом запроса, который может иметь обновляемых записей. Эти наборы данных являются набора записей, которые можно использовать для проверки, добавить, изменить или удаления записей в базовой таблице или таблицах. Наборы записей динамического типа может содержать поля из одного или нескольких таблиц в базе данных.  
  
-   Записей типа снимка — это Статическая копия набора записей, которые можно использовать для поиска данных или создавать отчеты. Эти наборы записей может содержать поля из одной или нескольких таблиц в базе данных, но не может быть обновлен.  
  
 Каждая форма набора записей представляет набор записей, во время открытия набора записей фиксированным. При переходе к записи в набор записей типа таблицы или набора записей типа динамического влияют изменения, внесенные в запись после открытия набора записей другими пользователями или других наборов записей в приложении. (Не удается обновить набор записей типа моментальных снимков.) Можно использовать `CDaoRecordset` напрямую или являются производными класса набора записей для конкретного приложения из `CDaoRecordset`. После этого можно:  
  
-   Прокручивать записи.  
  
-   Значение индекса и быстро искать записи с помощью [Seek](#seek) (только для табличного типа записей).  
  
-   Найти записи на основании сравнения строк: «< «,»\<=», «=», «> =», или «>» (добавляющий и записей типа снимка).  
  
-   Обновить записи и укажите режим блокировки (за исключением записей типа снимка).  
  
-   Фильтрация набора записей, чтобы ограничить записи, которые он выбирает из доступных в источнике данных.  
  
-   Выполните сортировку набора записей.  
  
-   Параметризация набора записей можно изменить выбранный для него, сведения, которые неизвестны до времени выполнения.  
  
 Класс `CDaoRecordset` предоставляет интерфейс аналогично класс `CRecordset`. Основное отличие заключается в этом классе `CDaoRecordset` обращается к данным посредством доступа к данным объекта (DAO) основании OLE. Класс `CRecordset` обращается к СУБД через Open Database Connectivity (ODBC) и драйвер ODBC для этого СУБД.  
  
> [!NOTE]
>  Классы баз данных DAO отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему доступ к источникам данных ODBC с помощью классов DAO. классы DAO обычно обеспечивают превосходную возможности, так как они характерны для базы данных Microsoft Jet.  
  
 Можно использовать либо `CDaoRecordset` напрямую или являются производными от класса `CDaoRecordset`. Чтобы использовать класс записей в любом случае, открыть базу данных и создайте объект набора записей, передав конструктору указатель на `CDaoDatabase` объект. Можно также создать `CDaoRecordset` объекта и позволить создать временную MFC `CDaoDatabase` объект. Затем вызовите набора записей [откройте](#open) функция-член, указывающее, является ли объект recordset табличного типа, набор записей типа динамического или набора записей типа снимка. Вызов **откройте** выбирает данные из базы данных и извлекает первую запись.  
  
 Член объекта функции и данные элементы используются для прокручивать записи и работать с ними. Доступные операции зависят от того, является ли объект recordset табличного типа, набор записей типа динамического или набора записей типа и обновляемые или только для чтения — это зависит от возможностей базы данных или Open Database Connectivity (ODBC) источник данных. Для обновления записей, которые могут были изменены или добавлены с момента **откройте** call, вызывающие этот объект [Requery](#requery) функции-члена. Вызвать объект **закрыть** члена функции и уничтожить объект после завершения работы с его.  
  
 `CDaoRecordset`использует обмен полями записей DAO (DFX) для поддержки чтение и обновление полей записей через строго типизированные члены C++ вашей `CDaoRecordset` или `CDaoRecordset`-производного класса. Вы также можете реализовать динамическая привязка столбцов в базе данных без использования механизма DFX с помощью [GetFieldValue](#getfieldvalue) и [SetFieldValue](#setfieldvalue).  
  
 Дополнительные сведения см. в разделе «Набор записей объект» в справке DAO.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoRecordset`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
##  <a name="addnew"></a>CDaoRecordset::AddNew  
 Вызовите эту функцию-член для добавления новой записи в набор записей типа таблицы или динамического типа.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Примечания  
 Поля записи изначально пусты. (В терминологии связанных баз данных, Null означает «предложений having значение отсутствует», а не является таким же, как **NULL** в C++.) Чтобы завершить операцию, необходимо вызвать [обновление](#update) функции-члена. **Обновление** сохраняет изменения в источнике данных.  
  
> [!CAUTION]
>  Если изменить запись, а затем перейдите к другой записи без вызова **обновление**, изменения будут утеряны без предупреждения.  
  
 При добавлении записи в наборе записей динамического типа путем вызова [AddNew](#addnew), запись является видимым в наборе записей и включается в базовой таблице, где он становится видимым для любого нового `CDaoRecordset` объектов.  
  
 Положение новой записи зависит от типа набора записей:  
  
-   В наборе записей, куда вставляется новая запись не гарантируется. Это поведение изменено с Microsoft Jet 3.0 по соображениям производительности и параллелизма. Если ваша цель — сделать вновь добавленная запись текущей, получить закладки для последнего изменения записи и перейти к закладке:  
  
 [!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]  
  
-   В наборе записей тип таблицы, для которого было задано индекса возвращаются записи в их правильном месте в порядке сортировки. Если индекс не был определен, новые записи возвращаются в конце набора записей.  
  
 Запись, которая была текущей до использования `AddNew` остаются актуальными. Если вы хотите сделать текущим новой записи, а набор записей поддерживает закладок, вызов [SetBookmark](#setbookmark) закладку, определяется значение свойства LastModified базового объекта набора записей DAO. Это полезно для определения значения для полей счетчика (с автоматическим приращением) в добавленная запись. Дополнительные сведения см. в разделе [GetLastModifiedBookmark](#getlastmodifiedbookmark).  
  
 Если базы данных поддерживает транзакции, можно сделать ваш `AddNew` вызовов часть транзакции. Дополнительные сведения о транзакциях см. класс [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Обратите внимание, что необходимо вызвать [CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) перед вызовом `AddNew`.  
  
 Недопустимо для вызова `AddNew` для объекта recordset, [откройте](#open) функция-член не был вызван. Объект `CDaoException` возникает при вызове метода `AddNew` для набора записей, который не может быть добавлен. Можно определить, является ли набор записей обновляется путем вызова [CanAppend](#canappend).  
  
 Метки framework изменить поля элементов данных, чтобы убедиться, что они будут записаны на запись в источнике данных с помощью механизма обмена (DFX) полями записей DAO. Как правило, изменение значения поля устанавливает для поля «грязных» автоматически, поэтому редко нужно вызывать [SetFieldDirty](#setfielddirty) самостоятельно, но иногда может потребоваться убедитесь, что столбцы будут быть явным образом обновлены или вставлены независимо от какое значение находится в элемента данных поля. Механизм DFX также используются использование **ПСЕВДО NULL**. Дополнительные сведения см. в разделе [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 Если не используется механизм двойной буферизации, изменив значение поля не задает автоматически поле как "грязные". В этом случае он будет необходимо явно задать поле «грязных». Флаг, содержащихся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) управляет эту проверку автоматического поля.  
  
> [!NOTE]
>  Если есть записи, двойная буферизация (то есть поле автоматического включена проверка), вызов `CancelUpdate` переменных-членов приведет к восстановлению до значения, которые они имели до `AddNew` или **изменить** был вызван.  
  
 Дополнительные сведения см. в разделах «Метод AddNew», «Метод CancelUpdate», «Свойство LastModified» и «EditMode свойство» в справке DAO.  
  
##  <a name="canappend"></a>CDaoRecordset::CanAppend  
 Вызовите эту функцию-член для определения того, допускает ли ранее открывавшихся записей можно добавить новые записи путем вызова [AddNew](#addnew) функции-члена.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей разрешает добавление новых записей; в противном случае — 0. `CanAppend`Возвращает 0, если открыть набор записей, только для чтения.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «Добавление Method» в справке DAO.  
  
##  <a name="canbookmark"></a>CDaoRecordset::CanBookmark  
 Вызовите эту функцию-член для определения ли ранее открывавшихся записей позволяет отдельно пометить записей с помощью закладок.  
  
```  
BOOL CanBookmark();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей поддерживает закладки, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 При использовании наборов записей, основываясь целиком на таблицах ядра базы данных Microsoft Jet, можно использовать закладки за исключением для записей типа снимка, помеченное как прокрутки наборы последовательного доступа. Другие базы данных (внешние источники данных ODBC) могут не поддерживать закладки.  
  
 Дополнительные сведения см. в разделе «Свойство Bookmarkable» в справке DAO.  
  
##  <a name="cancelupdate"></a>CDaoRecordset::CancelUpdate  
 `CancelUpdate` Функция-член отменяет все имеющиеся обновления из-за [изменить](#edit) или [AddNew](#addnew) операции.  
  
```  
virtual void CancelUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Например, если приложение вызывает **изменить** или `AddNew` функции-члена и не вызван [обновление](#update), `CancelUpdate` отменяет все изменения, внесенные после **изменить**или `AddNew` был вызван.  
  
> [!NOTE]
>  Если есть записи, двойная буферизация (то есть поле автоматического включена проверка), вызов `CancelUpdate` переменных-членов приведет к восстановлению до значения, которые они имели до `AddNew` или **изменить** был вызван.  
  
 При наличии не **изменить** или `AddNew` операции, `CancelUpdate` вызывает MFC для создания исключения. Вызовите [GetEditMode](#geteditmode) функцию-член, чтобы определить, имеется отложенная операция, которую можно отменить.  
  
 Дополнительные сведения см. в разделе «Метод CancelUpdate» в справке DAO.  
  
##  <a name="canrestart"></a>CDaoRecordset::CanRestart  
 Вызовите эту функцию-член для определения того, допускает ли набор записей перезапуска его запроса (чтобы обновить свои записи) путем вызова **Requery** функции-члена.  
  
```  
BOOL CanRestart();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если **Requery** может быть вызван для запуска набора записей запрос повторно, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Наборы записей тип таблицы не поддерживают **Requery**.  
  
 Если **Requery** — не поддерживается вызов [закрыть](#close) затем [откройте](#open) обновления данных. Можно вызвать **Requery** обновление набора записей объекта основного запроса с параметрами после изменения значений параметров.  
  
 Дополнительные сведения см. в разделе «Свойство перезапуска» в справке DAO.  
  
##  <a name="canscroll"></a>CDaoRecordset::CanScroll  
 Вызовите эту функцию-член для определения того, допускает ли прокрутка набора записей.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если можно прокручивать записи, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 При вызове метода [откройте](#open) с **dbForwardOnly**, набор записей только может прокручиваться вперед.  
  
 Дополнительные сведения см. в разделе «Позиционирования текущей записи указателя с DAO» справки DAO.  
  
##  <a name="cantransact"></a>CDaoRecordset::CanTransact  
 Вызовите эту функцию-член для определения того, допускает ли набор записей транзакций.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в источнике данных поддерживает транзакции, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «Свойство транзакции» в справке DAO.  
  
##  <a name="canupdate"></a>CDaoRecordset::CanUpdate  
 Вызовите эту функцию-член для определения, возможно ли обновление набора записей.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если можно обновить набор записей (Добавление, обновление и удаление записей), иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Набор записей может быть только для чтения, если базовый источник данных доступен только для чтения или если вы указали **dbReadOnly** для `nOptions` при вызове [откройте](#open) для набора записей.  
  
 Дополнительные сведения см. в разделах «Метод AddNew», «Изменить метод», «Метода Delete», «Метод Update» и «Обновляемые свойства» в справке DAO.  
  
##  <a name="cdaorecordset"></a>CDaoRecordset::CDaoRecordset  
 Создает объект `CDaoRecordset`.  
  
```  
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pDatabase`  
 Содержит указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объект или значение **NULL**. В противном случае **NULL** и `CDaoDatabase` объекта **откройте** функция-член не был вызван соединиться с источником данных, набор записей пытается открыть его автоматически во время свой собственный [открыть ](#open) вызова. Если передать **NULL**, `CDaoDatabase` создается и подключение с использованием источника данных, если производного класса набора записей из указанного объекта `CDaoRecordset`.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать либо `CDaoRecordset` напрямую или быть производным классом от приложения из `CDaoRecordset`. Мастер классов можно использовать для формирования классов набора записей.  
  
> [!NOTE]
>  Если вы наследуете `CDaoRecordset` класса, производного класса необходимо указать свой собственный конструктор. В конструкторе производного класса, вызовите конструктор `CDaoRecordset::CDaoRecordset`, передавая ей соответствующие параметры вместе.  
  
 Передайте **NULL** конструктор набора записей иметь `CDaoDatabase` объект создается и подключенным для вас автоматически. Это удобно использовать, не требует создания и подключение `CDaoDatabase` объекта до создания набора записей. Если `CDaoDatabase` объектов не открыт, [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) также будет создан объект, использует рабочую область по умолчанию. Дополнительные сведения см. в разделе [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).  
  
##  <a name="close"></a>CDaoRecordset::Close  
 Закрытие `CDaoRecordset` объект удаляется из коллекции открытие наборов записей в связанной базы данных.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку **закрыть** не уничтожает `CDaoRecordset` объекта, можно повторно использовать объект путем вызова **откройте** на тот же источник данных или другого источника данных.  
  
 Все ожидающие [AddNew](#addnew) или [изменить](#edit) отменяются и всех незавершенных транзакций будет выполнен откат. Если вы хотите сохранить отложенные добавления и изменения, вызовите [обновление](#update) перед вызовом метода **закрыть** для каждого набора записей.  
  
 Можно вызвать **откройте** повторно после вызова **закрыть**. Это позволяет повторно использовать объекта набора записей. Лучшим вариантом будет вызывать [Requery](#requery), если это возможно.  
  
 Дополнительные сведения см. в разделе «Метод Close» в справке DAO.  
  
##  <a name="delete"></a>CDaoRecordset::Delete  
 Вызовите эту функцию-член для удаления текущей записи в открытом объекте набора записей динамического или тип таблицы.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Примечания  
 После успешного удаления, элементам данных полей, присваивается значение Null, и необходимо явно вызвать один из функции-члены навигации набора записей ( [переместить](#move), [Seek](#seek), [ SetBookmark](#setbookmark)и так далее), чтобы отказаться от удаленной записи. При удалении записей из набора записей должен существовать текущей записи в наборе записей перед вызовом метода **удалить**; в противном случае MFC вызывает исключение.  
  
 **Удалить** удаляет текущую запись и делает ее недоступной. Несмотря на то, что нельзя изменить или использовать удаленную запись, остаются актуальными. После перемещения в другую запись, тем не менее, нельзя создать удаленную запись текущей еще раз.  
  
> [!CAUTION]
>  Набор записей должна быть обновлена, а должно быть допустимой записи в наборе записей текущего при вызове **удалить**. Например, если удалить запись, но не прокручиваются новой записи перед вызовом метода **удалить** , **удаление** вызывает [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Отмена удаления записи при использовании транзакций и вызывать [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) функции-члена. Если базовая таблица является таблицей первичного каскадом удалить связь, удаление текущей записи может также удалить одну или несколько записей во внешней таблице. Дополнительные сведения см. в разделе Определение «каскадное удаление» справки DAO.  
  
 В отличие от `AddNew` и **изменить**, вызов **удаление** должен следовать вызов **обновление**.  
  
 Дополнительные сведения см. в разделах «Метод AddNew», «Изменить метод», «Метода Delete», «Метод Update» и «Обновляемые свойства» в справке DAO.  
  
##  <a name="dofieldexchange"></a>CDaoRecordset::DoFieldExchange  
 Платформа вызывает эту функцию-член для обмена данными между элементами данных полей объекта набора записей и соответствующих столбцов текущей записи в источнике данных автоматически.  
  
```  
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Содержит указатель на `CDaoFieldExchange` объект. Платформа уже будет установлен этот объект для указания контекста для операции обмена поля.  
  
### <a name="remarks"></a>Примечания  
 Также привязывает параметризованные члены данных, если таковые имеются, соответствует заполнителям параметров в строке инструкции SQL для выбора набора записей. Обмен полей данных, называемый обмен полями записей DAO (DFX) работает в обоих направлениях: члены данных полей объекта набора записей с полями записи в источнике данных и запись в источнике данных для объекта набора записей. Если динамическая привязка столбцов необходимых для реализации `DoFieldExchange`.  
  
 Единственным действием, обычно необходимо выполнить для реализации `DoFieldExchange` для набора записей производный класс является создание класса с ClassWizard и укажите имена и типы данных элементов данных полей. Можно также добавить код, ClassWizard записывает для указания элементов данных параметров. Все поля являются привязываться динамически, эта функция будет неактивна, если не указать параметризованные члены данных.  
  
 При объявлении класса производного набора записей с ClassWizard мастер записывает переопределение `DoFieldExchange` , что аналогичный следующему примеру:  
  
 [!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]  
  
##  <a name="edit"></a>CDaoRecordset::Edit  
 Вызовите эту функцию-член, чтобы разрешить изменения в текущей записи.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Примечания  
 При вызове метода **изменить** функция-член, изменения, внесенные в поля текущей записи, копируются в буфер копирования. После внесения требуемых изменений к записи, вызовите **обновление** для сохранения изменений. **Изменить** сохраняет значения членов данных набора записей. При вызове метода **изменить**, внесите изменения, затем вызовите **изменить** , восстанавливаются значения записи он находился перед первым **изменить** вызова.  
  
> [!CAUTION]
>  Если изменить запись, а затем выполнять любые операции, который переходит к другой записи без предварительного вызова функции **обновление**, изменения будут утеряны без предупреждения. Кроме того Если закрыть родительскую базу данных или набора записей, к измененной записи удаляются без предупреждения.  
  
 В некоторых случаях может потребоваться обновить столбец, делая Null (содержащий нет данных). Чтобы сделать это, вызовите `SetFieldNull` с параметром **TRUE** пометить поле Null; это также приводит обновляемого столбца. Если необходимо добавить поле записи с источником данных, несмотря на то, что его значение не изменилось, вызовите `SetFieldDirty` с параметром **TRUE**. Это работает, даже если оно имело значение Null.  
  
 Метки framework изменить поля элементов данных, чтобы убедиться, что они будут записаны на запись в источнике данных с помощью механизма обмена (DFX) полями записей DAO. Как правило, изменение значения поля устанавливает для поля «грязных» автоматически, поэтому редко нужно вызывать [SetFieldDirty](#setfielddirty) самостоятельно, но иногда может потребоваться убедитесь, что столбцы будут быть явным образом обновлены или вставлены независимо от какое значение находится в элемента данных поля. Механизм DFX также используются использование **ПСЕВДО NULL**. Дополнительные сведения см. в разделе [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 Если не используется механизм двойной буферизации, изменив значение поля не задает автоматически поле как "грязные". В этом случае он будет необходимо явно задать поле «грязных». Флаг, содержащихся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) управляет эту проверку автоматического поля.  
  
 Когда объекта набора записей pessimistically заблокирован в многопользовательской среде, записи остаются заблокированными с момента **изменить** используется до завершения обновления. Если набор записей оптимистически заблокирован, запись заблокирован и сравнивается с предварительно измененной записи непосредственно перед обновлением данных в базе данных. Если запись была изменена с момента вызова **изменить**, **обновление** завершается с ошибкой и MFC вызывает исключение. Можно изменить режим блокировки с `SetLockingMode`.  
  
> [!NOTE]
>  О форматах внешней базы данных, таких как ODBC и устанавливаемый ISAM всегда используется оптимистическая блокировка.  
  
 Текущая запись остаются актуальными, после вызова метода **изменить**. Для вызова **изменить**, должен быть текущей записи. Если нет текущей записи или набора записей не ссылается на таблицу открытого-типа или типа динамического объекта набора записей, возникает исключение. Вызов **изменить** вызывает `CDaoException` исключение при следующих условиях:  
  
-   Отсутствует текущая запись.  
  
-   Базы данных или набора записей доступно только для чтения.  
  
-   Нет полей в записи недоступны для обновления.  
  
-   Базы данных или набора записей был открыт другим пользователем в монопольном режиме.  
  
-   Другой пользователь уже заблокировал страницы, содержащей записи.  
  
 Если источник данных поддерживает транзакции, то сможете **изменить** вызовов часть транзакции. Обратите внимание, что необходимо вызвать `CDaoWorkspace::BeginTrans` перед вызовом **изменить** и после открытия набора записей. Также Обратите внимание, что вызов `CDaoWorkspace::CommitTrans` не заменять вызов **обновление** для завершения **изменить** операции. Дополнительные сведения о транзакциях см. класс `CDaoWorkspace`.  
  
 Дополнительные сведения см. в разделах «Метод AddNew», «Изменить метод», «Метода Delete», «Метод Update» и «Обновляемые свойства» в справке DAO.  
  
##  <a name="fillcache"></a>CDaoRecordset::FillCache  
 Вызовите эту функцию-член для кэширования указанное число записей из набора записей.  
  
```  
void FillCache(
    long* pSize = NULL,  
    COleVariant* pBookmark = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pSize`  
 Указывает количество строк для заполнения кэша. Если этот параметр не указан, значение определяется значение CacheSize свойства базового объекта DAO.  
  
 `pBookmark`  
 Объект [COleVariant](../../mfc/reference/colevariant-class.md) указания закладки. Кэш заполняется, начиная с записи, обозначается данной закладки. Если этот параметр не указан, кэш заполняется, начиная с записи, указано в свойстве CacheStart базового объекта DAO.  
  
### <a name="remarks"></a>Примечания  
 Кэширование позволяет повысить производительность приложения, которое получает или извлекает данные с удаленного сервера. Кэш — пространство в локальной памяти, хранящего данные последней выбранной строки с сервера на предположении, что данные будут, скорее всего, быть запрошено повторно во время выполнения приложения. При запросе данных базы данных Microsoft Jet сначала проверяет кэш для данных вместо получения его из на сервер, который занимает больше времени. С помощью кэширования данных на источники данных не ODBC не действует как данные не сохраняются в кэше.  
  
 Вместо ожидания кэша должен быть заполнен записей, как они не будут выбраны, можно явно заполнить кэш в любое время путем вызова `FillCache` функции-члена. Это более быстрый способ заполнения кэша, так как `FillCache` выбирается несколько записей одновременно, вместо одной записи за раз. Например, во время отображения экранной каждой записи, что вызов приложения `FillCache` для получения следующего один экран записей.  
  
 Любой базы данных ODBC, доступ к набору записей объектов может иметь локального кэша. Чтобы создать кэш, откройте объекта набора записей из удаленного источника данных и затем вызвать `SetCacheSize` и `SetCacheStart` функций-членов набора записей. Если `lSize` и *lBookmark* создать диапазон, частично или полностью за пределами диапазона, заданного предложением `SetCacheSize` и `SetCacheStart`, часть набора записей за пределами этого диапазона, обрабатывается и не загружается в кэш. Если `FillCache` запрашивает записей больше, чем остаются в удаленном источнике данных, будут выбраны только оставшихся записей и исключение не возникает.  
  
 Записей, выбранных из кэша не отражают изменения, сделанные параллельно с источником данных другими пользователями.  
  
 `FillCache`извлекает только те записи, которые еще не кэшируются. Чтобы принудительно обновить кэшированные данные, вызовите `SetCacheSize` функцию-член с `lSize` параметра равно 0, вызов `SetCacheSize` с `lSize` параметр равен размеру кэша запрашивали, а затем вызвать `FillCache`.  
  
 Дополнительные сведения см. в разделе «Метод FillCache» в справке DAO.  
  
##  <a name="find"></a>CDaoRecordset::Find  
 Вызовите эту функцию-член для поиска определенной строки в наборе записей добавляющий или моментальных снимков с помощью оператора сравнения.  
  
```  
virtual BOOL Find(
    long lFindType,  
    LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Параметры  
 *lFindType*  
 Значение, указывающее тип требуемой операции поиска. Допустимые значения:  
  
- **AFX_DAO_NEXT** найти путь для следующего совпадения.  
  
- **AFX_DAO_PREV** местоположения предыдущего совпадения.  
  
- **AFX_DAO_FIRST** найти первое расположение совпадения.  
  
- **AFX_DAO_LAST** местоположения последнего совпадения.  
  
 `lpszFilter`  
 Строковое выражение (как **ГДЕ** предложения в инструкции SQL без слова **ГДЕ**) используется для поиска записи. Пример:  
  
 [!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если Обнаружены совпадающие записи, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Во-первых, далее, можно найти экземпляр предыдущей, или последней строки. **Найти** настолько виртуальную функцию, можно изменить ее и добавить свою собственную реализацию. `FindFirst`, `FindLast`, `FindNext`, И `FindPrev` функции-члены вызывают **найти** функции-члена, чтобы можно было использовать **найти** для управления поведением всех операций поиска .  
  
 Чтобы найти запись в наборе записей табличного типа, вызовите [Seek](#seek) функции-члена.  
  
> [!TIP]
>  Меньший набор записей, у вас есть, тем она эффективнее **найти** будет. В целом и особенно с данных ODBC лучше создать новый запрос, который извлекает необходимые записи.  
  
 Дополнительные сведения см. в разделе «FindNext FindFirst FindLast, методы FindPrevious» в справке DAO.  
  
##  <a name="findfirst"></a>CDaoRecordset::FindFirst  
 Вызовите эту функцию-член для поиска первой записи, которая соответствует заданному условию.  
  
```  
BOOL FindFirst(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFilter`  
 Строковое выражение (как **ГДЕ** предложения в инструкции SQL без слова **ГДЕ**) используется для поиска записи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если Обнаружены совпадающие записи, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `FindFirst` Функции-члена начинает поиск с начала набора записей и продолжается до конца набора данных.  
  
 Если требуется включить все записи в поиска (не только те, которые удовлетворяют определенному условию) используют одну из операций перемещения для перемещения по записям. Чтобы найти запись в наборе записей табличного типа, вызовите `Seek` функции-члена.  
  
 Если записи, соответствующие критериям не найден, указатель текущей записи не определена, и `FindFirst` возвращает ноль. Если набор записей содержит несколько записей, которые удовлетворяют критериям, `FindFirst` находит первое вхождение `FindNext` находит следующее вхождение и т. д.  
  
> [!CAUTION]
>  При изменении текущей записи, не забудьте сохранить изменения, вызвав **обновление** функция-член перед тем как перейти к другой записи. При перемещении в другую запись без обновления, внесенные изменения будут потеряны без предупреждения.  
  
 **Найти** поиск функций-членов из расположения, так и в направлении, указанным в следующей таблице:  
  
|Найти операции|Begin|Направление поиска|  
|---------------------|-----------|----------------------|  
|`FindFirst`|Начало набора записей|Конец набора записей|  
|`FindLast`|Конец набора записей|Начало набора записей|  
|`FindNext`|Текущая запись.|Конец набора записей|  
|**FindPrevious**|Текущая запись.|Начало набора записей|  
  
> [!NOTE]
>  При вызове `FindLast`, базы данных Microsoft Jet полностью заполняет набор записей до начала поиска, если это еще не была выполнена. Первого поиска может занять больше времени, чем последующие поиска.  
  
 С помощью одной из операций поиска не совпадает с вызовом **MoveFirst** или `MoveNext`, тем не менее, который просто делает первой или следующей записи текущего без указания условие. Вы можете использовать операцию поиска с помощью операции перемещения.  
  
 При использовании операции поиска необходимо учитывайте следующее:  
  
-   Если **найти** возвращает ненулевое значение, текущая запись не определен. В этом случае необходимо поместить указатель текущей записи к допустимой записи.  
  
-   Нельзя использовать операцию поиска с помощью однонаправленного прокрутки статического типа набора записей.  
  
-   Американский формат даты (месяц день год) следует использовать при поиске полей, содержащих даты, даже если не используется версия США, ядро базы данных Microsoft Jet; в противном случае подходящие записи могут быть не найдены.  
  
-   При работе с базами данных ODBC и больших динамических подмножеств данных, вы можете заметить, что с помощью операции поиска работает медленно, особенно при работе с большой наборы записей. Можно повысить производительность с помощью SQL-запросов с настроен **ORDERBY** или **ГДЕ** предложений, запросы с параметрами, или **CDaoQuerydef** объектов, извлекать определенного индексированные записей.  
  
 Дополнительные сведения см. в разделе «FindNext FindFirst FindLast, методы FindPrevious» в справке DAO.  
  
##  <a name="findlast"></a>CDaoRecordset::FindLast  
 Вызовите эту функцию-член, чтобы найти последнюю запись, которая соответствует заданному условию.  
  
```  
BOOL FindLast(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFilter`  
 Строковое выражение (как **ГДЕ** предложения в инструкции SQL без слова **ГДЕ**) используется для поиска записи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если Обнаружены совпадающие записи, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `FindLast` Функции-члена начинает поиск с конца набора данных и выполняет поиск назад к началу набора записей.  
  
 Если требуется включить все записи в поиска (не только те, которые удовлетворяют определенному условию) используют одну из операций перемещения для перемещения по записям. Чтобы найти запись в наборе записей табличного типа, вызовите `Seek` функции-члена.  
  
 Если записи, соответствующие критериям не найден, указатель текущей записи не определена, и `FindLast` возвращает ноль. Если набор записей содержит несколько записей, которые удовлетворяют критериям, `FindFirst` находит первое вхождение `FindNext` находит следующее вхождение после первого вхождения и т. д.  
  
> [!CAUTION]
>  При изменении текущей записи, нужно убедиться, что нужно сохранить изменения, вызвав **обновление** функция-член перед тем как перейти к другой записи. При перемещении в другую запись без обновления, внесенные изменения будут потеряны без предупреждения.  
  
 С помощью одной из операций поиска не совпадает с вызовом **MoveFirst** или `MoveNext`, тем не менее, который просто делает первой или следующей записи текущего без указания условие. Вы можете использовать операцию поиска с помощью операции перемещения.  
  
 При использовании операции поиска необходимо учитывайте следующее:  
  
-   Если **найти** возвращает ненулевое значение, текущая запись не определен. В этом случае необходимо поместить указатель текущей записи к допустимой записи.  
  
-   Нельзя использовать операцию поиска с помощью однонаправленного прокрутки статического типа набора записей.  
  
-   Американский формат даты (месяц день год) следует использовать при поиске полей, содержащих даты, даже если не используется версия США, ядро базы данных Microsoft Jet; в противном случае подходящие записи могут быть не найдены.  
  
-   При работе с базами данных ODBC и больших динамических подмножеств данных, вы можете заметить, что с помощью операции поиска работает медленно, особенно при работе с большой наборы записей. Можно повысить производительность с помощью SQL-запросов с настроен **ORDERBY** или **ГДЕ** предложений, запросы с параметрами, или **CDaoQuerydef** объектов, извлекать определенного индексированные записей.  
  
 Дополнительные сведения см. в разделе «FindNext FindFirst FindLast, методы FindPrevious» в справке DAO.  
  
##  <a name="findnext"></a>CDaoRecordset::FindNext  
 Вызовите эту функцию-член для следующей записи, которая соответствует заданному условию поиска.  
  
```  
BOOL FindNext(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFilter`  
 Строковое выражение (как **ГДЕ** предложения в инструкции SQL без слова **ГДЕ**) используется для поиска записи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если Обнаружены совпадающие записи, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `FindNext` Функция-член начинает поиск в текущей строке и выполняет поиск в конец набора записей.  
  
 Если требуется включить все записи в поиска (не только те, которые удовлетворяют определенному условию) используют одну из операций перемещения для перемещения по записям. Чтобы найти запись в наборе записей табличного типа, вызовите `Seek` функции-члена.  
  
 Если записи, соответствующие критериям не найден, указатель текущей записи не определена, и `FindNext` возвращает ноль. Если набор записей содержит несколько записей, которые удовлетворяют критериям, `FindFirst` находит первое вхождение `FindNext` находит следующее вхождение и т. д.  
  
> [!CAUTION]
>  При изменении текущей записи, нужно убедиться, что нужно сохранить изменения, вызвав **обновление** функция-член перед тем как перейти к другой записи. При перемещении в другую запись без обновления, внесенные изменения будут потеряны без предупреждения.  
  
 С помощью одной из операций поиска не совпадает с вызовом **MoveFirst** или `MoveNext`, тем не менее, который просто делает первой или следующей записи текущего без указания условие. Вы можете использовать операцию поиска с помощью операции перемещения.  
  
 При использовании операции поиска необходимо учитывайте следующее:  
  
-   Если **найти** возвращает ненулевое значение, текущая запись не определен. В этом случае необходимо поместить указатель текущей записи к допустимой записи.  
  
-   Нельзя использовать операцию поиска с помощью однонаправленного прокрутки статического типа набора записей.  
  
-   Американский формат даты (месяц день год) следует использовать при поиске полей, содержащих даты, даже если не используется версия США, ядро базы данных Microsoft Jet; в противном случае подходящие записи могут быть не найдены.  
  
-   При работе с базами данных ODBC и больших динамических подмножеств данных, вы можете заметить, что с помощью операции поиска работает медленно, особенно при работе с большой наборы записей. Можно повысить производительность с помощью SQL-запросов с настроен **ORDERBY** или **ГДЕ** предложений, запросы с параметрами, или **CDaoQuerydef** объектов, извлекать определенного индексированные записей.  
  
 Дополнительные сведения см. в разделе «FindNext FindFirst FindLast, методы FindPrevious» в справке DAO.  
  
##  <a name="findprev"></a>CDaoRecordset::FindPrev  
 Вызовите эту функцию-член для предыдущей записи, которая соответствует заданному условию поиска.  
  
```  
BOOL FindPrev(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFilter`  
 Строковое выражение (как **ГДЕ** предложения в инструкции SQL без слова **ГДЕ**) используется для поиска записи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если Обнаружены совпадающие записи, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `FindPrev` Функция-член начинает поиск в текущей строке и ищет в обратном направлении к началу набора записей.  
  
 Если требуется включить все записи в поиска (не только те, которые удовлетворяют определенному условию) используют одну из операций перемещения для перемещения по записям. Чтобы найти запись в наборе записей табличного типа, вызовите `Seek` функции-члена.  
  
 Если записи, соответствующие критериям не найден, указатель текущей записи не определена, и `FindPrev` возвращает ноль. Если набор записей содержит несколько записей, которые удовлетворяют критериям, `FindFirst` находит первое вхождение `FindNext` находит следующее вхождение и т. д.  
  
> [!CAUTION]
>  При изменении текущей записи, нужно убедиться, что нужно сохранить изменения, вызвав **обновление** функция-член перед тем как перейти к другой записи. При перемещении в другую запись без обновления, внесенные изменения будут потеряны без предупреждения.  
  
 С помощью одной из операций поиска не совпадает с вызовом **MoveFirst** или `MoveNext`, тем не менее, который просто делает первой или следующей записи текущего без указания условие. Вы можете использовать операцию поиска с помощью операции перемещения.  
  
 При использовании операции поиска необходимо учитывайте следующее:  
  
-   Если **найти** возвращает ненулевое значение, текущая запись не определен. В этом случае необходимо поместить указатель текущей записи к допустимой записи.  
  
-   Нельзя использовать операцию поиска с помощью однонаправленного прокрутки статического типа набора записей.  
  
-   Американский формат даты (месяц день год) следует использовать при поиске полей, содержащих даты, даже если не используется версия США, ядро базы данных Microsoft Jet; в противном случае подходящие записи могут быть не найдены.  
  
-   При работе с базами данных ODBC и больших динамических подмножеств данных, вы можете заметить, что с помощью операции поиска работает медленно, особенно при работе с большой наборы записей. Можно повысить производительность с помощью SQL-запросов с настроен **ORDERBY** или **ГДЕ** предложений, запросы с параметрами, или **CDaoQuerydef** объектов, извлекать определенного индексированные записей.  
  
 Дополнительные сведения см. в разделе «FindNext FindFirst FindLast, методы FindPrevious» в справке DAO.  
  
##  <a name="getabsoluteposition"></a>CDaoRecordset::GetAbsolutePosition  
 Возвращает номер текущей записи объекта набора записей.  
  
```  
long GetAbsolutePosition();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число от 0 до количества записей в наборе записей. Соответствует порядковой позиции текущей записи в наборе записей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства AbsolutePosition базового объекта DAO (с нуля); значение, равное 0 относится к первой записи в наборе записей. Можно определить количество заполненных записей в наборе записей, вызвав [GetRecordCount](#getrecordcount). Вызов `GetRecordCount` может занять некоторое время, так как он должен получить доступ к все записи, чтобы определить число объектов.  
  
 Если отсутствует текущая запись, как при нет записей в наборе записей, - 1 возвращается. При удалении текущей записи, значение свойства AbsolutePosition не определен и MFC вызывает исключение, если на него ссылаться. Для наборов записей добавляющий новые записи добавляются в конец последовательности.  
  
> [!NOTE]
>  Это свойство не предназначено для использования в качестве символов-заместителей номер записи. Закладки по-прежнему рекомендуемый способ сохранения и возврат к заданной позиции и единственный способ размещения текущей записи для всех типов объектов набора записей. В частности позицию данной записи изменяется при удалении записи перед ее. Нет никакой гарантии, что данная запись будет иметь же абсолютное положение, если повторно набора записей создается снова, потому что порядок отдельных записей в наборе записей не обязательно, если он создается с помощью инструкции SQL с помощью  **ORDERBY** предложения.  
  
> [!NOTE]
>  Эта функция-член является допустимым только для динамического типа и записей типа снимка.  
  
 Дополнительные сведения см. в разделе «Свойство AbsolutePosition» в справке DAO.  
  
##  <a name="getbookmark"></a>CDaoRecordset::GetBookmark  
 Вызовите эту функцию-член, чтобы получить значение закладки в определенной записи.  
  
```  
COleVariant GetBookmark();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, представляющее закладку на текущей записи.  
  
### <a name="remarks"></a>Примечания  
 При создании или открытии объекта набора записей, каждая из него записей уже уникальная закладка если их поддерживает. Вызовите `CanBookmark` , чтобы определить, поддерживает ли набор записей закладки.  
  
 Можно сохранить закладку для текущей записи, присваивая значение закладки, с которой `COleVariant` объекта. Чтобы быстро вернуться к этой записи в любое время после перемещения в другой записи, вызовите `SetBookmark` с параметром, который соответствует значению, `COleVariant` объекта.  
  
> [!NOTE]
>  Вызов [Requery](#requery) изменяет DAO закладки.  
  
 Дополнительные сведения см. в разделе «Свойства закладки» в справке DAO.  
  
##  <a name="getcachesize"></a>CDaoRecordset::GetCacheSize  
 Вызовите эту функцию-член для получения число записей в кэше.  
  
```  
long GetCacheSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее количество записей в наборе записей, с данными, кэшироваться локально из источника данных ODBC.  
  
### <a name="remarks"></a>Примечания  
 Кэширование данных повышает производительность приложения, получающий данные с удаленного сервера через объекты типа динамического набора записей. Кэш представляет пробел в локальной памяти, которая содержит данные, самое последнее полученное от сервера, в том случае, если данные будет запрошена во время выполнения приложения. При запросе данных базы данных Microsoft Jet сначала проверяет кэш для запрошенных данных вместо их извлечения из на сервер, который занимает больше времени. Данные, которые получены из источника данных ODBC не сохраняется в кэше.  
  
 Любой источник данных ODBC, например подключенной таблицы могут иметь локального кэша.  
  
 Дополнительные сведения см. в разделе «CacheSize CacheStart свойства» в справке DAO.  
  
##  <a name="getcachestart"></a>CDaoRecordset::GetCacheStart  
 Вызовите эту функцию-член для получения значения первой записи в наборе записей, кэшируемых закладки.  
  
```  
COleVariant GetCacheStart();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `COleVariant` , указывающий закладки первой записи в наборе записей для кэширования.  
  
### <a name="remarks"></a>Примечания  
 Базы данных Microsoft Jet запрашивает записей в пределах диапазона кэша из кэша, а он запрашивает записи за пределами диапазона кэша с сервера.  
  
> [!NOTE]
>  Записей, полученных из кэша не отражают изменения, сделанные параллельно с источником данных другими пользователями.  
  
 Дополнительные сведения см. в разделе «CacheSize CacheStart свойства» в справке DAO.  
  
##  <a name="getcurrentindex"></a>CDaoRecordset::GetCurrentIndex  
 Вызовите эту функцию-член для определения индекса, в настоящее время индексированные табличный тип `CDaoRecordset` объекта.  
  
```  
CString GetCurrentIndex();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` содержит имя индекса в данный момент recordset табличного типа. Возвращает пустую строку, если индекс не было задано.  
  
### <a name="remarks"></a>Примечания  
 Данный индекс является основой для упорядочения записей в наборе записей табличного типа и используется [Seek](#seek) функции-члена для поиска записей.  
  
 Объект `CDaoRecordset` объект может иметь несколько индексов, но одновременно можно использовать только один индекс (хотя [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) объекта может быть несколько определенных индексов).  
  
 Дополнительные сведения см. раздел «Объект индекса» и «текущий индекс» в справке DAO определение.  
  
##  <a name="getdatecreated"></a>CDaoRecordset::GetDateCreated  
 Вызовите эту функцию-член для извлечения дату и время создания базовой таблицы.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий дату и время создания базовой таблицы.  
  
### <a name="remarks"></a>Примечания  
 Параметры даты и времени являются производными от компьютера, на котором был создан базовой таблицы.  
  
 Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.  
  
##  <a name="getdatelastupdated"></a>CDaoRecordset::GetDateLastUpdated  
 Вызовите эту функцию-член для извлечения дату и время последнего обновления схемы.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий дату и время последнего обновления структуры базовой таблицы (схема).  
  
### <a name="remarks"></a>Примечания  
 Параметры даты и времени являются производными от компьютера, последнего обновления структуры базовой таблицы (схема).  
  
 Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.  
  
##  <a name="getdefaultdbname"></a>CDaoRecordset::GetDefaultDBName  
 Вызовите эту функцию-член для определения имени базы данных для этого набора записей.  
  
```  
virtual CString GetDefaultDBName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий путь и имя базы данных, из которого создается данный набор записей.  
  
### <a name="remarks"></a>Примечания  
 Если набор записей создается без указатель [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), а затем этот путь используется набор записей для открытия базы данных по умолчанию. По умолчанию эта функция возвращает пустую строку. Когда ClassWizard производный новый набор записей из `CDaoRecordset`, эта функция создаст для вас.  
  
 Следующий пример иллюстрирует использование две обратные косые черты (\\\\) в строке, как требуется для правильной интерпретации строки.  
  
 [!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]  
  
##  <a name="getdefaultsql"></a>CDaoRecordset::GetDefaultSQL  
 Платформа вызывает эту функцию-член для получения оператора SQL по умолчанию, на котором основан набор записей.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий инструкцию SQL по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Это может быть имя таблицы или SQL **ВЫБЕРИТЕ** инструкции.  
  
 Косвенно определите инструкцию SQL по умолчанию путем объявления класса набора записей с ClassWizard и ClassWizard не выполняет эту задачу автоматически.  
  
 Если передается значение null, строка для [откройте](#open), то эта функция вызывается для определения имени таблицы или SQL для набора записей.  
  
##  <a name="geteditmode"></a>CDaoRecordset::GetEditMode  
 Вызовите эту функцию-член для определения состояния редактирования, которое является одним из следующих значений:  
  
```  
short GetEditMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, указывающее состояние редактирования для текущей записи.  
  
### <a name="remarks"></a>Примечания  
  
|Значение|Описание:|  
|-----------|-----------------|  
|**dbEditNone**|Ни одна из операций редактирования уже выполняется.|  
|**dbEditInProgress**|**Изменить** был вызван.|  
|**dbEditAdd**|`AddNew`был вызван.|  
  
 Дополнительные сведения см. в разделе «Свойство EditMode» в справке DAO.  
  
##  <a name="getfieldcount"></a>CDaoRecordset::GetFieldCount  
 Вызовите эту функцию-член для извлечения нескольких полей (столбцов), определенных в наборе записей.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число полей в наборе записей.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «Свойство Count» в справке DAO.  
  
##  <a name="getfieldinfo"></a>CDaoRecordset::GetFieldInfo  
 Вызовите эту функцию-член для получения сведений о полях в наборе записей.  
  
```  
void GetFieldInfo(
    int nIndex,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetFieldInfo(
    LPCTSTR lpszName,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс предопределенных полей в коллекции полей набора записей, для поиска по индексу.  
  
 `fieldinfo`  
 Ссылку на [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры.  
  
 `dwInfoOptions`  
 Параметры, определяющие, какой набор записей для извлечения. Здесь перечислены доступные параметры и как они вызвать функцию возврата. Для наилучшей производительности загрузки только уровня необходимые сведения:  
  
- `AFX_DAO_PRIMARY_INFO`(По умолчанию) Имя, тип, размер, атрибуты  
  
- `AFX_DAO_SECONDARY_INFO`Первичные данные, а также: порядковый номер позиции, необходимые, разрешить нулевой длины, порядок сортировки, внешнего имени, исходное поле исходной таблицы  
  
- `AFX_DAO_ALL_INFO`Основной и дополнительной информации, а также: текст для проверки значения по умолчанию, правила проверки  
  
 `lpszName`  
 Имя поля.  
  
### <a name="remarks"></a>Примечания  
 Одну версию функции позволяет найти поле с индексом. Другая версия позволяет искать поле по имени.  
  
 Описание сведений, возвращаемых см. в разделе [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют элементам данных, перечисленные выше в описании `dwInfoOptions`. При запросе сведения на одном уровне, вы получаете сведения всех предыдущих уровней.  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="getfieldvalue"></a>CDaoRecordset::GetFieldValue  
 Вызовите эту функцию-член для извлечения данных в наборе записей.  
  
```  
virtual void GetFieldValue(
    LPCTSTR lpszName,  
    COleVariant& varValue);

 
virtual void GetFieldValue(
    int nIndex,  
    COleVariant& varValue);
 
virtual COleVariant GetFieldValue(LPCTSTR lpszName); 
virtual COleVariant GetFieldValue(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку, содержащую имя поля.  
  
 `varValue`  
 Ссылку на `COleVariant` объекта, который будет хранить значение поля.  
  
 `nIndex`  
 Отсчитываемый от нуля индекс поля в коллекции полей набора записей, для поиска по индексу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Две версии `GetFieldValue` , которые возвращают значение возврата [COleVariant](../../mfc/reference/colevariant-class.md) объект, содержащий значение поля.  
  
### <a name="remarks"></a>Примечания  
 Поля можно искать по имени или по порядковому номеру.  
  
> [!NOTE]
>  Более эффективно для вызова одной из версий эта функция-член, принимающий `COleVariant` ссылку на объект как параметр, а не версию, которая возвращает вызов `COleVariant` объекта. Более поздние версии этой функции сохраняются для обеспечения обратной совместимости.  
  
 Используйте `GetFieldValue` и [SetFieldValue](#setfieldvalue) динамически привязывать поля во время выполнения, а не статически привязки столбцов с помощью [DoFieldExchange](#dofieldexchange) механизм.  
  
 `GetFieldValue`и `DoFieldExchange` механизм можно объединять для повышения производительности. Например, использовать `GetFieldValue` получить значение, которое требуется только по требованию, и назначить этот вызов на кнопку «Подробнее» в интерфейсе.  
  
 Дополнительные сведения см. в разделах «Поле объект» и «Значение свойства» в справке DAO.  
  
##  <a name="getindexcount"></a>CDaoRecordset::GetIndexCount  
 Вызовите эту функцию-член для определения числа индексов, доступных на данном множестве записей табличного типа.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество индексов в таблице типа записей.  
  
### <a name="remarks"></a>Примечания  
 `GetIndexCount`полезно для перебора всех индексов в наборе записей. Для этой цели используйте `GetIndexCount` в сочетании с [GetIndexInfo](#getindexinfo). При вызове этой функции-члена для динамического или записей типа снимка, MFC вызывает исключение.  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="getindexinfo"></a>CDaoRecordset::GetIndexInfo  
 Вызовите эту функцию-член для получения различные виды информации о индекс, определенный в базовой таблице набор записей.  
  
```  
void GetIndexInfo(
    int nIndex,  
    CDaoIndexInfo& indexinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetIndexInfo(
    LPCTSTR lpszName,  
    CDaoIndexInfo& indexinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс в коллекции индексов таблицы, для поиска по числовой позиции.  
  
 `indexinfo`  
 Ссылку на [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры.  
  
 `dwInfoOptions`  
 Параметры, указывающие, какие сведения об индексе для извлечения. Здесь перечислены доступные параметры и как они вызвать функцию возврата. Для наилучшей производительности загрузки только уровня необходимые сведения:  
  
- `AFX_DAO_PRIMARY_INFO`(По умолчанию) Сведения о поле, имя поля  
  
- `AFX_DAO_SECONDARY_INFO`Первичные данные, а также: основной, Unique, кластеризованный, IgnoreNulls, необходимые, внешний  
  
- `AFX_DAO_ALL_INFO`Основной и дополнительной информации, а также: числа различных объектов  
  
 `lpszName`  
 Указатель на имя объекта индекса для поиска по имени.  
  
### <a name="remarks"></a>Примечания  
 Одну версию функции позволяет найти индекс с указанной позицией в коллекции. Другая версия позволяет найти индекс с именем.  
  
 Описание сведений, возвращаемых см. в разделе [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют элементам данных, перечисленные выше в описании `dwInfoOptions`. При запросе сведения на одном уровне, вы получаете сведения всех предыдущих уровней.  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="getlastmodifiedbookmark"></a>CDaoRecordset::GetLastModifiedBookmark  
 Вызовите эту функцию-член для извлечения закладки наиболее новые или обновленные записи.  
  
```  
COleVariant GetLastModifiedBookmark();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `COleVariant` с закладкой, указывающее, недавно добавленных или измененных записей.  
  
### <a name="remarks"></a>Примечания  
 При создании или открытии объекта набора записей, каждая из него записей уже уникальная закладка если их поддерживает. Вызовите [GetBookmark](#getbookmark) , чтобы определить, поддерживает ли набор записей закладки. Если набор записей не поддерживает закладки, `CDaoException` возникает исключение.  
  
 При добавлении записи отображается в конце набора записей и не является текущей записи. Чтобы сделать новую запись текущей, вызовите `GetLastModifiedBookmark` и затем вызвать метод `SetBookmark` для возврата вновь добавленной записи.  
  
 Дополнительные сведения см. в разделе «Свойство LastModified» в справке DAO.  
  
##  <a name="getlockingmode"></a>CDaoRecordset::GetLockingMode  
 Вызовите эту функцию-член для определения типа фактически блокировки для набора записей.  
  
```  
BOOL GetLockingMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если тип блокировки пессимистическая, в противном случае значение 0 для нежесткой блокировки.  
  
### <a name="remarks"></a>Примечания  
 Когда Пессимистическая блокировка действует, страницы данных, содержащего запись, вы изменяете блокировки сразу после вызова [изменить](#edit) функции-члена. Страница не заблокирован при вызове [обновление](#update) или [закрыть](#close) функции-члена или любой из операций поиска или перемещения.  
  
 Если оптимистическая блокировка действует страница данных, содержащая запись блокируется, только в том случае, пока запись обновляется с **обновление** функции-члена.  
  
 При работе с источниками данных ODBC, режим блокировки всегда является оптимистическим.  
  
 Дополнительные сведения см. в разделах «Свойства LockEdits» и «Блокировки поведение в многопользовательском приложений» в справке DAO.  
  
##  <a name="getname"></a>CDaoRecordset::GetName  
 Вызовите эту функцию-член для извлечения имени набора записей.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` содержит имя набора записей.  
  
### <a name="remarks"></a>Примечания  
 Имя набора записей должно начинаться с буквы и может содержать не более 40 знаков. Он может включать цифры и символы подчеркивания, но не может содержать знаки пунктуации и пробелы.  
  
 Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.  
  
##  <a name="getparamvalue"></a>CDaoRecordset::GetParamValue  
 Вызовите эту функцию-член для извлечения текущее значение указанного параметра, сохраненного в базовый объект DAOParameter.  
  
```  
virtual COleVariant GetParamValue(int nIndex);  
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Числовая позиция параметра в базовый объект DAOParameter.  
  
 `lpszName`  
 Имя параметра, значение которого требуется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект класса [COleVariant](../../mfc/reference/colevariant-class.md) , содержащее значение параметра.  
  
### <a name="remarks"></a>Примечания  
 Параметр доступен по имени или его числовую позицию в коллекции.  
  
 Дополнительные сведения см. в разделе «Параметр объект» в справке DAO.  
  
##  <a name="getpercentposition"></a>CDaoRecordset::GetPercentPosition  
 При работе с динамического или набора записей типа моментальных снимков, если вы вызываете `GetPercentPosition` до полного заполнения набора записей, перемещение указывается относительно количество записей, доступ к, обозначенный вызов [GetRecordCount](#getrecordcount).  
  
```  
float GetPercentPosition();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число от 0 до 100, указывающее Приблизительное расположение текущей записи в объекте recordset, основанные на процентах записей в наборе записей.  
  
### <a name="remarks"></a>Примечания  
 Вы можно перейти к последней записи путем вызова [MoveLast](#movelast) для завершения заполнения все наборы записей, но это может занять значительное время.  
  
 Можно вызвать `GetPercentPosition` на всех трех типов объектов набора записей, включая таблицы без индексов. Тем не менее, не может вызвать `GetPercentPosition` последовательным прокрутки моментальные снимки или набор записей, открытый передаваемого запроса от внешней базы данных. Если отсутствует текущая запись или текущая запись. он был удален, `CDaoException` возникает исключение.  
  
 Дополнительные сведения см. в разделе «Свойство PercentPosition» в справке DAO.  
  
##  <a name="getrecordcount"></a>CDaoRecordset::GetRecordCount  
 Вызовите эту функцию-член чтобы узнать, сколько записей в наборе записей были прочитаны.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число записей в объекте recordset.  
  
### <a name="remarks"></a>Примечания  
 `GetRecordCount`Указывает количество записей содержатся типа динамического или набора записей типа снимка пока все записи были прочитаны. Это вызова функции-члена может занять значительное время.  
  
 После обращения последней записи, которая возвращает значение, указывающее общее количество неудаленными записей в наборе записей. Чтобы принудительно доступ к последней записи, вызовите `MoveLast` или `FindLast` функция-член для набора записей. Также можно использовать SQL Count для определения приблизительное количество записей, которые возвращает запрос.  
  
 Как приложение удаляет записи в наборе записей динамического типа, возвращаемое значение `GetRecordCount` уменьшается. Тем не менее, записи, удаленные другим пользователям, не отражаются в `GetRecordCount` до текущей записи располагается удаленная запись. Если выполняется транзакция, которая влияет на число записей и впоследствии откат транзакции, `GetRecordCount` не будет отражать фактическое число оставшихся записей.  
  
 Значение `GetRecordCount` из набора записей типа моментальных снимков не влияют изменения в базовых таблицах.  
  
 Значение `GetRecordCount` из тип таблицы набор записей отражает приблизительное количество записей в таблице и немедленно влияет как добавления и удаления записей в таблице.  
  
 Набор записей с записи не возвращает значение 0. При работе с таблицами или баз данных ODBC, `GetRecordCount` всегда возвращается значение-1. Вызов **Requery** функции-члена набора записей сбрасывает значение `GetRecordCount` как если бы были повторно выполняется запрос.  
  
 Дополнительные сведения см. в разделе «RecordCount свойство» в справке DAO.  
  
##  <a name="getsql"></a>CDaoRecordset::GetSQL  
 Вызовите эту функцию-член для получения инструкции SQL, который был использован для выбора записей в наборе записей, когда он был открыт.  
  
```  
CString GetSQL() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий инструкции SQL.  
  
### <a name="remarks"></a>Примечания  
 Как правило, это будет SQL **ВЫБЕРИТЕ** инструкции.  
  
 Строка, возвращаемая функцией `GetSQL` обычно отличается от любую строку в набор записей в Вы передали `lpszSQL` параметр [откройте](#open) функции-члена. Это обусловлено записей создает полная инструкция SQL, в зависимости от того, что Вы передали **откройте**, указанный с ClassWizard и что указан в [m_strFilter](#m_strfilter) и [m_strSort](#m_strsort) членов данных.  
  
> [!NOTE]
>  Вызовите эту функцию-член только после вызова метода **откройте**.  
  
 Дополнительные сведения см. в разделе «Свойство SQL» в справке DAO.  
  
##  <a name="gettype"></a>CDaoRecordset::GetType  
 Эта функция-член вызывается после открытия набора записей, чтобы определить тип объекта набора записей.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений, указывающих тип набора записей:  
  
- **dbOpenTable** recordset табличного типа  
  
- **dbOpenDynaset** копирование или изменение  
  
- **dbOpenSnapshot** набора записей типа снимка  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.  
  
##  <a name="getvalidationrule"></a>CDaoRecordset::GetValidationRule  
 Вызовите эту функцию-член для определения правил, используемый для проверки данных.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, содержащий значение, которое проверяет данные в записи, как изменить или добавить в таблицу.  
  
### <a name="remarks"></a>Примечания  
 Это правило выполняется на основе текста и применяется каждый раз при изменении базовой таблицы. Если данные не является допустимым, MFC вызывает исключение. Сообщения об ошибке — свертыванию базового объекта поля, если указанный текст или текст выражения, указанного в свойстве ValidationRule базового объекта поля. Можно вызвать [GetValidationText](#getvalidationtext) для получения текста сообщения об ошибке.  
  
 Например, в поле записи, которая требует дня месяца может быть правило проверки «BETWEEN день 1 до 31.»  
  
 Дополнительные сведения см. в разделе «ValidationRule свойство» в справке DAO.  
  
##  <a name="getvalidationtext"></a>CDaoRecordset::GetValidationText  
 Вызовите эту функцию-член для извлечения текста свертыванию базового объекта поля.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объекта, содержащего текст сообщения, которое отображается, если значение поля не удовлетворяет правило проверки базового объекта поля.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.  
  
##  <a name="isbof"></a>CDaoRecordset::IsBOF  
 Вызов этой функции-члена до перехода от записи к записи, чтобы узнать, является ли проверены перед первой записью в наборе записей.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей не содержит записей или прокручен назад перед первой записью; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Можно также вызвать `IsBOF` вместе с `IsEOF` чтобы определить набор записей содержит какие-либо записи или является пустым. Сразу после вызова метода **откройте**, набор записей не содержит записей, `IsBOF` возвращает ненулевое значение. При открытии набора записей, который имеет по крайней мере одну запись, первая запись становится текущей записью и `IsBOF` возвращает 0.  
  
 Если первая запись становится текущей записи и вызывается `MovePrev`, `IsBOF` впоследствии возвращает ненулевое значение. Если `IsBOF` возвращает ненулевое значение, при вызове метода `MovePrev`, создается исключение. Если `IsBOF` возвращает ненулевое значение, текущая запись не определена, и любое действие, которое требует текущей записи будет приведет к исключению.  
  
 Влияние методов, определенных в `IsBOF` и `IsEOF` параметры:  
  
-   Вызов **откройте** внутренне делает первую запись в наборе записей текущей записи путем вызова **MoveFirst**. Таким образом, вызов **откройте** на пустой набор записей причины `IsBOF` и `IsEOF` для возврата ненулевое значение. (См. следующую таблицу для поведения сбоя **MoveFirst** или `MoveLast` вызова.)  
  
-   Все операции перемещения, найдите запись, успешно вызвать оба `IsBOF` и `IsEOF` возвращает значение 0.  
  
-   `AddNew` Вызова, за которым следует **обновление** , успешно вставляет новую запись вызова `IsBOF` для возврата 0, но только если `IsEOF` уже имеет ненулевое значение. Состояние `IsEOF` всегда остаются неизменными. В соответствии с определением базы данных Microsoft Jet, указатель текущей записи пустому набору записей — в конце файла, поэтому любой новая запись вставляется после текущей записи.  
  
-   Любой **удаление** вызов, даже если он удаляет только оставшиеся записи из набора записей не изменится значение `IsBOF` или `IsEOF`.  
  
 В этой таблице показано, какие операции перемещения разрешены с различными комбинациями `IsBOF` /  `IsEOF`.  
  
||MoveFirst, MoveLast|MovePrev,<br /><br /> Переместить < 0|Переместить 0|MoveNext,<br /><br /> Переместить > 0|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`= значение ненулевое,<br /><br /> `IsEOF`=0|Allowed|Исключение|Исключение|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`ненулевое значение =|Allowed|Allowed|Исключение|Исключение|  
|Оба ненулевое значение|Исключение|Исключение|Исключение|Исключение|  
|Оба 0|Allowed|Allowed|Allowed|Allowed|  
  
 Разрешение операции перемещения не означает операцию успешно обнаружит записи. Просто указывает на то попытка выполнить указанную операцию перемещения может и не создаст исключение. Значение `IsBOF` и `IsEOF` функций-членов может измениться в результате Предпринятая операция перемещения.  
  
 Эффект перемещения операций, которые не найдите запись, на значение `IsBOF` и `IsEOF` параметры, показаны в следующей таблице.  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**,`MoveLast`|Ненулевое значение|Ненулевое значение|  
|**Переместить** 0|Без изменений|Без изменений|  
|`MovePrev`, **Переместить** < 0|Ненулевое значение|Без изменений|  
|`MoveNext`, **Переместить** > 0|Без изменений|Ненулевое значение|  
  
 Дополнительные сведения см. в разделе «BOF, EOF свойства» в справке DAO.  
  
##  <a name="isdeleted"></a>CDaoRecordset::IsDeleted  
 Вызовите эту функцию-член для определения, был ли удален текущей записи.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей располагается на удаленную запись; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если прокручивать записи и `IsDeleted` возвращает **TRUE** (не равно нулю), затем вы должны перейти к другой записи перед тем как выполнять никакие другие операции набора записей.  
  
> [!NOTE]
>  Нет необходимости проверять состояние удаленных записей в наборе записей моментальных снимков или тип таблицы. Так как невозможно удалить записи из моментального снимка, нет необходимости вызывать `IsDeleted`. Для записей типа таблицы удаленные записи фактически удаляются из набора записей. После записи был удален, вы другим пользователем или в другой записей перемещаться к этой записи невозможно. Таким образом, нет необходимости вызывать `IsDeleted`.  
  
 При удалении записи из подмножества он удаляется из набора записей, и нельзя прокрутки к этой записи. Тем не менее, если запись в динамический набор будет удален другим пользователем или в другом записей на основе одной таблицы `IsDeleted` вернет **TRUE** при позднее перейти к этой записи.  
  
 Дополнительные сведения см. в разделах «Метода Delete», «Дата изменения свойства» и «EditMode свойство» в справке DAO.  
  
##  <a name="iseof"></a>CDaoRecordset::IsEOF  
 Вызовите эту функцию-член, при переходе от записи к записи, чтобы узнать, является ли вышли за пределы последней записи в наборе записей.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если набор записей не содержит записей или выполнен переход за последнюю запись; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Можно также вызвать `IsEOF` чтобы определить набор записей содержит какие-либо записи или является пустым. Сразу после вызова метода **откройте**, набор записей не содержит записей, `IsEOF` возвращает ненулевое значение. При открытии набора записей, который имеет по крайней мере одну запись, первая запись становится текущей записью и `IsEOF` возвращает 0.  
  
 Если последняя запись становится текущей записью, при вызове `MoveNext`, `IsEOF` впоследствии возвращает ненулевое значение. Если `IsEOF` возвращает ненулевое значение, при вызове метода `MoveNext`, создается исключение. Если `IsEOF` возвращает ненулевое значение, текущая запись не определена, и любое действие, которое требует текущей записи будет приведет к исключению.  
  
 Влияние методов, определенных в `IsBOF` и `IsEOF` параметры:  
  
-   Вызов **откройте** внутренне делает первую запись в наборе записей текущей записи путем вызова **MoveFirst**. Таким образом, вызов **откройте** на пустой набор записей причины `IsBOF` и `IsEOF` для возврата ненулевое значение. (См. следующую таблицу для поведения сбоя **MoveFirst** вызова.)  
  
-   Все операции перемещения, найдите запись, успешно вызвать оба `IsBOF` и `IsEOF` возвращает значение 0.  
  
-   `AddNew` Вызова, за которым следует **обновление** , успешно вставляет новую запись вызова `IsBOF` для возврата 0, но только если `IsEOF` уже имеет ненулевое значение. Состояние `IsEOF` всегда остаются неизменными. В соответствии с определением базы данных Microsoft Jet, указатель текущей записи пустому набору записей — в конце файла, поэтому любой новая запись вставляется после текущей записи.  
  
-   Любой **удаление** вызов, даже если он удаляет только оставшиеся записи из набора записей не изменится значение `IsBOF` или `IsEOF`.  
  
 В этой таблице показано, какие операции перемещения разрешены с различными комбинациями `IsBOF` /  `IsEOF`.  
  
||MoveFirst, MoveLast|MovePrev,<br /><br /> Переместить < 0|Переместить 0|MoveNext,<br /><br /> Переместить > 0|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`= значение ненулевое,<br /><br /> `IsEOF`=0|Allowed|Исключение|Исключение|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`ненулевое значение =|Allowed|Allowed|Исключение|Исключение|  
|Оба ненулевое значение|Исключение|Исключение|Исключение|Исключение|  
|Оба 0|Allowed|Allowed|Allowed|Allowed|  
  
 Разрешение операции перемещения не означает операцию успешно обнаружит записи. Просто указывает на то попытка выполнить указанную операцию перемещения может и не создаст исключение. Значение `IsBOF` и `IsEOF` функций-членов может измениться в результате Предпринятая операция перемещения.  
  
 Эффект перемещения операций, которые не найдите запись, на значение `IsBOF` и `IsEOF` параметры, показаны в следующей таблице.  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**,`MoveLast`|Ненулевое значение|Ненулевое значение|  
|**Переместить** 0|Без изменений|Без изменений|  
|`MovePrev`, **Переместить** < 0|Ненулевое значение|Без изменений|  
|`MoveNext`, **Переместить** > 0|Без изменений|Ненулевое значение|  
  
 Дополнительные сведения см. в разделе «BOF, EOF свойства» в справке DAO.  
  
##  <a name="isfielddirty"></a>CDaoRecordset::IsFieldDirty  
 Вызовите эту функцию-член для определения, помечена ли член подмножества данных указанного поля как «грязных» (изменить).  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 Указатель на член поля данных, состояние которой требуется проверить, или **NULL** для определения полей «грязных».  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент данных заданного поля помечен как "грязный"; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Данные в все измененными элементами данных полей должны быть переданы запись в источнике данных при обновлении текущей записи путем вызова **обновление** функцию-член `CDaoRecordset` (после вызова **изменить**или `AddNew`). Обладая такими сведениями, можно выполнить дополнительные действия, такие как ее снятие элемента данных поля, чтобы пометить столбец, поэтому она не будет записана в источник данных.  
  
 `IsFieldDirty`реализуется с помощью `DoFieldExchange`.  
  
##  <a name="isfieldnull"></a>CDaoRecordset::IsFieldNull  
 Вызовите эту функцию-член, чтобы определить, помечен ли элемент данных заданного поля в наборе записей как Null.  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 Указатель на член поля данных, состояние которой требуется проверить, или **NULL** для определения, если любое из полей имеют значение Null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент данных заданного поля будет отмечена как Null. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 (В терминологии связанных баз данных, Null означает «предложений having значение отсутствует», а не является таким же, как **NULL** в C++.) Если элемент данных поля помечен как Null, то он интерпретируется как столбца текущей записи, для которых нет значения.  
  
> [!NOTE]
>  В некоторых случаях использование `IsFieldNull` может оказаться неэффективным, как показано в следующем примере кода:  
  
 [!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]  
  
> [!NOTE]
>  При использовании динамической привязки записей, не на основе `CDaoRecordset`, обязательно используйте **VT_NULL** как показано в примере.  
  
##  <a name="isfieldnullable"></a>CDaoRecordset::IsFieldNullable  
 Вызовите эту функцию-член, чтобы определить, является ли элемент данных заданного поля «nullable» (может быть присвоено значение Null; C++ **NULL** не обязательно является Null, означающее, в терминологии связанных баз данных, «предложений having значение отсутствует»).  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 Указатель на член поля данных, состояние которой требуется проверить, или **NULL** для определения, если любое из полей имеют значение Null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент данных заданного поля может быть выполнено Null; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Поле, которое не может иметь значение Null должны иметь значение. При попытке задать такому полю значение Null во время добавления или обновления записи источника данных отклоняет Добавление или обновление, и **обновление** вызовет исключение. Исключение возникает при вызове **обновление**, не при вызове `SetFieldNull`.  
  
##  <a name="isopen"></a>CDaoRecordset::IsOpen  
 Вызовите эту функцию-член для определения того, открыт ли набор записей.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объекта набора записей **откройте** или **Requery** ранее вызвать функцию-член и набор записей не закрыт; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_bcheckcachefordirtyfields"></a>CDaoRecordset::m_bCheckCacheForDirtyFields  
 Содержит флаг, указывающий ли кэшированные поля автоматически помечаются как "грязный" (измененного) и Null.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию используется флаг **TRUE**. Параметр в этот элемент данных управляет весь механизм двойной буферизации. Если задан флаг **TRUE**, можно отключить кэширование для поля, с помощью механизма DFX. Если задан флаг **FALSE**, необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.  
  
 Значение этого элемента данных, перед вызовом метода **откройте**. Этот механизм используется главным образом для удобства использования. Производительность снижается из-за двойной буферизации полей при внесении изменений.  
  
##  <a name="m_nfields"></a>CDaoRecordset::m_nFields  
 Содержит число элементов данных полей в классе записей и число столбцов, выбранных в наборе записей из источника данных.  
  
### <a name="remarks"></a>Примечания  
 Необходимо инициализировать конструктор для класса записей `m_nFields` с правильным числом статически связанные поля. Мастер классов записывает инициализация автоматически при использовании для объявления класса набора записей. Можно также создать его вручную.  
  
 Платформа использует это число для управления взаимодействием между элементами данных полей и соответствующие столбцы текущей записи в источнике данных.  
  
> [!NOTE]
>  Этот номер должен соответствовать количеству выходных столбцов, зарегистрированные в `DoFieldExchange` после вызова `SetFieldType` с параметром **CDaoFieldExchange::outputColumn**.  
  
 Вы можете привязать столбцы динамически с помощью `CDaoRecordset::GetFieldValue` и `CDaoRecordset::SetFieldValue`. Если сделать это, необходимо увеличить число в `m_nFields` в соответствии с количество функции DFX вызовов вашей `DoFieldExchange` функции-члена.  
  
##  <a name="m_nparams"></a>CDaoRecordset::m_nParams  
 Содержит количество элементов данных параметров в классе записей — количество параметров, переданных с запросом набора записей.  
  
### <a name="remarks"></a>Примечания  
 Если класс набора записей элементов данных параметров, необходимо инициализировать конструктор для класса `m_nParams` с правильным числом. Значение `m_nParams` по умолчанию равно 0. При добавлении элементов данных параметров — это необходимо сделать вручную — необходимо также вручную добавить инициализацию в конструкторе класса, в соответствии с числом параметров (который должен быть по крайней мере количество '' меток-заполнителей в вашей **m_strFilter**  или `m_strSort` строка).  
  
 Платформа использует этот номер, если он параметризует запрос набора записей.  
  
> [!NOTE]
>  Этот номер должен соответствовать номеру «params», зарегистрированный в `DoFieldExchange` после вызова `SetFieldType` с параметром **CFieldExchange::param**.  
  
 Дополнительные сведения см. в разделе «Параметр объект» в справке DAO.  
  
##  <a name="m_pdaorecordset"></a>CDaoRecordset::m_pDAORecordset  
 Содержит указатель на интерфейс OLE для базового объекта набора записей DAO `CDaoRecordset` объекта.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот указатель, если требуется прямой доступ к интерфейсу DAO.  
  
 Дополнительные сведения см. в разделе «Набор записей объект» в справке DAO.  
  
##  <a name="m_pdatabase"></a>CDaoRecordset::m_pDatabase  
 Содержит указатель на `CDaoDatabase` объекта, через который набор записей подключен к источнику данных.  
  
### <a name="remarks"></a>Примечания  
 Эта переменная задается двумя способами. Как правило, передать указатель на уже открытого `CDaoDatabase` объекта при создании объекта набора записей. Если передать **NULL** вместо этого **CDaoRecordset** создает `CDaoDatabase` объект и открывает его. В любом случае `CDaoRecordset` сохраняет указатель в этой переменной.  
  
 Обычно не требуется напрямую использовать указателем, сохраненным в **m_pDatabase**. При написании собственных расширений для `CDaoRecordset`, однако может потребоваться использовать указатель. Например, может потребоваться указатель при вызове собственных `CDaoException`(s).  
  
 Дополнительные сведения см. в разделе «Объект базы данных» в справке DAO.  
  
##  <a name="m_strfilter"></a>CDaoRecordset::m_strFilter  
 Содержит строку, которая используется для создания **ГДЕ** предложения FROM инструкции SQL.  
  
### <a name="remarks"></a>Примечания  
 Отсутствует зарезервированное слово **ГДЕ** для фильтрации набора записей. Использование этого элемента данных не применим для записей типа таблицы. Использование **m_strFilter** не имеет значения при открытии набора записей с помощью `CDaoQueryDef` указателя.  
  
 Используйте формат даты (месяц день год) США при фильтрации полей, содержащих даты, даже если не используется версия США, ядро базы данных Microsoft Jet; в противном случае данные не могут быть отфильтрованы, должным образом.  
  
 Дополнительные сведения см. в разделе «Свойства фильтра» в справке DAO.  
  
##  <a name="m_strsort"></a>CDaoRecordset::m_strSort  
 Содержит строку, содержащую **ORDERBY** предложения FROM инструкции SQL без зарезервированных слов **ORDERBY**.  
  
### <a name="remarks"></a>Примечания  
 Можно выполнить сортировку по динамического моментального снимка тип объекта набора записей.  
  
 Нельзя выполнить сортировку объекта набора записей типа таблицы. Чтобы определить порядок сортировки recordset табличного типа, вызовите [SetCurrentIndex](#setcurrentindex).  
  
 Использование `m_strSort` не имеет значения при открытии набора записей с помощью `CDaoQueryDef` указателя.  
  
 Дополнительные сведения см. в разделе «Свойства сортировки» в справке DAO.  
  
##  <a name="move"></a>CDaoRecordset::Move  
 Вызовите эту функцию-член для размещения набора записей `lRows` записей с текущей записью.  
  
```  
virtual void Move(long lRows);
```  
  
### <a name="parameters"></a>Параметры  
 `lRows`  
 Количество записей для перемещения вперед или назад. Положительные значения Переход вперед, к концу набора записей. Отрицательные значения перемещение назад, к началу.  
  
### <a name="remarks"></a>Примечания  
 Можно перемещаться вперед и назад. `Move( 1 )`эквивалентно `MoveNext`, и `Move( -1 )` эквивалентно `MovePrev`.  
  
> [!CAUTION]
>  Вызов любого из **переместить** функции вызывает исключение, если набор записей не имеющей записей. Как правило, вызвать `IsBOF` и `IsEOF` перед операции перемещения, чтобы определить какие-либо записи набора записей. После вызова метода **откройте** или **Requery**, вызвать либо метод `IsBOF` или `IsEOF`.  
  
> [!NOTE]
>  Если выполнен переход за начало или конец набора записей ( `IsBOF` или `IsEOF` возвращает ненулевое значение), вызов **переместить** вызывает `CDaoException`.  
  
> [!NOTE]
>  При вызове любого из **переместить** функции во время текущей записи обновляется или добавления, обновления будут потеряны без предупреждения.  
  
 При вызове **переместить** на снимках прокруткой только вперед, `lRows` параметр должен быть положительным целым числом и не допускаются закладки, чтобы можно было перейти вперед только.  
  
 Чтобы первой, последней, следующей или предыдущей записи в наборе записей текущей записи, вызов **MoveFirst**, `MoveLast`, `MoveNext`, или `MovePrev` функции-члена.  
  
 Дополнительные сведения см. в разделах «Переместить метод» и «MoveFirst, MoveLast, MoveNext, методы MovePrevious» в справке DAO.  
  
##  <a name="movefirst"></a>CDaoRecordset::MoveFirst  
 Вызовите эту функцию-член вносить первой записи в наборе записей (если таковые имеются) текущей записи.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Примечания  
 Нет необходимости вызывать **MoveFirst** сразу после открытия набора записей. В это время первой записи (если таковые имеются) автоматически является текущей записи.  
  
> [!CAUTION]
>  Вызов любого из **переместить** функции вызывает исключение, если набор записей не имеющей записей. Как правило, вызвать `IsBOF` и `IsEOF` перед операции перемещения, чтобы определить какие-либо записи набора записей. После вызова метода **откройте** или **Requery**, вызвать либо метод `IsBOF` или `IsEOF`.  
  
> [!NOTE]
>  При вызове любого из **переместить** функции во время текущей записи обновляется или добавления, обновления будут потеряны без предупреждения.  
  
 Используйте **переместить** функции для перемещения по записям без применения условия. Используйте операции поиска для поиска записей в наборе или объекта набора записей статического типа, которые удовлетворяют определенному условию. Чтобы найти запись в таблице тип объекта набора записей, вызовите `Seek`.  
  
 Если набор записей содержит ссылку на recordset табличного типа, перемещение после текущего индекса таблицы. Текущий индекс можно задать с помощью индекса свойства базового объекта DAO. Если не установлен текущий индекс, не определен порядок возвращаемых записей.  
  
 При вызове метода `MoveLast` принудительно запрос в объекте recordset, на основе SQL-запроса или querydef, завершение и будет заполнена объекта набора записей.  
  
 Не удается вызвать **MoveFirst** или `MovePrev` функция-член с прокруткой только вперед моментального снимка.  
  
 Чтобы переместить позицию текущего записи в объекте recordset конкретного записей вперед или назад, вызовите **переместить**.  
  
 Дополнительные сведения см. в разделах «Переместить метод» и «MoveFirst, MoveLast, MoveNext, методы MovePrevious» в справке DAO.  
  
##  <a name="movelast"></a>CDaoRecordset::MoveLast  
 Вызов этой функции-члена вносить последней записи (если таковые имеются) в текущую запись набора записей.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Вызов любого из **переместить** функции вызывает исключение, если набор записей не имеющей записей. Как правило, вызвать `IsBOF` и `IsEOF` перед операции перемещения, чтобы определить какие-либо записи набора записей. После вызова метода **откройте** или **Requery**, вызвать либо метод `IsBOF` или `IsEOF`.  
  
> [!NOTE]
>  При вызове любого из **переместить** функции во время текущей записи обновляется или добавления, обновления будут потеряны без предупреждения.  
  
 Используйте **переместить** функции для перемещения по записям без применения условия. Используйте операции поиска для поиска записей в наборе или объекта набора записей статического типа, которые удовлетворяют определенному условию. Чтобы найти запись в таблице тип объекта набора записей, вызовите `Seek`.  
  
 Если набор записей содержит ссылку на recordset табличного типа, перемещение после текущего индекса таблицы. Текущий индекс можно задать с помощью индекса свойства базового объекта DAO. Если не установлен текущий индекс, не определен порядок возвращаемых записей.  
  
 При вызове метода `MoveLast` принудительно запрос в объекте recordset, на основе SQL-запроса или querydef, завершение и будет заполнена объекта набора записей.  
  
 Чтобы переместить позицию текущего записи в объекте recordset конкретного записей вперед или назад, вызовите **переместить**.  
  
 Дополнительные сведения см. в разделах «Переместить метод» и «MoveFirst, MoveLast, MoveNext, методы MovePrevious» в справке DAO.  
  
##  <a name="movenext"></a>CDaoRecordset::MoveNext  
 Вызовите эту функцию-член для внесения следующей записи в текущую запись набора записей.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Примечания  
 Рекомендуется вызывать `IsBOF` прежде чем перейти к предыдущей записи. Вызов `MovePrev` вызовет `CDaoException` Если `IsBOF` возвращает ненулевое значение, указывающее, что была выполнена прокрутка перед первой записью или что записи не были выбраны, набор записей.  
  
> [!CAUTION]
>  Вызов любого из **переместить** функции вызывает исключение, если набор записей не имеющей записей. Как правило, вызвать `IsBOF` и `IsEOF` перед операции перемещения, чтобы определить какие-либо записи набора записей. После вызова метода **откройте** или **Requery**, вызвать либо метод `IsBOF` или `IsEOF`.  
  
> [!NOTE]
>  При вызове любого из **переместить** функции во время текущей записи обновляется или добавления, обновления будут потеряны без предупреждения.  
  
 Используйте **переместить** функции для перемещения по записям без применения условия. Используйте операции поиска для поиска записей в наборе или объекта набора записей статического типа, которые удовлетворяют определенному условию. Чтобы найти запись в таблице тип объекта набора записей, вызовите `Seek`.  
  
 Если набор записей содержит ссылку на recordset табличного типа, перемещение после текущего индекса таблицы. Текущий индекс можно задать с помощью индекса свойства базового объекта DAO. Если не установлен текущий индекс, не определен порядок возвращаемых записей.  
  
 Чтобы переместить позицию текущего записи в объекте recordset конкретного записей вперед или назад, вызовите **переместить**.  
  
 Дополнительные сведения см. в разделах «Переместить метод» и «MoveFirst, MoveLast, MoveNext, методы MovePrevious» в справке DAO.  
  
##  <a name="moveprev"></a>CDaoRecordset::MovePrev  
 Вызовите эту функцию-член для внесения предыдущей записи в текущую запись набора записей.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Примечания  
 Рекомендуется вызывать `IsBOF` прежде чем перейти к предыдущей записи. Вызов `MovePrev` вызовет `CDaoException` Если `IsBOF` возвращает ненулевое значение, указывающее, что была выполнена прокрутка перед первой записью или что записи не были выбраны, набор записей.  
  
> [!CAUTION]
>  Вызов любого из **переместить** функции вызывает исключение, если набор записей не имеющей записей. Как правило, вызвать `IsBOF` и `IsEOF` перед операции перемещения, чтобы определить какие-либо записи набора записей. После вызова метода **откройте** или **Requery**, вызвать либо метод `IsBOF` или `IsEOF`.  
  
> [!NOTE]
>  При вызове любого из **переместить** функции во время текущей записи обновляется или добавления, обновления будут потеряны без предупреждения.  
  
 Используйте **переместить** функции для перемещения по записям без применения условия. Используйте операции поиска для поиска записей в наборе или объекта набора записей статического типа, которые удовлетворяют определенному условию. Чтобы найти запись в таблице тип объекта набора записей, вызовите `Seek`.  
  
 Если набор записей содержит ссылку на recordset табличного типа, перемещение после текущего индекса таблицы. Текущий индекс можно задать с помощью индекса свойства базового объекта DAO. Если не установлен текущий индекс, не определен порядок возвращаемых записей.  
  
 Не удается вызвать **MoveFirst** или `MovePrev` функция-член с прокруткой только вперед моментального снимка.  
  
 Чтобы переместить позицию текущего записи в объекте recordset конкретного записей вперед или назад, вызовите **переместить**.  
  
 Дополнительные сведения см. в разделах «Переместить метод» и «MoveFirst, MoveLast, MoveNext, методы MovePrevious» в справке DAO.  
  
##  <a name="open"></a>CDaoRecordset::Open  
 Необходимо вызвать эту функцию-член для получения записей для набора записей.  
  
```  
virtual void Open(
    int nOpenType = AFX_DAO_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    int nOptions = 0);

 
virtual void Open(
    CDaoTableDef* pTableDef,  
    int nOpenType = dbOpenTable,  
    int nOptions = 0);

 
virtual void Open(
    CDaoQueryDef* pQueryDef,  
    int nOpenType = dbOpenDynaset,  
    int nOptions = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nOpenType`  
 Одно из следующих значений:  
  
- **dbOpenDynaset** набор записей типа динамического с двунаправленный прокрутки. Это значение по умолчанию.  
  
- **dbOpenTable** recordset табличного типа с двунаправленный прокрутки.  
  
- **dbOpenSnapshot** набор записей типа моментального снимка с двунаправленный прокрутки.  
  
 `lpszSQL`  
 Указатель на строку, содержащую одно из следующих:  
  
-   Объект **NULL** указателя.  
  
-   Имя одного или нескольких tabledefs и/или querydefs (разделенных запятыми).  
  
-   SQL **ВЫБЕРИТЕ** инструкции (при необходимости с помощью SQL **ГДЕ** или **ORDERBY** предложение).  
  
-   Запрос к серверу.  
  
 `nOptions`  
 Один или несколько из указанных ниже параметров. Значение по умолчанию — 0. Ниже приведены возможные значения.  
  
- **dbAppendOnly** можно только добавить новые записи (только для набора записей типа динамического). Этот параметр означает буквально, записи только на добавление. Классы баз данных MFC ODBC имеют заполняемом только параметр, разрешающий записей, извлекаются и добавляются.  
  
- **dbForwardOnly** набор записей является снимком прокруткой только вперед.  
  
- **dbSeeChanges** создают исключение, если другой пользователь изменение данных, вы изменяете.  
  
- **dbDenyWrite** другим пользователям не удается изменить или добавить записи.  
  
- **dbDenyRead** другие пользователи не могут просматривать записи (только для табличного типа записей).  
  
- **dbReadOnly** можно только просмотреть записей, другие пользователи могут изменять их.  
  
- **dbInconsistent** несогласованных обновлений разрешены (копирование или изменение только).  
  
- **dbConsistent** только согласованности обновлений разрешены (копирование или изменение только).  
  
> [!NOTE]
>  Константы **dbConsistent** и **dbInconsistent** являются взаимоисключающими. Можно использовать один или другой, но не одновременно в заданном экземпляре **откройте**.  
  
 *pTableDef*  
 Указатель на [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) объекта. Эта версия допустим только для записей типа таблицы. При использовании этого параметра `CDaoDatabase` указатель, используемый для создания `CDaoRecordset` не используется; вместо этого используется база данных, в которой находится tabledef.  
  
 *pQueryDef*  
 Указатель на [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) объекта. Эта версия является допустимым только для динамического типа и записей типа снимка. При использовании этого параметра `CDaoDatabase` указатель, используемый для создания `CDaoRecordset` не используется; вместо этого используется база данных, в которой находится querydef.  
  
### <a name="remarks"></a>Примечания  
 Перед вызовом метода **откройте**, следует создать объекта набора записей. Для этого можно использовать следующие способы.  
  
-   При создании объекта набора записей, передайте указатель `CDaoDatabase` объекта, который уже открыт.  
  
-   При создании объекта набора записей, передайте указатель на `CDaoDatabase` объект, который не был открыт. Открывает набор записей `CDaoDatabase` объекта, но не закроет его при закрытии объекта набора записей.  
  
-   При создании объекта набора записей, передайте **NULL** указателя. Вызовы объекта набора записей `GetDefaultDBName` получить имя Microsoft Access. Откройте файл MDB. Открывает набор записей `CDaoDatabase` объект и сохраняет его открыть, при условии, что набор записей открыт. При вызове **закрыть** для объекта recordset `CDaoDatabase` объекта также закрывается.  
  
    > [!NOTE]
    >  При открытии набора записей `CDaoDatabase` объекта, он открывает источник данных с совмещаемый доступ.  
  
 Для версии **откройте** , использующий `lpszSQL` параметр, после открытия набора записей для извлечения в одном из следующих способов. Первый вариант — хранить DFX функции в вашей `DoFieldExchange`. Второй вариант — использовать динамическую привязку путем вызова `GetFieldValue` функции-члена. Эти параметры можно реализовать отдельно или в сочетании. Если они объединены, необходимо передать в инструкцию SQL самостоятельно при вызове **откройте**.  
  
 При использовании второй версии **откройте** где передается в `CDaoTableDef` объекта, полученные столбцы будут доступны для привязки через `DoFieldExchange` и DFX механизма, или привязка динамически через `GetFieldValue`.  
  
> [!NOTE]
>  Можно вызвать только **откройте** с помощью `CDaoTableDef` объект для записей типа таблицы.  
  
 При использовании третьей версии **откройте** где передается в `CDaoQueryDef` объектов, что запрос будет выполняться и результирующие столбцы будут доступны для привязки через `DoFieldExchange` и механизмом DFX или динамической привязки через `GetFieldValue`.  
  
> [!NOTE]
>  Можно вызвать только **откройте** с помощью `CDaoQueryDef` объект для динамического типа и записей типа снимка.  
  
 Для первой версии **откройте** , использующий `lpszSQL` параметра записей, выбранных на основе критериев, показанные в следующей таблице.  
  
|Значение параметра `lpszSQL`|Определяется выбрано записей|Пример|  
|--------------------------------------|----------------------------------------|-------------|  
|**NULL**|Строка, возвращаемая функцией `GetDefaultSQL`.||  
|Список разделенных запятыми из одного или нескольких tabledefs и/или querydef имена.|Все столбцы представлены в `DoFieldExchange`.|`"Customer"`|  
|**ВЫБЕРИТЕ** список столбцов **FROM** список таблиц|Указанные столбцы из указанного tabledef(s) и/или querydef(s).|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|  
  
 Стандартные действия заключается в передаче **NULL** для **откройте**; в этом случае **откройте** вызовы `GetDefaultSQL`, переопределяемый член функции, ClassWizard приводит к возникновению ошибки при создании `CDaoRecordset`-производного класса. Это значение представляет имена tabledef(s) и/или querydef, указанной в ClassWizard. Вместо этого можно указать другие сведения в `lpszSQL` параметра.  
  
 Все передаваемые **откройте** создает окончательной строки SQL для запроса (в этой строке может содержаться SQL **ГДЕ** и **ORDERBY** добавляемый в конец предложения `lpszSQL` вы строка переданный), а затем выполняет запрос. Можно проверить сконструированный строку путем вызова `GetSQL` после вызова **откройте**.  
  
 Элементами данных полей класса набора записей привязанные к столбцам выбранных данных. Если все записи, первая запись становится текущей записи.  
  
 Если требуется задать параметры для набора записей, таких как фильтр или сортировку, установите `m_strSort` или **m_strFilter** после создания объекта набора записей, но перед вызовом **откройте**. Если требуется для обновления записей в наборе записей после набор записей открыт, вызовите **Requery**.  
  
 При вызове метода **откройте** на динамического или набора записей типа, или если источник данных ссылается на инструкцию SQL или tabledef, который представляет подключенной таблицы, не могут использовать **dbOpenTable** для типа Аргумент; в противном случае MFC вызывает исключение. Чтобы определить, представляет ли объект tabledef подключенной таблицы, создайте [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) и вызовите его [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) функции-члена.  
  
 Используйте **dbSeeChanges** флаг предназначается для перехвата изменений, внесенных другим пользователем или в другую программу на компьютере, при изменении или удалении этой же записи. Например, если два пользователя начать редактирование той же записи, первый пользователь, вызовите **обновление** успешного выполнения функции-члена. Когда **обновление** вызывается второй учетной записи пользователя, `CDaoException` возникает исключение. Аналогично Если второй пользователь пытается обратиться к **удалить** для удаления записи, который уже был изменен пользователем первого `CDaoException` происходит.  
  
 Как правило если пользователь получает это `CDaoException` при обновлении, код должен обновить содержимое полей и получить измененные значения. Если исключение возникает в процессе удаления, код может отображать новые данные записей пользователю и сообщение, указывающее, что данные недавно изменились. На этом этапе код может запросить подтверждение, что по-прежнему пользователю необходимо удалить запись.  
  
> [!TIP]
>  Используйте параметр прокруткой только вперед ( **dbForwardOnly**) для повышения производительности, когда приложение выполняет один проход по набору записей, открытые из источника данных ODBC.  
  
 Дополнительные сведения см. в разделе «Метод OpenRecordset» в справке DAO.  
  
##  <a name="requery"></a>CDaoRecordset::Requery  
 Вызовите эту функцию-член для перестроения (Обновить) набор записей.  
  
```  
virtual void Requery();
```  
  
### <a name="remarks"></a>Примечания  
 Если все записи, первая запись становится текущей записи.  
  
 Чтобы набора записей для отражения, добавления и удаления, вы или другие пользователи, осуществляющие к источнику данных, необходимо перестроить набора записей путем вызова **Requery**. Если динамический набор записей, он автоматически отражает обновлений, которые вы или другие пользователи для его существующих записей (но не дополнения). Если набор записей является моментальным снимком, необходимо вызвать **Requery** для отражения изменений, с другими пользователями, а также добавления и удаления.  
  
 Для подмножества или моментального снимка, вызовите **Requery** любое время, необходимо перестроить набора записей, используя значения параметров. Установить новый фильтровать или сортировать, задав [m_strFilter](#m_strfilter) и [m_strSort](#m_strsort) перед вызовом **Requery**. Установить новые параметры, назначив новые значения членов данных параметра перед вызовом **Requery**.  
  
 Если произошел сбой попытки повторного построения recordset, закрывается набора записей. Перед вызовом метода **Requery**, можно определить, является ли набор записей можно опросить путем вызова [CanRestart](#canrestart) функции-члена. `CanRestart`не может гарантировать **Requery** будет выполнена успешно.  
  
> [!CAUTION]
>  Вызовите **Requery** только после вызова **откройте**.  
  
> [!NOTE]
>  Вызов [Requery](#requery) изменяет DAO закладки.  
  
 Не удается вызвать **Requery** на динамического или набора записей статического типа, если вызов `CanRestart` возвращает 0, или использовать его в набор записей типа таблицы.  
  
 Если оба `IsBOF` и `IsEOF` возвращает ненулевое значение, после вызова метода **Requery**, запрос не вернул никаких записей и набор записей будет не содержат данных.  
  
 Дополнительные сведения см. в разделе «Повторного» справки DAO.  
  
##  <a name="seek"></a>CDaoRecordset::Seek  
 Вызовите эту функцию-член для обнаружения записи в объекте recordset индексированных тип таблицы, удовлетворяющей указанным критериям для текущего индекса и убедитесь, что запись текущей записи.  
  
```  
BOOL Seek(
    LPCTSTR lpszComparison,  
    COleVariant* pKey1,  
    COleVariant* pKey2 = NULL,  
    COleVariant* pKey3 = NULL);

 
BOOL Seek(
    LPCTSTR lpszComparison,  
    COleVariant* pKeyArray,  
    WORD nKeys);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszComparison`  
 Одно из следующих строковых выражений: «< «,»\<=», «=», «> =», или «>».  
  
 `pKey1`  
 Указатель на [COleVariant](../../mfc/reference/colevariant-class.md) , значение которого соответствует первое поле в индекс. Обязательно.  
  
 *pKey2*  
 Указатель на `COleVariant` , значение которого соответствует второго поля в индексе, если таковые имеются. По умолчанию используется значение **NULL**.  
  
 *pKey3*  
 Указатель на `COleVariant` , значение которого соответствует третье поле в индексе, если таковые имеются. По умолчанию используется значение **NULL**.  
  
 *pKeyArray*  
 Указатель на массив значений типа Variant. Размер массива соответствует числу полей в индексе.  
  
 *nKeys*  
 Целое число в зависимости от размера массива, то есть число полей в индексе.  
  
> [!NOTE]
>  Не следует указывать подстановочные знаки в ключах. Подстановочные знаки вызовет `Seek` для возврата без совпадающих записей.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если Обнаружены совпадающие записи, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте вторую версию (array) `Seek` обработка индексов четырех полей или более.  
  
 `Seek`включает индекс высокой производительности, поиска по записей типа таблицы. Необходимо установить текущий индекс путем вызова `SetCurrentIndex` перед вызовом `Seek`. Если индекс определяет неуникальные ключевое поле или поля, `Seek` находит первой записи, которая удовлетворяет критериям. Если индекс не задано, создается исключение.  
  
 Обратите внимание, что если вы не создаете набор записей ЮНИКОДА, `COleVariant` объекты должны быть явно объявлены ANSI. Это можно сделать с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** форма конструктора с `vtSrc` значение `VT_BSTRT` (ANSI) или с помощью **COleVariant** функция [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** с `vtSrc` значение `VT_BSTRT`.  
  
 При вызове `Seek`, передать один или несколько значений ключей и оператор сравнения ("< «,»\<=», «=», «> =», или «>»). `Seek`Ищет указанные ключевые поля и находит первой записи, которая соответствует критериям, заданным `lpszComparison` и `pKey1`. После нахождения `Seek` возвращает ненулевое значение и делает эту запись текущей. Если `Seek` не может найти совпадения, `Seek` возвращает ноль, а текущая запись не определена. При использовании DAO напрямую, необходимо явно проверить свойство NoMatch.  
  
 Если `lpszComparison` «=», «> =», или «>», `Seek` начинается с начала индекса. Если `lpszComparison` является «<» или «< =», `Seek` начинается в конце индекса и ищет в обратном направлении только при наличии индекса повторяющиеся записи в конце. В этом случае `Seek` начинается запись произвольный среди индекс повторяющиеся записи в конце индекса.  
  
 Существует не должен быть текущей записи при использовании `Seek`.  
  
 Чтобы найти запись типа динамического или набора записей типа моментального снимка, удовлетворяющего определенному условию, используйте операции поиска. Чтобы включить все записи, не только те, которые удовлетворяют определенному условию, использовать операции перемещения для перемещения по записям.  
  
 Не удается вызвать `Seek` на присоединенной таблице любого типа, так как вложенные таблицы должен быть открыт как динамического или записей типа снимка. Тем не менее при вызове метода `CDaoDatabase::Open` непосредственно открыть базу данных может устанавливаться ISAM, можно вызвать `Seek` на таблицах в этой базе данных, несмотря на то, что производительность может быть медленно.  
  
 Дополнительные сведения см. в разделе «Поиск Method» в справке DAO.  
  
##  <a name="setabsoluteposition"></a>CDaoRecordset::SetAbsolutePosition  
 Задает относительный номер текущей записи объекта набора записей.  
  
```  
void SetAbsolutePosition(long lPosition);
```  
  
### <a name="parameters"></a>Параметры  
 *lPosition*  
 Соответствует порядковой позиции текущей записи в наборе записей.  
  
### <a name="remarks"></a>Примечания  
 Вызов `SetAbsolutePosition` позволяет разместить указатель текущей записи к конкретной записи, по его порядковый номер позиции, добавляющий или набора записей типа. Можно также определить текущий номер записи, вызвав [GetAbsolutePosition](#getabsoluteposition).  
  
> [!NOTE]
>  Эта функция-член является допустимым только для динамического типа и записей типа снимка.  
  
 Значение свойства AbsolutePosition базового объекта DAO (с нуля); значение, равное 0 относится к первой записи в наборе записей. Установка значения больше, чем число записей заполненных причины MFC для создания исключения. Можно определить количество заполненных записей в наборе записей, вызвав `GetRecordCount` функции-члена.  
  
 При удалении текущей записи, значение свойства AbsolutePosition не определен и MFC вызывает исключение, если на него ссылаться. Новые записи добавляются в конец последовательности.  
  
> [!NOTE]
>  Это свойство не предназначено для использования в качестве символов-заместителей номер записи. Закладки по-прежнему рекомендуемый способ сохранения и возврат к заданной позиции и единственный способ размещения текущей записи для всех типов объектов набора записей, которые поддерживают закладки. В частности позицию данной записи изменяется при удалении записи перед ее. Нет никакой гарантии, что данная запись будет иметь же абсолютное положение, если повторно набора записей создается снова, потому что порядок отдельных записей в наборе записей не обязательно, если он создается с помощью инструкции SQL с помощью  **ORDERBY** предложения.  
  
 Дополнительные сведения см. в разделе «Свойство AbsolutePosition» в справке DAO.  
  
##  <a name="setbookmark"></a>CDaoRecordset::SetBookmark  
 Вызовите эту функцию-член для размещения набора записей в записи, содержащей указанную закладку.  
  
```  
void SetBookmark(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>Параметры  
 `varBookmark`  
 Объект [COleVariant](../../mfc/reference/colevariant-class.md) объект, содержащий значение для определенной записи.  
  
### <a name="remarks"></a>Примечания  
 При создании или открытии объекта набора записей, каждый ее записи уже имеет уникальный закладки. Закладки для текущей записи можно получить, вызвав `GetBookmark` и сохранение значение `COleVariant` объекта. Возможность позже вернуться к этой записи путем вызова `SetBookmark` с помощью сохраненного закладок.  
  
> [!NOTE]
>  Вызов [Requery](#requery) изменяет DAO закладки.  
  
 Обратите внимание, что если вы не создаете набор записей ЮНИКОДА, `COleVariant` объекта должны быть явно объявлены ANSI. Это можно сделать с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** форма конструктора с `vtSrc` значение `VT_BSTRT` (ANSI) или с помощью **COleVariant** функция [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** с `vtSrc` значение `VT_BSTRT`.  
  
 Дополнительные сведения см. в разделах «Свойства закладки» и Bookmarkable свойство» в справке DAO.  
  
##  <a name="setcachesize"></a>CDaoRecordset::SetCacheSize  
 Вызовите эту функцию-член, чтобы задать число записей для кэширования.  
  
```  
void SetCacheSize(long lSize);
```  
  
### <a name="parameters"></a>Параметры  
 `lSize`  
 Указывает количество записей. Обычно значение — 100. Значение 0 отключает кэширование. Параметр должен быть от 5 до 1200 записей. Значительный объем памяти, может использовать кэш.  
  
### <a name="remarks"></a>Примечания  
 Кэш представляет пробел в локальной памяти, которая содержит данные, самое последнее полученное от сервера, в том случае, если данные будет запрошена во время выполнения приложения. Кэширование данных повышает производительность приложения, получающий данные с удаленного сервера через объекты типа динамического набора записей. При запросе данных базы данных Microsoft Jet сначала проверяет кэш для запрошенных данных вместо их извлечения из на сервер, который занимает больше времени. Данные, которые получены из источника данных ODBC не сохраняется в кэше.  
  
 Любой источник данных ODBC, например подключенной таблицы могут иметь локального кэша. Чтобы создать кэш, открывает объект набора записей из удаленного источника данных, вызов `SetCacheSize` и `SetCacheStart` функции-члены, а затем вызовите `FillCache` функции-члена или шаг по записям с помощью одной из операций перемещения. `lSize` Параметр `SetCacheSize` функция-член может основываться на число записей, приложение может работать с за один раз. Например, если вы используете набор записей как источник данных для отображения на экране, можно передать `SetCacheSize` `lSize` параметра равным 20 для отображения 20 записей за один раз.  
  
 Дополнительные сведения см. в разделе «CacheSize CacheStart свойства» в справке DAO.  
  
##  <a name="setcachestart"></a>CDaoRecordset::SetCacheStart  
 Вызовите эту функцию-член для указания закладки первой записи в наборе записей для кэширования.  
  
```  
void SetCacheStart(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>Параметры  
 `varBookmark`  
 Объект [COleVariant](../../mfc/reference/colevariant-class.md) , указывающий закладки первой записи в наборе записей для кэширования.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать значение закладки для всех записей `varBookmark` параметр `SetCacheStart` функции-члена. Сделать запись, необходимо запустить с текущей записью кэша, установить закладку для этой записи с помощью [SetBookmark](#setbookmark)и передать значение закладки в качестве параметра для `SetCacheStart` функции-члена.  
  
 Базы данных Microsoft Jet запрашивает записей в пределах диапазона кэша из кэша, а он запрашивает записи за пределами диапазона кэша с сервера.  
  
 Записей, полученных из кэша не отражают изменения, сделанные параллельно с источником данных другими пользователями.  
  
 Чтобы принудительно обновить кэшированные данные, необходимо передать `lSize` параметр `SetCacheSize` как 0, вызов `SetCacheSize` снова с размером кэша вы первоначально запрошенный, а затем вызвать `FillCache` функции-члена.  
  
 Обратите внимание, что если вы не создаете набор записей ЮНИКОДА, `COleVariant` объекта должны быть явно объявлены ANSI. Это можно сделать с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** форма конструктора с `vtSrc` значение `VT_BSTRT` (ANSI) или с помощью **COleVariant** функция [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** с `vtSrc` значение `VT_BSTRT`.  
  
 Дополнительные сведения см. в разделе CacheSize, CacheStart свойства» в справке DAO.  
  
##  <a name="setcurrentindex"></a>CDaoRecordset::SetCurrentIndex  
 Вызовите эту функцию-член для задания индекса recordset табличного типа.  
  
```  
void SetCurrentIndex(LPCTSTR lpszIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszIndex`  
 Указатель, содержащая имя индекса, чтобы задать.  
  
### <a name="remarks"></a>Примечания  
 Записи в базовых таблицах не хранятся в любом порядке. Индекс параметра меняет порядок записей, возвращаемых из базы данных, но не влияет на порядок, в котором хранятся записи. Указанный индекс должен быть уже определен. При попытке использовать объект индекса, который не существует, или если индекс не указано, при вызове [Seek](#seek), MFC вызывает исключение.  
  
 Можно создать новый индекс для таблицы путем вызова [CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) и Добавление нового индекса в коллекции индексов базовой tabledef путем вызова [CDaoTableDef::Append](../../mfc/reference/cdaotabledef-class.md#append), и затем открыть набор записей.  
  
 Записей, возвращаемых recordset табличного типа может упорядочиваться только индексы, определенные для базовых tabledef. Чтобы отсортировать записи в ином порядке, можно открыть динамического или набора записей типа моментальных снимков с помощью SQL **ORDERBY** предложение хранятся в [CDaoRecordset::m_strSort](#m_strsort).  
  
 Дополнительные сведения см. раздел «Объект индекса» и «текущий индекс» в справке DAO определение.  
  
##  <a name="setfielddirty"></a>CDaoRecordset::SetFieldDirty  
 Вызовите эту функцию-член для пометки элемента данных поля в наборе записей, как измененные или как без изменений.  
  
```  
void SetFieldDirty(
    void* pv,  
    BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 Содержит адрес элемента данных поля в наборе записей или **NULL**. Если **NULL**, помечаются все члены данных полей в наборе записей. (C++ **NULL** не является таким же, как значение Null в терминологии связанных баз данных, что означает «предложений having значение отсутствует».)  
  
 `bDirty`  
 **Значение TRUE,** должен быть помечен как «грязным» (измененного) элемента данных поля. В противном случае **FALSE** должен быть помечен как «чистые» (без изменений) элемента данных поля.  
  
### <a name="remarks"></a>Примечания  
 Пометка поля как неизмененные гарантирует, что поле не изменяется.  
  
 Метки framework изменить поля элементов данных, чтобы убедиться, что они будут записаны на запись в источнике данных с помощью механизма обмена (DFX) полями записей DAO. Как правило, изменение значения поля устанавливает для поля «грязных» автоматически, поэтому редко нужно вызывать `SetFieldDirty` самостоятельно, но иногда может потребоваться убедитесь, что столбцы будут будут явно обновлены или вставлены независимо от того, какое значение поля данных член. Механизм DFX также используются использование **PSEUDONULL**. Дополнительные сведения см. в разделе [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 Если не используется механизм двойной буферизации, изменив значение поля не задает автоматически поле как "грязные". В этом случае будет необходимо явно задать поле как "грязные". Флаг, содержащихся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) управляет эту проверку автоматического поля.  
  
> [!NOTE]
>  Вызовите эту функцию-член, только после вызова [изменить](#edit) или [AddNew](#addnew).  
  
 С помощью **NULL** для первый аргумент функции, применяемые ко всем функция **outputColumn** поля не **param** поля в `CDaoFieldExchange`. Например вызов  
  
 [!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]  
  
 установит только **outputColumn** поля **NULL**; **param** полей не затрагиваются.  
  
 Для работы с **param**, необходимо указать фактический адрес отдельные **param** требуется для работы, такие как:  
  
 [!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]  
  
 Это означает, что нельзя задать все **param** поля **NULL**, как и с **outputColumn** поля.  
  
 `SetFieldDirty`реализуется с помощью `DoFieldExchange`.  
  
##  <a name="setfieldnull"></a>CDaoRecordset::SetFieldNull  
 Вызовите эту функцию-член для пометки элемента данных поля в наборе записей, как Null (в частности, имеющая значение не) или как отличных от Null.  
  
```  
void SetFieldNull(
    void* pv,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 Содержит адрес элемента данных поля в наборе записей или **NULL**. Если **NULL**, помечаются все члены данных полей в наборе записей. (C++ **NULL** не является таким же, как значение Null в терминологии связанных баз данных, что означает «предложений having значение отсутствует».)  
  
 `bNull`  
 Ненулевое значение, если элемента данных поля является помечен как имеющий значение (Null). В противном случае значение 0, если было отмечено как ненулевой элемента данных поля.  
  
### <a name="remarks"></a>Примечания  
 `SetFieldNull`используется для полей, привязанных к `DoFieldExchange` механизм.  
  
 При добавлении новой записи в набор записей, все поля элементов данных изначально присваивается значение Null и помечен как «грязным» (измененного). При извлечении записи из источника данных, ее столбцы уже имеют значения либо равны Null. Если это неприемлемо сделать поле значение Null, [CDaoException](../../mfc/reference/cdaoexception-class.md) возникает исключение.  
  
 При использовании механизма двойной буферизации, например, при желании специально для назначения поля текущей записи как не имеющий значения, вызывает `SetFieldNull` с `bNull` значение **TRUE** пометка его как Null. Если поле ранее было помечено как Null, и теперь требуется ему присваивается значение, просто установите его новым значением. Необходимо снять флаг Null с `SetFieldNull`. Чтобы определить, разрешено ли поле иметь значение Null, вызовите [IsFieldNullable](#isfieldnullable).  
  
 Если вы не используете механизм двойной буферизации, изменив значение поля не задает автоматически поле как "грязные" и отличных от Null. В частности необходимо задать поля «грязных» и отличных от Null. Флаг, содержащихся в [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) управляет эту проверку автоматического поля.  
  
 Использование использует механизм DFX **PSEUDONULL**. Дополнительные сведения см. в разделе [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
> [!NOTE]
>  Вызовите эту функцию-член, только после вызова [изменить](#edit) или [AddNew](#addnew).  
  
 С помощью **NULL** первый аргумент функции будут относиться только к функции **outputColumn** поля не **param** поля в `CDaoFieldExchange`. Например вызов  
  
 [!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]  
  
 установит только **outputColumn** поля **NULL**; **param** полей не затрагиваются.  
  
##  <a name="setfieldvalue"></a>CDaoRecordset::SetFieldValue  
 Вызовите эту функцию-член для задания значения поля, по порядковому номеру или путем изменения значения строки.  
  
```  
virtual void SetFieldValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);

 
virtual void SetFieldValue(
    int nIndex,  
    const COleVariant& varValue);

 
void SetFieldValue(
    LPCTSTR lpszName,  
    LPCTSTR lpszValue);

 
void SetFieldValue(
    int nIndex,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку, содержащую имя поля.  
  
 `varValue`  
 Ссылку на [COleVariant](../../mfc/reference/colevariant-class.md) объект, содержащий значение поля.  
  
 `nIndex`  
 Целое число, представляющее порядковый номер поля в коллекции полей набора записей (начиная с нуля).  
  
 `lpszValue`  
 Указатель на строку, содержащую значение поля.  
  
### <a name="remarks"></a>Примечания  
 Используйте `SetFieldValue` и [GetFieldValue](#getfieldvalue) динамически привязывать поля во время выполнения, а не статически привязки столбцов с помощью [DoFieldExchange](#dofieldexchange) механизм.  
  
 Обратите внимание, что если не создается набор записей Юникод, либо необходимо использовать, один из видов `SetFieldValue` , который не содержит `COleVariant` параметра, или `COleVariant` объекта должны быть явно объявлены ANSI. Это можно сделать с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** форма конструктора с `vtSrc` значение `VT_BSTRT` (ANSI) или с помощью **COleVariant** функция [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** с `vtSrc` значение `VT_BSTRT`.  
  
 Дополнительные сведения см. в разделах «Поле объект» и «Значение свойства» в справке DAO.  
  
##  <a name="setfieldvaluenull"></a>CDaoRecordset::SetFieldValueNull  
 Вызовите эту функцию-член поля присваивается значение Null.  
  
```  
void SetFieldValueNull(int nIndex);  
void SetFieldValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс поля в наборе записей, для поиска по индексу (с нуля).  
  
 `lpszName`  
 Имя поля в наборе записей для поиска по имени.  
  
### <a name="remarks"></a>Примечания  
 C++ **NULL** не обязательно является Null, означающее, в терминологии связанных баз данных, «предложений having значение отсутствует».  
  
 Дополнительные сведения см. в разделах «Поле объект» и «Значение свойства» в справке DAO.  
  
##  <a name="setlockingmode"></a>CDaoRecordset::SetLockingMode  
 Вызовите эту функцию-член для задания типа блокировки для набора записей.  
  
```  
void SetLockingMode(BOOL bPessimistic);
```  
  
### <a name="parameters"></a>Параметры  
 *bPessimistic*  
 Флаг, указывающий тип блокировки.  
  
### <a name="remarks"></a>Примечания  
 Когда Пессимистическая блокировка действует, содержащего запись, вы изменяете страниц заблокирован сразу после вызова **изменить** функции-члена. Страница не заблокирован при вызове **обновление** или **закрыть** функции-члена или любой из операций поиска или перемещения.  
  
 Если оптимистическая блокировка действует, содержащий запись страниц блокируется, только в том случае, пока запись обновляется с **обновление** функции-члена.  
  
 Страница заблокирована, другой пользователь не может изменить записей на одной странице. При вызове метода `SetLockingMode` и передать ненулевое значение и другой пользователь уже заблокирован страницы, создается исключение при вызове **изменить**. Другие пользователи могут считывать данные из блокировку страниц.  
  
 При вызове метода `SetLockingMode` имеет значение 0 и более поздние версии вызова **обновление** пока страницы заблокировано другим пользователем, возникает исключение. Чтобы просмотреть изменения, внесенные в записи другим пользователем (и изменения потеряны), вызовите `SetBookmark` функция-член со значением закладки текущей записи.  
  
 При работе с источниками данных ODBC, режим блокировки всегда является оптимистическим.  
  
##  <a name="setparamvalue"></a>CDaoRecordset::SetParamValue  
 Вызовите эту функцию-член для задания значения параметра в наборе записей во время выполнения.  
  
```  
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Числовая позиция параметра в коллекции параметров querydef.  
  
 `var`  
 Задаваемое значение; см. заметки.  
  
 `lpszName`  
 Имя параметра, значение которого требуется задать.  
  
### <a name="remarks"></a>Примечания  
 Параметр должна быть уже установлена как часть строки SQL набора записей. Параметр доступен по имени или по его позиции индекса в коллекции.  
  
 Укажите значение, которое задается как `COleVariant` объект. Сведения о задании нужное значение и тип в вашей `COleVariant` см. в разделе класса [COleVariant](../../mfc/reference/colevariant-class.md). Обратите внимание, что если вы не создаете набор записей ЮНИКОДА, `COleVariant` объекта должны быть явно объявлены ANSI. Это можно сделать с помощью [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** форма конструктора с `vtSrc` значение `VT_BSTRT` (ANSI) или с помощью **COleVariant** функция [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** с `vtSrc` значение `VT_BSTRT`.  
  
##  <a name="setparamvaluenull"></a>CDaoRecordset::SetParamValueNull  
 Вызовите эту функцию-член для параметра значение Null.  
  
```  
void SetParamValueNull(int nIndex);  
void SetParamValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс поля в наборе записей, для поиска по индексу (с нуля).  
  
 `lpszName`  
 Имя поля в наборе записей для поиска по имени.  
  
### <a name="remarks"></a>Примечания  
 C++ **NULL** не обязательно является Null, означающее, в терминологии связанных баз данных, «предложений having значение отсутствует».  
  
##  <a name="setpercentposition"></a>CDaoRecordset::SetPercentPosition  
 Вызовите эту функцию-член для задания значения, что изменения Приблизительное расположение текущей записи в объекте recordset, основанные на процентах записей в наборе записей.  
  
```  
void SetPercentPosition(float fPosition);
```  
  
### <a name="parameters"></a>Параметры  
 *fPosition*  
 Число от 0 до 100.  
  
### <a name="remarks"></a>Примечания  
 При работе с динамического или набора записей типа снимка, заполнить набор записей, перемещая последней записи, перед вызовом метода `SetPercentPosition`. При вызове метода `SetPercentPosition` до полного заполнения набора записей, перемещение указывается относительно количество записей, доступ к, обозначенный значение [GetRecordCount](#getrecordcount). Вы можно перейти к последней записи путем вызова `MoveLast`.  
  
 При вызове метода `SetPercentPosition`, становится текущей записи приблизительное позиции, соответствующий этому значению.  
  
> [!NOTE]
>  Вызов `SetPercentPosition` Перемещение текущей записи к конкретной записи в наборе записей не рекомендуется. Вызовите [SetBookmark](#setbookmark) вместо этого функция-член.  
  
 Дополнительные сведения см. в разделе «Свойство PercentPosition» в справке DAO.  
  
##  <a name="update"></a>CDaoRecordset::Update  
 Это функция-член вызывается после вызова `AddNew` или **изменить** функции-члена.  
  
```  
virtual void Update();
```  
  
### <a name="remarks"></a>Примечания  
 Этот вызов необходим для завершения `AddNew` или **изменить** операции.  
  
 Оба `AddNew` и **изменить** Подготовка буфера редактирования, в котором размещена добавленных или измененных данных для сохранения в источнике данных. **Обновление** сохраняет данные. Обновляются только поля, помеченные или обнаружены изменения.  
  
 Если источник данных поддерживает транзакции, то сможете **обновление** вызова (и соответствующим `AddNew` или **изменить** вызова) частью транзакции.  
  
> [!CAUTION]
>  При вызове метода **обновление** без предварительного вызова `AddNew` или **изменить**, **обновление** вызывает `CDaoException`. При вызове метода `AddNew` или **изменить**, необходимо вызвать **обновление** перед вызовом метода [MoveNext](#movenext) или закрыть соединение с источником данных или набора записей. В противном случае изменения будут утеряны и без уведомления.  
  
 Когда объекта набора записей pessimistically заблокирован в многопользовательской среде, записи остаются заблокированными с момента **изменить** используется до завершения обновления. Если набор записей оптимистически заблокирован, запись заблокирован и сравнивается с предварительно измененной записи непосредственно перед обновлением данных в базе данных. Если запись была изменена с момента вызова **изменить**, **обновление** завершается с ошибкой и MFC вызывает исключение. Можно изменить режим блокировки с `SetLockingMode`.  
  
> [!NOTE]
>  О форматах внешней базы данных, таких как ODBC и устанавливаемый ISAM всегда используется оптимистическая блокировка.  
  
 Дополнительные сведения см. в разделах «Метод AddNew», «CancelUpdate Method», «Метод Delete», «Свойство LastModified», «Метод обновления» и «EditMode свойство» в справке DAO.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)   
 [Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)   
 [Класс CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)
