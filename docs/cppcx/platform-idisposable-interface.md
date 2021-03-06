---
title: "Интерфейс Platform::IDisposable | Документы Microsoft"
ms.custom: 
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
dev_langs:
- C++
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c9ff9deff5df9bb0e0b3bdc88a482aa8063bef3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="platformidisposable-interface"></a>Интерфейс Platform::IDisposable
Используется для освобождения неуправляемых ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public interface class IDisposable  
```  
  
## <a name="attributes"></a>Атрибуты  
 **GuidAttribute**("de0cbaea-8065-4a45-b196-c9d443f9bab3")  
  
 **VersionAttribute**(NTDDI_WIN8)  
  
### <a name="members"></a>Участники  
 Интерфейс IDisposable наследует от интерфейса IUnknown. Интерфейс IDisposable также имеет следующие типы членов.  
  
 **Методы**  
  
 Интерфейс IDisposable содержит следующие методы.  
  
|Метод|Описание:|  
|------------|-----------------|  
|Ликвидировать|Используется для освобождения неуправляемых ресурсов.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform