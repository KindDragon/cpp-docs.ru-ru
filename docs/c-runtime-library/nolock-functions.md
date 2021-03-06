---
title: "Функции _nolock | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- _nolock functions
- nolock functions
ms.assetid: 7d651d87-38d2-4303-9897-fdb5f7a3e899
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 250f12be8e1768b5e73636210753c95188d9229f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nolock-functions"></a>Функции _nolock
Эти функции не выполняют никаких блокировок. Они предназначены для пользователей, которым требуется максимальная производительность. Подробнее см. [Производительность многопоточных библиотек](../c-runtime-library/multithreaded-libraries-performance.md).  
  
 Используйте функции _nolock только в том случае, если программа действительно является однопоточной или если она устанавливает собственные блокировки.  
  
 [_fclose_nolock](../c-runtime-library/reference/fclose-nolock.md)  
  
 [_fflush_nolock](../c-runtime-library/reference/fflush-nolock.md)  
  
 [_fgetc_nolock, _fgetwc_nolock](../c-runtime-library/reference/fgetc-nolock-fgetwc-nolock.md)  
  
 [_fread_nolock](../c-runtime-library/reference/fread-nolock.md)  
  
 [_fseek_nolock, _fseeki64_nolock](../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md)  
  
 [_ftell_nolock, _ftelli64_nolock](../c-runtime-library/reference/ftell-nolock-ftelli64-nolock.md)  
  
 [_fwrite_nolock](../c-runtime-library/reference/fwrite-nolock.md)  
  
 [_getc_nolock, _getwc_nolock](../c-runtime-library/reference/getc-nolock-getwc-nolock.md)  
  
 [_getch_nolock, _getwch_nolock](../c-runtime-library/reference/getch-nolock-getwch-nolock.md)  
  
 [_getchar_nolock, _getwchar_nolock](../c-runtime-library/reference/getchar-nolock-getwchar-nolock.md)  
  
 [_getche_nolock, _getwche_nolock](../c-runtime-library/reference/getche-nolock-getwche-nolock.md)  
  
 [_getdcwd_nolock, _wgetdcwd_nolock](../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md)  
  
 [_putc_nolock, _putwc_nolock](../c-runtime-library/reference/putc-nolock-putwc-nolock.md)  
  
 [_putch_nolock, _putwch_nolock](../c-runtime-library/reference/putch-nolock-putwch-nolock.md)  
  
 [_putchar_nolock, _putwchar_nolock](../c-runtime-library/reference/putchar-nolock-putwchar-nolock.md)  
  
 [_ungetc_nolock, _ungetwc_nolock](../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md)  
  
 [_ungetch_nolock, _ungetwch_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)  
  
## <a name="see-also"></a>См. также  
 [Ввод и вывод](../c-runtime-library/input-and-output.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)