---
title: "Класс task_options (среда выполнения с параллелизмом) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ppltasks/concurrency::task_options
dev_langs:
- C++
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ad83e9e0a871ddc2d8f2c767cb0690da1e6f349
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="taskoptions-class-concurrency-runtime"></a>Класс task_options (среда выполнения с параллелизмом)
Представляет допустимые параметры для создания задачи  
  
## <a name="syntax"></a>Синтаксис  
  
```
class task_options;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор task_options::task_options (среда выполнения с параллелизмом)](#ctor)|Перегружен. Заданный по умолчанию список параметров создания задачи|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод task_options::get_cancellation_token (среда выполнения с параллелизмом)](#get_cancellation_token)|Возвращает токен отмены|  
|[Метод task_options::get_continuation_context (среда выполнения с параллелизмом)](#get_continuation_context)|Возвращает контекст продолжения|  
|[Метод task_options::get_scheduler (среда выполнения с параллелизмом)](#get_scheduler)|Возвращает планировщик|  
|[Метод task_options::has_cancellation_token (среда выполнения с параллелизмом)](#has_cancellation_token)|Показывает, был ли определен токен отмены пользователем|  
|[Метод task_options::has_scheduler (среда выполнения с параллелизмом)](#has_scheduler)|Показывает, был ли определен планировщик n пользователем|  
|[Метод task_options::set_cancellation_token (среда выполнения с параллелизмом)](#set_cancellation_token)|Задает токен в параметрах|  
|[Метод task_options::set_continuation_context (среда выполнения с параллелизмом)](#set_continuation_context)|Задает контекст данного продолжения в параметрах|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `task_options`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="get_cancellation_token">Метод task_options::get_cancellation_token (среда выполнения с параллелизмом)</a>  
 Возвращает токен отмены  
  
```
cancellation_token get_cancellation_token() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="get_continuation_context">Метод task_options::get_continuation_context (среда выполнения с параллелизмом)</a>  
 Возвращает контекст продолжения  
  
```
task_continuation_context get_continuation_context() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="get_scheduler">Метод task_options::get_scheduler (среда выполнения с параллелизмом)</a>  
 Возвращает планировщик  
  
```
scheduler_ptr get_scheduler() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="has_cancellation_token">Метод task_options::has_cancellation_token (среда выполнения с параллелизмом)</a>  
 Показывает, был ли определен токен отмены пользователем  
  
```
bool has_cancellation_token() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="has_scheduler">Метод task_options::has_scheduler (среда выполнения с параллелизмом)</a>  
 Показывает, был ли определен планировщик n пользователем  
  
```
bool has_scheduler() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="set_cancellation_token">Метод task_options::set_cancellation_token (среда выполнения с параллелизмом)</a>  
 Задает токен в параметрах  
  
```
void set_cancellation_token(cancellation_token _Token);
```  
  
### <a name="parameters"></a>Параметры  
 `_Token`  
  
##  <a name="set_continuation_context">Метод task_options::set_continuation_context (среда выполнения с параллелизмом)</a>  
 Задает контекст данного продолжения в параметрах  
  
```
void set_continuation_context(task_continuation_context _ContinuationContext);
```  
  
### <a name="parameters"></a>Параметры  
 `_ContinuationContext`  
  
##  <a name="ctor">Конструктор task_options::task_options (среда выполнения с параллелизмом)</a>  
 Заданный по умолчанию список параметров создания задачи  
  
```
task_options();

task_options(
    cancellation_token _Token);

task_options(
    task_continuation_context _ContinuationContext);

task_options(
    cancellation_token _Token,
    task_continuation_context _ContinuationContext);

template<typename _SchedType>
task_options(
    std::shared_ptr<_SchedType> _Scheduler);

task_options(
    scheduler_interface& _Scheduler);

task_options(
    scheduler_ptr _Scheduler);

task_options(
    const task_options& _TaskOptions);
```  
  
### <a name="parameters"></a>Параметры  
 `_SchedType`  
 `_Token`  
 `_ContinuationContext`  
 `_Scheduler`  
 `_TaskOptions`  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
