---
title: "CFile-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFile
- AFX/CFile
- AFX/CFile::CFile
- AFX/CFile::Abort
- AFX/CFile::Close
- AFX/CFile::Duplicate
- AFX/CFile::Flush
- AFX/CFile::GetFileName
- AFX/CFile::GetFilePath
- AFX/CFile::GetFileTitle
- AFX/CFile::GetLength
- AFX/CFile::GetPosition
- AFX/CFile::GetStatus
- AFX/CFile::LockRange
- AFX/CFile::Open
- AFX/CFile::Read
- AFX/CFile::Remove
- AFX/CFile::Rename
- AFX/CFile::Seek
- AFX/CFile::SeekToBegin
- AFX/CFile::SeekToEnd
- AFX/CFile::SetFilePath
- AFX/CFile::SetLength
- AFX/CFile::SetStatus
- AFX/CFile::UnlockRange
- AFX/CFile::Write
- AFX/CFile::hFileNull
- AFX/CFile::m_hFile
- AFX/CFile::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CFile [MFC], CFile
- CFile [MFC], Abort
- CFile [MFC], Close
- CFile [MFC], Duplicate
- CFile [MFC], Flush
- CFile [MFC], GetFileName
- CFile [MFC], GetFilePath
- CFile [MFC], GetFileTitle
- CFile [MFC], GetLength
- CFile [MFC], GetPosition
- CFile [MFC], GetStatus
- CFile [MFC], LockRange
- CFile [MFC], Open
- CFile [MFC], Read
- CFile [MFC], Remove
- CFile [MFC], Rename
- CFile [MFC], Seek
- CFile [MFC], SeekToBegin
- CFile [MFC], SeekToEnd
- CFile [MFC], SetFilePath
- CFile [MFC], SetLength
- CFile [MFC], SetStatus
- CFile [MFC], UnlockRange
- CFile [MFC], Write
- CFile [MFC], hFileNull
- CFile [MFC], m_hFile
- CFile [MFC], m_pTM
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f7a2b0e1dd95b460d6b6007e79378bc69f1b4ce
ms.sourcegitcommit: 2aeb507a426fc7881ea59115b1d5139c0a30ba91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2018
---
# <a name="cfile-class"></a>CFile-класс
Базовый класс для файловых классов Microsoft Foundation Class.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFile : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFile::CFile](#cfile)|Создает `CFile` объекта из дескриптора путь или файл.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFile::Abort](#abort)|Закрывает файл, игнорируя все предупреждения и ошибки.|  
|[CFile::Close](#close)|Файл был закрыт и удаляет объект.|  
|[CFile::Duplicate](#duplicate)|Создает дубликат объекта на основе этого файла.|  
|[CFile::Flush](#flush)|Очищает все еще записываемые данные.|  
|[CFile::GetFileName](#getfilename)|Извлекает имя выбранного файла.|  
|[CFile::GetFilePath](#getfilepath)|Извлекает полный путь к выбранному файлу.|  
|[CFile::GetFileTitle](#getfiletitle)|Извлекает название выбранного файла.|  
|[CFile::GetLength](#getlength)|Получает длину файла.|  
|[CFile::GetPosition](#getposition)|Извлекает текущий указатель файла.|  
|[CFile::GetStatus](#getstatus)|Получает сведения о состоянии открыть файл или в статической версии, получает состояние указанного файла (статические виртуальная функция).|  
|[CFile::LockRange](#lockrange)|Блокировки диапазона байтов в файле.|  
|[CFile::Open](#open)|Безопасно открывает файл с возможностью тестирования ошибки.|  
|[CFile::Read](#read)|Чтение (без буферизации) данных из файла в текущее положение в файле.|  
|[CFile::Remove](#remove)|Удаляет указанный файл (статическую функцию).|  
|[CFile::Rename](#rename)|Переименовывает указанный файл (статическую функцию).|  
|[CFile::Seek](#seek)|Помещает текущего указателя файла.|  
|[CFile::SeekToBegin](#seektobegin)|Устанавливает текущий указатель файла в начале файла.|  
|[CFile::SeekToEnd](#seektoend)|Устанавливает текущий указатель файла в конце файла.|  
|[CFile::SetFilePath](#setfilepath)|Задает полный путь к выбранному файлу.|  
|[CFile::SetLength](#setlength)|Изменяет размер файла.|  
|[CFile::SetStatus](#setstatus)|Задает состояние указанного файла (статические виртуальная функция).|  
|[CFile::UnlockRange](#unlockrange)|Снимает блокировку диапазона байтов в файле.|  
|[CFile::Write](#write)|Данные (без буферизации) операции записи файла в текущее положение в файле.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFile::operator ДЕСКРИПТОРА](#operator_handle)|Дескриптор `CFile` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFile::hFileNull](#hfilenull)|Определяет, если `CFile` объект имеет допустимый дескриптор.|  
|[CFile::m_hFile](#m_hfile)|Обычно содержит дескриптор файла операционной системы.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CFile::m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект.|  
  
## <a name="remarks"></a>Примечания  
 Он непосредственно выполняет функции ввода вывода без буферизации, двоичная диска и косвенно поддерживает текстовые файлы и файлы памяти через его производных классов. `CFile`работает в сочетании с `CArchive` класс для поддержки сериализации объектов Microsoft Foundation Class.  
  
 Иерархические связи между этот класс и его производные классы позволяет программе работать на всех файловых объектов через полиморфного `CFile` интерфейса. Например, файл памяти ведет себя как файл на диске.  
  
 Используйте `CFile` и его производные классы для общего назначения дискового ввода-вывода. Используйте `ofstream` или другие классы iostream Microsoft для форматированный текст, отправляемый в файл на диске.  
  
 Как правило, автоматически при открытии файла на диске `CFile` Создание и уничтожение закрытых на. Статические функции-члены позволяют запрашивать состояние файла, не открывая его.  
  
 Дополнительные сведения об использовании `CFile`, см. в статьях [файлы в MFC](../../mfc/files-in-mfc.md) и [обработка файлов](../../c-runtime-library/file-handling.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="abort"></a>CFile::Abort  
 Закрывает файл, связанный с этим объектом и он становится недоступным для чтения или записи.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Примечания  
 Если файл не закрыт перед удалением объекта, деструктор закрывает его для вас.  
  
 При обработке исключений, `CFile::Abort` отличается от `CFile::Close` в двух важных аспектах. Во-первых, **прервать** функция не вызывают исключение при сбое, поскольку сбои будут пропускаться **прервать**. Во-вторых, **прервать** не будет **ASSERT** Если файл не открыт или закрыт ранее.  
  
 Если вы использовали **новый** для выделения `CFile` объекта в куче, необходимо удалить его после закрытия файла. **Прервать** задает `m_hFile` для `CFile::hFileNull`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]  
  
##  <a name="cfile"></a>CFile::CFile  
 Создает и инициализирует объект `CFile`.  
  
```  
CFile();  
CFile(CAtlTransactionManager* pTM);  
CFile(HANDLE hFile);

 
CFile(
LPCTSTR lpszFileName,  
UINT nOpenFlags);

 
CFile(
LPCTSTR lpszFileName,  
UINT nOpenFlags,  
CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Параметры  
 `hFile`  
 Дескриптор файла, который будет присоединен к объекту `CFile`.  
  
 `lpszFileName`  
 Относительный или полный путь к файлу, который будет присоединен к объекту `CFile`.  
  
 `nOpenFlags`  
 Побитовое сочетание (ИЛИ) параметров доступа к указанному файлу. Возможные параметры см. в разделе "Заметки".  
  
 `pTM`  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="remarks"></a>Примечания  
 В следующих пяти таблицах представлены доступные параметры для `nOpenFlags`.  
  
 Выберите только один из следующих параметров режима доступа к файлу. Режим доступа к файлу по умолчанию — `CFile::modeRead`, т. е. только для чтения.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`CFile::modeRead`|Запрашивает доступ только для чтения.|  
|`CFile::modeWrite`|Запрашивает доступ только для записи.|  
|`CFile::modeReadWrite`|Запрашивает доступ для чтения и записи.|  
  
 Выберите один из следующих параметров режима символов.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`CFile::typeBinary`|Задает двоичный режим (используется только в производных классах).|  
|`CFile::typeText`|Задает текстовый режим со специальной обработкой пар перевода строки возврата каретки (используется только в производных классах).|  
|`CFile::typeUnicode`|Задает режим Юникода (используется только в производных классах). Текст записывается в файл в формате Юникод, если приложение использует конфигурацию Юникода. Данные BOM в файл не записываются.|  
  
 Выберите только один из следующих параметров режима общего доступа к файлу. Режим общего доступа к файлу по умолчанию — `CFile::shareExclusive`, т. е. эксклюзивный доступ.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`CFile::shareDenyNone`|Нет ограничений по общему доступу.|  
|`CFile::shareDenyRead`|Запрет доступа для чтения для всех других пользователей.|  
|`CFile::shareDenyWrite`|Запрет доступа для записи для всех других пользователей.|  
|`CFile::shareExclusive`|Запрет доступа для чтения и записи для всех других пользователей.|  
  
 Выберите первый или и первый, и второй из следующих параметров режима создания файла. Режим создания по умолчанию — `CFile::modeNoTruncate`, т. е. открывается существующий файл.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`CFile::modeCreate`|Создает новый файл, если файл не существует.; Если файл уже существует, [CFileException](../../mfc/reference/cfileexception-class.md) возникает.|  
|`CFile::modeNoTruncate`|Создает файл, если он не существует. В противном случае файл присоединяется к объекту `CFile`.|  
  
 Выберите соответствующие параметры кэширования файлов, описанные далее. По умолчанию система использует схему кэширования общего назначения, которая недоступна в виде параметра.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`CFile::osNoBuffer`|Система не использует промежуточный кэш для файла. Этот параметр отменяет использование следующих двух параметров.|  
|`CFile::osRandomAccess`|Файловый кэш оптимизирован для случайного доступа. Не используйте этот параметр вместе с параметром последовательного сканирования.|  
|`CFile::osSequentialScan`|Файловый кэш оптимизирован для последовательного доступа. Не используйте этот параметр вместе с параметром случайного доступа.|  
|`CFile::osWriteThrough`|Операции записи выполняются без задержки.|  
  
 Выберите следующий параметр безопасности, чтобы дескриптор файла не наследовался. По умолчанию любые новые дочерние процессы могут использовать дескриптор файла.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`CFile::modeNoInherit`|Запрещает дочерним процессам использовать дескриптор файла.|  
  
 Конструктор по умолчанию инициализирует члены, но не присоединяет файл к объекту `CFile`. После использования этого конструктора, используйте [CFile::Open](#open) метод, чтобы открыть файл и присоединить его к `CFile` объекта.  
  
 Конструктор с одним параметром инициализирует члены и присоединяет существующий файл к объекту `CFile`.  
  
 Конструктор с двумя параметрами инициализирует члены и пытается открыть указанный файл. Если конструктор успешно открывает заданный файл, он присоединяется к объекту `CFile`. В противном случае конструктор возвращает указатель на объект `CInvalidArgException`. Дополнительные сведения о программной обработке исключений см. в разделе [исключения](../../mfc/exception-handling-in-mfc.md).  
  
 Если объект `CFile` успешно открывает указанный файл, он закрывается автоматически при удалении объекта `CFile`. В противном случае необходимо явно закрыть файл, после отмены его присоединения к объекту `CFile`.  
  
### <a name="example"></a>Пример  
 В следующем коде показано использование `CFile`.  
  
 [!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]  
  
##  <a name="close"></a>CFile::Close  
 Закрывает файл, связанный с этим объектом и он становится недоступным для чтения или записи.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Если файл не закрыт перед удалением объекта, деструктор закрывает его для вас.  
  
 Если вы использовали **новый** для выделения `CFile` объекта в куче, необходимо удалить его после закрытия файла. **Закрыть** задает `m_hFile` для `CFile::hFileNull`.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CFile::CFile](#cfile).  
  
##  <a name="duplicate"></a>CFile::Duplicate  
 Создает дубликат `CFile` объекта для заданного файла.  
  
```  
virtual CFile* Duplicate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на копию `CFile` объекта.  
  
### <a name="remarks"></a>Примечания  
 Это эквивалентно функции времени выполнения C `_dup`.  
  
##  <a name="flush"></a>CFile::Flush  
 Вызывает запись данных, остающихся в буфере файла для записи в файл.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Примечания  
 Использование `Flush` не гарантирует списание `CArchive` буферов. Если вы используете архив, вызовите [CArchive::Flush](../../mfc/reference/carchive-class.md#flush) первой.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CFile::SetFilePath](#setfilepath).  
  
##  <a name="getfilename"></a>CFile::GetFileName  
 Вызовите эту функцию-член для извлечения имени указанного файла.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя файла  
  
### <a name="remarks"></a>Примечания  
 Например, при вызове `GetFileName` для создания сообщения для пользователя о файле `c:\windows\write\myfile.wri`, имя файла, `myfile.wri`, возвращается.  
  
 Чтобы вернуть полный путь к файлу, включая имя, вызовите [GetFilePath](#getfilepath). Для возврата заголовка файла ( `myfile`), вызовите [GetFileTitle](#getfiletitle).  
  
### <a name="example"></a>Пример  
 Этот фрагмент кода открывает системы. INI-файл в каталоге WINDOWS. Если найден, пример выдает имя и путь и title, как показано в разделе выходные данные:  
  
 [!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]  
  
##  <a name="getfilepath"></a>CFile::GetFilePath  
 Вызовите эту функцию-член для извлечения полного пути для указанного файла.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный путь указанного файла.  
  
### <a name="remarks"></a>Примечания  
 Например, при вызове `GetFilePath` для создания сообщения для пользователя о файле `c:\windows\write\myfile.wri`, путь к файлу `c:\windows\write\myfile.wri`, возвращается.  
  
 Чтобы вернуть только имя файла ( `myfile.wri`), вызовите [GetFileName](#getfilename). Для возврата заголовка файла ( `myfile`), вызовите [GetFileTitle](#getfiletitle).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetFileName](#getfilename).  
  
##  <a name="getfiletitle"></a>CFile::GetFileTitle  
 Вызовите эту функцию-член для извлечения заголовок файла (отображаемое имя) для файла.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Заголовок базового файла.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924) для извлечения заголовка файла. В случае успешного выполнения, метод возвращает строку, система будет использовать для отображения имени файла для пользователя. В противном случае метод вызывает [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) для получения имени файла (включая расширение файла) исходный файл. Таким образом расширение файла будет не всегда быть включен в строку заголовка возвращенных файлов. Дополнительные сведения см. в разделе [GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924) и [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) в Windows SDK.  
  
 Чтобы вернуть полный путь к файлу, включая имя, вызовите [GetFilePath](#getfilepath). Чтобы вернуть только имя файла, вызовите [GetFileName](#getfilename).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetFileName](#getfilename).  
  
##  <a name="getlength"></a>CFile::GetLength  
 Получает текущий логический длина файла в байтах.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]  
  
##  <a name="getposition"></a>CFile::GetPosition  
 Получает текущее значение указателя файла, который может использоваться в последующих вызовах `Seek`.  
  
```  
virtual ULONGLONG GetPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]  
  
##  <a name="getstatus"></a>CFile::GetStatus  
 Этот метод извлекает сведения о состоянии, связанные с данной `CFile` экземпляр объекта или данный путь к файлу.  
  
```  
BOOL GetStatus(CFileStatus& rStatus) const;  
  
static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,  
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `rStatus`  
 Ссылка в предоставленный пользователем **CFileStatus** структуру, которая будет получать сведения о состоянии. **CFileStatus** структура содержит следующие поля:  
  
- **CTime m_ctime** дату и время создания файла.  
  
- **CTime m_mtime** дату и время последнего изменения файла.  
  
- **CTime m_atime** дату и время последнего доступа к файлу для чтения.  
  
- **ULONGLONG m_size** логический размер файла в байтах, о котором сообщает команда DIR.  
  
- **БАЙТОВ m_attribute** байтов атрибут файла.  
  
- **char [_MAX_PATH] m_szFullName** абсолютное имя файла в наборе символов Windows.  
  
 `lpszFileName`  
 Строка в кодировке Windows, укажите путь к нужному файлу. Путь может быть относительным или абсолютным, или он может содержать сетевой путь.  
  
 `pTM`  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если сведения о состоянии для заданного файла, полученного успешно, в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Версия нестатических **GetStatus** получает сведения о состоянии Открытие файла, связанного с данной `CFile` объекта.  Статической версии **GetStatus** получает состояние файла из данный путь к файлу без фактически при открытии файла. Это полезно для тестирования права на доступ и существование файла.  
  
 **M_attribute** членом **CFileStatus** структуры ссылается на набор атрибутов файла. `CFile` Класс предоставляет **атрибута** тип перечисления, поэтому можно символически атрибутов файла:  
  
```  
enum Attribute {
    normal =    0x00,
    readOnly =  0x01,
    hidden =    0x02,
    system =    0x04,
    volume =    0x08,
    directory = 0x10,
    archive =   0x20
    };
```    
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#10](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]  
  
##  <a name="hfilenull"></a>CFile::hFileNull  
 Определяет наличие допустимого дескриптора файла для `CFile` объекта.  
  
```  
static AFX_DATA const HANDLE hFileNull;  
```  
  
### <a name="remarks"></a>Примечания  
 Эта константа используется для определения, если `CFile` объект имеет допустимого дескриптора файла.  
  
 В следующем примере демонстрируется этой операции:  
  
 [!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]  
  
##  <a name="lockrange"></a>CFile::LockRange  
 Блокировки диапазона байтов в открытом файле, исключения, если файл уже заблокирован.  
  
```  
virtual void LockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>Параметры  
 `dwPos`  
 Смещение в байтах от начала диапазона байтов для блокировки.  
  
 `dwCount`  
 Число байтов в диапазона для блокировки.  
  
### <a name="remarks"></a>Примечания  
 Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Можно заблокировать более одной области файла, но не перекрывающихся областей разрешены.  
  
 При снятии блокировки области, с помощью `UnlockRange` функция-член, диапазон байтов должно точно соответствовать ранее заблокированной области. `LockRange` Функция не объединение соседних регионов; Если заблокированные две области располагаются рядом, необходимо разблокировать каждой области отдельно.  
  
> [!NOTE]
>  Эта функция доступна не для `CMemFile`-производного класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="m_hfile"></a>CFile::m_hFile  
 Содержит дескриптор файла операционной системы для открытого файла.  
  
```  
HANDLE m_hFile;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_hFile`— это открытая переменная типа **UINT**. Он содержит `CFile::hFileNull` (пустой файл операционной системы независимый индикатора) Если не был назначен дескриптор.  
  
 Использование `m_hFile` не рекомендуется, поскольку значение элемента зависит от производного класса. `m_hFile`становится открытый член для удобства поддержки неполиморфных использование класса.  
  
##  <a name="m_ptm"></a>CFile::m_pTM  
 Указатель на `CAtlTransactionManager` объект.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="open"></a>CFile::Open  
 Перегружен. **Откройте** предназначен для использования со значением по умолчанию `CFile` конструктор.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Строка, представляющая путь к нужному файлу. Путь может быть относительным, абсолютное или сетевое имя (UNC).  
  
 `nOpenFlags`  
 Объект **UINT** , определяющий его для управления доступом и режимом доступа. Он указывает действие, выполняемое при открытии файла. Параметры могут быть объединены с помощью побитового или ( **&#124;** ) оператор. Разрешения на доступ к одной и одной общей папки параметр являются обязательными; **modeCreate** и **modeNoInherit** режимы являются необязательными. В разделе [CFile](#cfile) конструктор список параметров режима.  
  
 `pError`  
 Указатель на существующий объект исключения файл, который получит состояние сбоя операции.  
  
 `pTM`  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если открыть выполнена успешно; в противном случае — 0. `pError` Параметр имеет смысл только в том случае, если возвращается значение 0.  
  
### <a name="remarks"></a>Примечания  
 Две функции, которые образуют «безопасной» метод для открытия файла, где нормальный, ожидаемое условие сбоя.  
  
 Хотя `CFile` конструктор вызовет исключение в случае ошибки **откройте** вернет **FALSE** причин ошибок. **Откройте** по-прежнему можно инициализировать [CFileException](../../mfc/reference/cfileexception-class.md) объект для описания ошибки, однако. Если вы не предоставите `pError` параметра, или если передается **NULL** для `pError`, **откройте** вернет **FALSE** и создает исключение `CFileException`. Если передать указатель в существующий `CFileException`, и **откройте** возникает ошибка, функция будет заполнить его подробное описание этой ошибки. В ни один из вариантов будут **откройте** создаст исключение.  
  
 В следующей таблице описаны возможные результаты **откройте**.  
  
|`pError`|Произошла ошибка|Возвращаемое значение|Содержимое CFileException|  
|--------------|------------------------|------------------|----------------------------|  
|**NULL**|Нет|**ЗНАЧЕНИЕ TRUE**|Н/Д|  
|указатель на`CFileException`|Нет|**ЗНАЧЕНИЕ TRUE**|без изменений|  
|**NULL**|Да|**ЗНАЧЕНИЕ FALSE**|Н/Д|  
|указатель на`CFileException`|Да|**ЗНАЧЕНИЕ FALSE**|инициализирован для описания ошибки|  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]  
  
##  <a name="operator_handle"></a>CFile::operator ДЕСКРИПТОРА  
 Этот оператор используется для передачи дескриптора `CFile` объекта функции, например [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) и [GetFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724320) , ожидается, что `HANDLE`.  
  
```  
operator HANDLE() const;  
```  
  
##  <a name="read"></a>CFile::Read  
 Считывает данные в буфер из файла, связанного с `CFile` объекта.  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Указатель на буфер, предоставленный пользователем, получающего данные, считанные из файла.  
  
 `nCount`  
 Максимальное число байтов, считываемых из файла. Для файлов в текстовом режиме пары перевода строки возврата каретки, рассматриваются как одиночные символы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество байтов, переданных в буфер. Обратите внимание, что для всех `CFile` классы, возвращаемое значение может быть меньше, чем `nCount` если достигнут конец файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]  
  
 Другой пример в разделе [CFile::Open](#open).  
  
##  <a name="remove"></a>CFile::Remove  
 Эта статическая функция удаляет файл, указанный в пути.  
  
```  
static void PASCAL Remove(
    LPCTSTR lpszFileName, 
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Строка, представляющая путь к нужному файлу. Путь может быть относительным или абсолютным и может содержать имя сети.  
  
 `pTM`  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="remarks"></a>Примечания  
 Он не удалит каталог.  
  
 **Удалить** функция-член вызывает исключение, если подключенный файл открыт или если не удается удалить файл. Это эквивалентно команды DEL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]  
  
##  <a name="rename"></a>CFile::Rename  
 Эта статическая функция переименовывает указанный файл.  
  
```  
static void PASCAL Rename(
    LPCTSTR lpszOldName,  
    LPCTSTR lpszNewName,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszOldName`  
 Старый путь.  
  
 `lpszNewName`  
 Новый путь.  
  
 `pTM`  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="remarks"></a>Примечания  
 Каталоги нельзя переименовать. Это эквивалентно команды REN.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]  
  
##  <a name="seek"></a>CFile::Seek  
 Перемещает файловый указатель в открытом файле.  
  
```  
virtual ULONGLONG Seek(
LONGLONG lOff,  
UINT nFrom);
```  
  
### <a name="parameters"></a>Параметры  
 `lOff`  
 Число байтов для перемещения указателя файла. Положительные значения переместить указатель на файл в конце файла; отрицательные значения переместить указатель файла к началу файла.  
  
 `nFrom`  
 Позиция для поиска из. Возможные значения см.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Положение указателя файла, если метод выполнен успешно; в противном случае возвращаемое значение не определено и указатель на `CFileException` исключения.  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице перечислены возможные значения для `nFrom` параметра.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`CFile::begin`|Поиск с начала файла.|  
|`CFile::current`|Поиск от текущего расположения указателя файла.|  
|`CFile::end`|Поиск с конца файла.|  
  
 При открытии файла указатель файла помещается в 0 в начале файла.  
  
 Указатель файла можно задать на позицию за пределами файла. После этого размер файла не увеличивается до записи в файл.  
  
 Обработчик исключений для этого метода необходимо удалить объект исключения, после обработки исключения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]  
  
##  <a name="seektobegin"></a>CFile::SeekToBegin  
 Задает значение указателя файла в начало файла.  
  
```  
void SeekToBegin();
```  
  
### <a name="remarks"></a>Примечания  
 `SeekToBegin()` равно `Seek( 0L, CFile::begin )`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="seektoend"></a>CFile::SeekToEnd  
 Задает значение указателя файла в логический конец файла.  
  
```  
ULONGLONG SeekToEnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина файла в байтах.  
  
### <a name="remarks"></a>Примечания  
 `SeekToEnd()` равно `CFile::Seek( 0L, CFile::end )`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="setfilepath"></a>CFile::SetFilePath  
 Вызывайте эту функцию, чтобы указать путь к файлу; Например, если путь к файлу вариант недоступен, если [CFile](../../mfc/reference/cfile-class.md) объект создан, вызовите метод `SetFilePath` для ее предоставления.  
  
```  
virtual void SetFilePath(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszNewName`  
 Указатель на строку, указав новый путь.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
> `SetFilePath`Откройте файл или необходимо создать файл; он просто связывает `CFile` объекта с помощью имени пути, которые затем могут использоваться.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]  
  
##  <a name="setlength"></a>CFile::SetLength  
 Вызывайте эту функцию, чтобы изменить длину файла.  
  
```  
virtual void SetLength(ULONGLONG dwNewLen);
```  
  
### <a name="parameters"></a>Параметры  
 `dwNewLen`  
 Требуемая длина файла в байтах. Это значение может быть меньше или больше текущей длины файла. Файл будет расширенные или усечен соответствующим образом.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  С `CMemFile`, могут вызвать эту функцию `CMemoryException` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]  
  
##  <a name="setstatus"></a>CFile::SetStatus  
 Задает состояние файла, связанного с расположение этого файла.  
  
```  
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,  
    const CFileStatus& status,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Строка, представляющая путь к нужному файлу. Путь может быть относительным или абсолютным и может содержать имя сети.  
  
 *status*  
 Буфер, содержащий новые сведения о состоянии. Вызовите **GetStatus** функции-члена для prefill **CFileStatus** структура с текущими значениями и внесите необходимые изменения. Если значение равно 0, соответствующий элемент состояния не обновляется. В разделе [GetStatus](#getstatus) функции-члена описание **CFileStatus** структуры.  
  
 `pTM`  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="remarks"></a>Примечания  
 Чтобы задать время, измените **m_mtime** поле *состояние*.  
  
 Обратите внимание, что при вызове `SetStatus` при попытке изменить атрибуты файла и **m_mtime** структуры состояние файла не равно нулю, атрибуты также могут быть затронуты (изменение отметки времени может иметь побочные эффекты атрибуты). Если вы хотите изменить только атрибуты файла, сначала установите **m_mtime** член структуры состояния файла для нуля и затем вызвать `SetStatus`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]  
  
##  <a name="unlockrange"></a>CFile::UnlockRange  
 Снимает блокировку диапазона байтов в открытом файле.  
  
```  
virtual void UnlockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>Параметры  
 `dwPos`  
 Смещение в байтах от начала диапазона байтов для разблокирования.  
  
 `dwCount`  
 Число байтов в диапазоне разблокирование.  
  
### <a name="remarks"></a>Примечания  
 См. в описании [LockRange](#lockrange) функции-члена подробные сведения.  
  
> [!NOTE]
>  Эта функция доступна не для `CMemFile`-производного класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="write"></a>CFile::Write  
 Записывает данные из буфера в файл, связанный с `CFile` объекта.  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Параметры  
 `lpBuf`  
 Указатель на предоставленный пользователем буфер, содержащий данные для записи в файл.  
  
 `nCount`  
 Число байтов, переданных из буфера. Для файлов в текстовом режиме пары перевода строки возврата каретки, рассматриваются как одиночные символы.  
  
### <a name="remarks"></a>Примечания  
 **Запись** вызывает исключение в ответ на несколько условий, включая условия переполнения диска.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]  
  
 Кроме того, см. в примерах для [CFile::CFile](#cfile) и [CFile::Open](#open).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC ФУНКЦИЙ](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CStdioFile](../../mfc/reference/cstdiofile-class.md)   
 [Класс CMemFile](../../mfc/reference/cmemfile-class.md)
