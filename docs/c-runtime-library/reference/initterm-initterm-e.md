---
title: "_initterm, _initterm_e | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _initterm_e
- _initterm
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _initterm_e
- initterm
- _initterm
- initterm_e
dev_langs:
- C++
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e27e165131b44181f1ee12f11477892fc144c267
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="initterm-initterme"></a>_initterm, _initterm_e
Внутренние методы, которые выполняют обход таблицы указателей функций и инициализируют их.  
  
 Первый указатель представляет собой начальное расположение в таблице, а второй указатель — конечное расположение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __cdecl _initterm(  
   PVFV *,  
   PVFV *  
);  
  
int __cdecl _initterm_e(  
   PVFV *,  
   PVFV *  
);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ненулевой код ошибки, если инициализация завершается неудачей и генерирует ошибку; 0 при отсутствии ошибок.  
  
## <a name="remarks"></a>Примечания  
 Эти методы вызываются только внутри системы во время инициализации программы C++. Не следует вызывать эти методы в программе.  
  
 Когда эти методы производят обход таблицы записей функций, они пропускают записи `NULL` и продолжают выполнение.  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)