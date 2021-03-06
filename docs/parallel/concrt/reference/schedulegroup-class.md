---
title: "Класс ScheduleGroup | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ScheduleGroup
- CONCRT/concurrency::ScheduleGroup
- CONCRT/concurrency::ScheduleGroup::Id
- CONCRT/concurrency::ScheduleGroup::Reference
- CONCRT/concurrency::ScheduleGroup::Release
- CONCRT/concurrency::ScheduleGroup::ScheduleTask
dev_langs:
- C++
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2ba16ff0e17a0a6e8cc63cefaebe1e66a93af7c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="schedulegroup-class"></a>Класс ScheduleGroup
Представляет абстракцию для группы расписаний. Группы расписаний организуют набор связанных работ, которые выигрывают от планирования в непосредственной близости друг от друга: во времени (путем выполнения другой задачи в той же группе перед перемещением в другую группу) или в пространстве (путем выполнения нескольких элементов в той же группе в том же узле NUMA или физическом сокете).  
  
## <a name="syntax"></a>Синтаксис  
  
```
class ScheduleGroup;
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[~ Деструктор ScheduleGroup](#dtor)||  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Id](#id)|Возвращает идентификатор для группы расписаний, уникальный в пределах планировщик, к которому принадлежит группа.|  
|[Ссылки](#reference)|Увеличивает значение счетчика ссылок группы расписания.|  
|[Релиз](#release)|Уменьшает значение счетчика ссылок группы планировщика.|  
|[ScheduleTask](#scheduletask)|Назначает легкое задание в группы расписаний.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ScheduleGroup`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="id"></a> Id 

 Возвращает идентификатор для группы расписаний, уникальный в пределах планировщик, к которому принадлежит группа.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор для группы расписаний, уникальный в пределах планировщик, к которому принадлежит группа.  
  
##  <a name="operator_delete"></a> оператор delete 

 Объект `ScheduleGroup` объект уничтожается внутренне средой выполнения при выпуске всех внешних ссылок на него. Его невозможно удалить явно.  
  
```
void operator delete(
    void* _PObject);

void operator delete(
    void* _PObject,
    int,
 const char *,
    int);
```    
  
### <a name="parameters"></a>Параметры  
 `_PObject`  
 Указатель на объект для удаления.  
  
##  <a name="reference"></a> Ссылка 

 Увеличивает значение счетчика ссылок группы расписания.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число увеличенное ссылку.  
  
### <a name="remarks"></a>Примечания  
 Обычно используется для управления временем существования группы расписаний для композиции. Когда счетчик ссылок группы расписания становится равным нулю, группа расписаний удаляется средой выполнения. Группе расписаний, создаваемых с помощью [CurrentScheduler::CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) метод, или [Scheduler::CreateScheduleGroup](scheduler-class.md#createschedulegroup) метода начинается с одного счетчик ссылок.  
  
##  <a name="release"></a> выпуск 

 Уменьшает значение счетчика ссылок группы планировщика.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Счетчик ссылок уменьшается на единицу вновь.  
  
### <a name="remarks"></a>Примечания  
 Обычно используется для управления временем существования группы расписаний для композиции. Когда счетчик ссылок группы расписания становится равным нулю, группа расписаний удаляется средой выполнения. После вызова `Release` метод определенное количество раз, чтобы удалить Создание ссылки на число и любые дополнительные ссылки, размещенные с помощью `Reference` метод, не могут использовать группы расписания. Это приведет к неопределенному поведению.  
  
 Расписание группы связан с определенным экземпляром планировщика. Необходимо убедиться, что все ссылки на группы расписаний освобождаются до освобождения всех ссылок на планировщик, поскольку последние может привести к уничтожению планировщика. Это приведет к неопределенному поведению.  
  
##  <a name="dtor"></a> ~ScheduleGroup 

```
virtual ~ScheduleGroup();
```  
  
##  <a name="scheduletask"></a> ScheduleTask 

 Назначает легкое задание в группы расписаний.  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Proc`  
 Указатель на функцию, выполняемую для выполнения основной части задачи недоступно.  
  
 `_Data`  
 Указатель void к данным, которая будет передана в качестве параметра в теле задачи.  
  
### <a name="remarks"></a>Примечания  
 Вызов `ScheduleTask` метод неявно помещает значение счетчика ссылок группы расписания, которая удаляется средой выполнения в соответствующее время после выполнения задачи.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс CurrentScheduler](currentscheduler-class.md)   
 [Класс Scheduler](scheduler-class.md)   
 [Планировщик задач](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



