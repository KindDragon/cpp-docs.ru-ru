---
title: "Определения функций в C| Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function declarators
- function definitions
- declaring functions, about function declarations
- declaring functions, declarators
- functions [C], parameters
- declarators, functions
- function parameters, function definitions
- function body
- declaring functions, variables
ms.assetid: ebab23c8-6eb8-46f3-b21d-570cd8457a80
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a58adfefc5e2b3b5085a44c38dd392d3369421c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="c-function-definitions"></a>Определения функций в C
Определение функции задает имя функции, типы и число ожидаемых параметров, а также тип значений, возвращаемый функцией. Определение функции также содержит тело функции с объявлениями ее локальных переменных и операторы, которые определяют действия, выполняемые функцией.  
  
## <a name="syntax"></a>Синтаксис  
 *translation-unit*:  
 *external-declaration*  
  
 *translation-unit external-declaration*  
  
 *external-declaration*: /\* Допускается только в области видимости файла (внешней) \*/  
 *function-definition*  
  
 `declaration`  
  
 *function-definition*: /\*Здесь декларатор является декларатором функции \*/  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* относится только к системам Microsoft */  
  
 Параметры прототипа:  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *declaration-list*:  
 *declaration*  
  
 *declaration-list declaration*  
  
 `declarator`:  
 *pointer* opt*direct-declarator*  
  
 *direct-declarator*: /\* Декларатор функции \*/  
 *direct-declarator*  **(**  *parameter-type-list*  **)** /* Декларатор нового стиля \*/  
  
 *direct-declarator* **(** *identifier-list* opt**)** /* Декларатор устаревшего стиля \*/  
  
 Для списка параметров в определении используется следующий синтаксис:  
  
 *parameter-type-list*: /\* Список параметров \*/  
 *parameter-list*  
  
 *parameter-list* **, ...**  
  
 *parameter-list*:  
 *parameter-declaration*  
  
 *parameter-list*  **,**  *parameter-declaration*  
  
 *parameter-declaration*:  
 *declaration-specifiers declarator*  
  
 *declaration-specifiers abstract-declarator* opt  
  
 В определении функции устаревшего стиле для списка параметров используется следующий синтаксис:  
  
 *identifier-list*: /\* Используется в определениях и объявлениях функций устаревшего стиля \*/  
 *identifier*  
  
 *identifier-list* **,**  *identifier*  
  
 Синтаксис тела функции:  
  
 *compound-statement*: /\* Текст функции \*/  
 **{**  `declaration`-*list* opt*statement-list* opt**}**  
  
 Изменять объявления функций могут только описатели класса хранения `extern` и **static**. Спецификатор `extern` означает, что на функцию можно ссылаться из других файлов; то есть, имя функции экспортируется в компоновщик. Описатель **static** означает, что на функцию невозможно ссылаться из других файлов. Имя такой функции не экспортируется компоновщиком. Если в определении функции класс хранения не указан, принимается класс `extern`. В любом случае функция всегда видна от точки определения до конца файла.  
  
 Сочетание необязательного описателя *declaration-specifiers* и обязательного `declarator` определяет тип возвращаемого значения и имя функции. Декларатор `declarator` представляет собой сочетание идентификатора, задающего имя функции, и круглых скобок после имени функции. Необязательный нетерминальный компонент *attribute-seq* используется только для систем Microsoft и описан в статье [Атрибуты функций](../c-language/function-attributes.md).  
  
 *direct-declarator* (в синтаксисе `declarator`) указывает имя определяемой функции и идентификаторы для ее параметров. Если *direct-declarator* содержит список *parameter-type-list*, в нем определяются типы всех параметров. Такой декларатор также является прототипом функции для ее последующих вызовов.  
  
 Элемент `declaration` в списке *declaration-list* в определении функции не может содержать описателей *storage-class-specifier*, кроме **register**. Описатель *type-specifier* в синтаксисе *declaration-specifiers* можно опустить только в случае, если для типа `int` указан класс хранения **register**.  
  
 *compound-statement* представляет собой тело функции, где размещаются объявления локальных переменных, ссылки на внешние объявленные элементы и операторы.  
  
 Компоненты определения функции подробно рассматриваются в статьях [Атрибуты функций](../c-language/function-attributes.md), [Класс хранения](../c-language/storage-class.md), [Тип возвращаемого значения](../c-language/return-type.md), [Параметры](../c-language/parameters.md) и [Текст функции](../c-language/function-body.md).  
  
## <a name="see-also"></a>См. также  
 [Функции](../c-language/functions-c.md)