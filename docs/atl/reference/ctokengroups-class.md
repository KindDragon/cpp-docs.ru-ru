---
title: "Класс CTokenGroups | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
dev_langs:
- C++
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 41b93e1c0a2e55013e280023a7f47610d38ddc10
ms.lasthandoff: 02/24/2017

---
# <a name="ctokengroups-class"></a>Класс CTokenGroups
Этот класс является оболочкой для **TOKEN_GROUPS** структуры.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CTokenGroups
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTokenGroups::CTokenGroups](#ctokengroups)|Конструктор.|  
|[CTokenGroups:: ~ CTokenGroups](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTokenGroups::Add](#add)|Добавляет `CSid` или существующих **TOKEN_GROUPS** структуры `CTokenGroups` объекта.|  
|[CTokenGroups::Delete](#delete)|Удаляет `CSid` и связанных с ним атрибутов из `CTokenGroups` объекта.|  
|[CTokenGroups::DeleteAll](#deleteall)|Удаляет все `CSid` объектов и связанные с ними атрибуты из `CTokenGroups` объекта.|  
|[CTokenGroups::GetCount](#getcount)|Возвращает число `CSid` объектов и связанных с ними атрибутов, содержащихся в **CTokenGroups** объекта.|  
|[CTokenGroups::GetLength](#getlength)|Возвращает размер `CTokenGroups` объекта.|  
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|Извлекает указатель на **TOKEN_GROUPS** структуры.|  
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|Извлекает `CSid` объектов и атрибутов, принадлежащих `CTokenGroups` объекта.|  
|[CTokenGroups::LookupSid](#lookupsid)|Получает атрибуты, связанные с `CSid` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTokenGroups::operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|Приведение `CTokenGroups` объект в указатель на **TOKEN_GROUPS** структуры.|  
|[CTokenGroups::operator =](#operator_eq)|Оператор присвоения.|  
  
## <a name="remarks"></a>Примечания  
 [Маркер доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909) — это объект, который описывает контекст безопасности процесса или потока и выделяется для каждого пользователя, входившего в системе Windows NT или Windows 2000.  
  
 **CTokenGroups** класс является оболочкой для [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) структуру, содержащую сведения о идентификаторы безопасности (SID) группы в маркер доступа.  
  
 Введение в модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="add"></a>CTokenGroups::Add  
 Добавляет `CSid` или существующих **TOKEN_GROUPS** структуры `CTokenGroups` объекта.  
  
```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );  
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 Объект [CSid](../../atl/reference/csid-class.md) объекта.  
  
 `dwAttributes`  
 Атрибуты для связывания с `CSid` объекта.  
  
 *rTokenGroups*  
 Объект [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) структуры.  
  
### <a name="remarks"></a>Примечания  
 Эти методы позволяют добавить один или несколько `CSid` объектов и связанные с ними атрибуты для `CTokenGroups` объекта.  
  
##  <a name="ctokengroups"></a>CTokenGroups::CTokenGroups  
 Конструктор.  
  
```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );  
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `CTokenGroups` Объекта или [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) структуру для создания `CTokenGroups` объекта.  
  
### <a name="remarks"></a>Примечания  
 `CTokenGroups` Объекта при необходимости могут создаваться с помощью **TOKEN_GROUPS** структуры или ранее определенный `CTokenGroups` объекта.  
  
##  <a name="dtor"></a>CTokenGroups:: ~ CTokenGroups  
 Деструктор  
  
```
virtual ~CTokenGroups() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все выделенные ресурсы.  
  
##  <a name="delete"></a>CTokenGroups::Delete  
 Удаляет `CSid` и связанных с ним атрибутов из `CTokenGroups` объекта.  
  
```
bool Delete(const CSid& rSid) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md) объекта, для которого следует удалить идентификатор безопасности (SID) и атрибутов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если `CSid` удаляется, значение false в противном случае.  
  
##  <a name="deleteall"></a>CTokenGroups::DeleteAll  
 Удаляет все `CSid` объектов и связанные с ними атрибуты из `CTokenGroups` объекта.  
  
```
void DeleteAll() throw();
```  
  
##  <a name="getcount"></a>CTokenGroups::GetCount  
 Возвращает число `CSid` объектов, содержащихся в `CTokenGroups`.  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число [CSid](../../atl/reference/csid-class.md) объектов и связанные с ними атрибуты содержатся в `CTokenGroups` объекта.  
  
##  <a name="getlength"></a>CTokenGroups::GetLength  
 Возвращает размер **CTokenGroup** объекта.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает общий размер **CTokenGroup** объекта в байтах.  
  
##  <a name="getptoken_groups"></a>CTokenGroups::GetPTOKEN_GROUPS  
 Извлекает указатель на **TOKEN_GROUPS** структуры.  
  
```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Извлекает указатель на [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) структуры, принадлежащих `CTokenGroups` объекта маркера доступа.  
  
##  <a name="getsidsandattributes"></a>CTokenGroups::GetSidsAndAttributes  
 Извлекает `CSid` объекты и (необязательно) атрибутов, принадлежащих `CTokenGroups` объекта.  
  
```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSids`  
 Указатель на массив [CSid](../../atl/reference/csid-class.md) объектов.  
  
 `pAttributes`  
 Указатель на массив DWORD. Если этот параметр опущен или имеет значение NULL, атрибуты не будут получены.  
  
### <a name="remarks"></a>Примечания  
 Этот метод перечисляет все `CSid` объектов, содержащихся в `CTokenGroups` объекта и поместите их и (необязательно флаги атрибутов) в массив объектов.  
  
##  <a name="lookupsid"></a>CTokenGroups::LookupSid  
 Получает атрибуты, связанные с `CSid` объекта.  
  
```
bool LookupSid(  
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md) объекта.  
  
 `pdwAttributes`  
 Указатель на значение DWORD, который будет принимать `CSid` атрибута объекта. Если опущен или имеет значение NULL, не удалось получить атрибут.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если `CSid` найден, значение false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Установка `pdwAttributes` для NULL предоставляет способ подтверждения наличия `CSid` без обращения к атрибуту. Обратите внимание, что этот метод не должен использоваться для проверки прав доступа, как в среде Windows 2000 могут возникнуть неверные результаты. Приложения должны использовать вместо [CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) метод.  
  
##  <a name="operator_eq"></a>CTokenGroups::operator =  
 Оператор присвоения.  
  
```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);  
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `CTokenGroups` Объекта или [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) структуры для назначения `CTokenGroups` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CTokenGroups` объекта.  
  
##  <a name="operator_const_token_groups__star"></a>CTokenGroups::operator const TOKEN_GROUPS *  
 Приводит значение к указателю на **TOKEN_GROUPS** структуры.  
  
```  
operator const TOKEN_GROUPS *() const throw(...);
```  
  
### <a name="remarks"></a>Примечания  
 Приводит значение к указателю на [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) структуры.  
  
## <a name="see-also"></a>См. также  
 [Образец безопасности](../../visual-cpp-samples.md)   
 [Идентификатор CSid класса](../../atl/reference/csid-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
