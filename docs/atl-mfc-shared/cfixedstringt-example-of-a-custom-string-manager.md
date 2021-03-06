---
title: "CFixedStringT: Пример пользовательского диспетчера строка | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7164d2313f5610d1d7e56f5449c81ea9e2282981
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT: Пример пользовательского диспетчера строки
Библиотека ATL реализует один пример диспетчера настраиваемой строки, используемых классом [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md), который называется **CFixedStringMgr**. `CFixedStringT`является производным от [CStringT](../atl-mfc-shared/reference/cstringt-class.md) и реализует строку, которая выделяет его символьных данных в рамках `CFixedStringT` самого объекта, при условии, что строки меньше, чем длина, заданная параметром **t_nChars** параметр шаблона `CFixedStringT`. Таким образом строка не обязательно кучи, если длина строки выходит за буфер фиксированного размера. Поскольку `CFixedStringT` не всегда используйте кучи для выделения его строковые данные, он не может использовать **CAtlStringMgr** его руководитель строки. Она использует диспетчер настраиваемой строки (**CFixedStringMgr**), реализующего [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) интерфейса. Этот интерфейс рассматривается в [реализация пользовательских строка Manager (Advanced метод)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md).  
  
 Конструктор для **CFixedStringMgr** принимает три параметра:  
  
-   **pData:** указатель фиксированного `CStringData` структуры для использования.  
  
-   **nChars:** максимальное количество символов `CStringData` структуру может содержать.  
  
-   **pMgr:** указатель `IAtlStringMgr` интерфейс «диспетчера резервного копирования строки».  
  
 Конструктор сохраняет значения `pData` и **pMgr** в своих переменных-членов, соответствующих (`m_pData` и **m_pMgr**). Затем она задает длину буфера равным нулю, доступных длину, равную максимальный размер буфера фиксированного и счетчик ссылок в значение -1. Значение счетчика ссылок указывает, блокируется буфера и использовать этот экземпляр **CFixedStringMgr** руководитель строки.  
  
 Как заблокированная, помеченное буфер не других `CStringT` экземпляров из хранение общих ссылки в буфер. Если другие `CStringT` экземпляров будет разрешено совместное использование буфера, возможно для буфера, содержащихся в `CFixedStringT` должны удаляться, а другие строки используется буфер.  
  
 **CFixedStringMgr** является полной реализацией `IAtlStringMgr` интерфейса. Реализация каждого метода обсуждаются отдельно.  
  
## <a name="implementation-of-cfixedstringmgrallocate"></a>Реализация CFixedStringMgr::Allocate  
 Реализация **CFixedStringMgr::Allocate** сначала проверяет, является ли запрошенный размер строки меньше или равно буфер фиксированного размера (хранятся в `m_pData` члена). Если буфер фиксированного достаточно большая, **CFixedStringMgr** блокирует буфер фиксированного с длиной, равной нулю. При условии, что длина строки не превысит размер буфера фиксированного, `CStringT` не придется повторно выделить буфер.  
  
 Если запрошенный размер строки больше, чем буфер фиксированного **CFixedStringMgr** пересылает запрос диспетчера резервного копирования строки. Диспетчер резервного копирования строка будет считаться выделить буфер из кучи. Однако перед возвратом этот буфер **CFixedStringMgr** блокировки буфера и заменяет указатель на указатель диспетчер буфера строку **CFixedStringMgr** объекта. Это гарантирует, что пытается повторно выделить или освободить буфер с `CStringT` приводит к вызову **CFixedStringMgr**.  
  
## <a name="implementation-of-cfixedstringmgrreallocate"></a>Реализация CFixedStringMgr::ReAllocate  
 Реализация **CFixedStringMgr::ReAllocate** очень похож на его реализацию **Allocate**.  
  
 Если размер запрашиваемого буфера меньше, чем буфер фиксированного буфер перебрасываются является предопределенной, выделение не выполняется. Тем не менее если буфер перебрасываются не буфер фиксированного, должен быть буфер, выделенный с помощью диспетчера резервного копирования. В этом случае диспетчера резервного копирования используется в перераспределении буфера.  
  
 Если буфер перебрасываются является предопределенной и новый размер буфера слишком велик для соответствия размерам буфер фиксированного **CFixedStringMgr** выделяет новый буфер с помощью диспетчера резервного копирования. Содержимое буфера фиксированного затем копируются в новый буфер.  
  
## <a name="implementation-of-cfixedstringmgrfree"></a>Реализация CFixedStringMgr::Free  
 Реализация **CFixedStringMgr::Free** шаблону как **Allocate** и `ReAllocate`. При освобождении буфер является предопределенной, метод устанавливает на буфер, заблокированные нулевой длины. Если при освобождении буфер был выделен с помощью диспетчера резервного копирования, **CFixedStringMgr** использует диспетчера резервного копирования, чтобы освободить ее.  
  
## <a name="implementation-of-cfixedstringmgrclone"></a>Реализация CFixedStringMgr::Clone  
 Реализация **CFixedStringMgr::Clone** всегда возвращает указатель на диспетчера резервного копирования, а не **CFixedStringMgr** сам. Это происходит потому, что каждый экземпляр **CFixedStringMgr** может быть связан только с одного экземпляра `CStringT`. Все прочие экземпляры `CStringT` предпринять попытку клонирования диспетчеру должны получить диспетчера резервного копирования вместо него. Это происходит потому диспетчера резервного копирования поддерживает общего доступа.  
  
## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>Реализация CFixedStringMgr::GetNilString  
 Реализация **CFixedStringMgr::GetNilString** Возвращает буфер фиксированного. Из-за каждого пользователя соответствие **CFixedStringMgr** и `CStringT`, заданного экземпляра `CStringT` никогда не используется более чем один буфер за раз. Таким образом в то же время не требуется нулевая строка и реальных строковый буфер.  
  
 Каждый раз, когда буфер фиксированного не используется, **CFixedStringMgr** гарантирует, что инициализируется с нулевой длиной. Это позволяет использовать в качестве нулевая строка. В качестве дополнительной `nAllocLength` членом буфер фиксированного всегда равно полный размер буфер фиксированного. Это означает, что `CStringT` может увеличиваться строку без вызова [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate), даже для пустой строки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** cstringt.h  
  
## <a name="see-also"></a>См. также  
 [Управление памятью с помощью CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)

