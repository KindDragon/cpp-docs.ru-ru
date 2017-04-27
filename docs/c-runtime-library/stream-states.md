---
title: "Состояния потока | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- streams, states
ms.assetid: 5f28c968-f132-403f-968c-8417ff315e52
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: aba5e757172f4206beab22be9367ff3d42e6e0e1
ms.lasthandoff: 02/24/2017

---
# <a name="stream-states"></a>Состояния потока
Допустимые состояния и переходы состояний для потока показаны на следующем рисунке.  
  
 ![Поток](../c-runtime-library/media/stream.gif "поток")  
  
 Каждый из кругов обозначает устойчивое состояние. Каждая из линий задает переход, который может возникать в результате вызова функции, работающей в потоке. Пять групп функций могут вызвать переходы состояний.  
  
 Функции в первых трех группах объявлены в \<stdio.h>:  
  
-   Функции чтения байтов — [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fread](../c-runtime-library/reference/fread.md), [fscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getc](../c-runtime-library/reference/getc-getwc.md), [getchar](../c-runtime-library/reference/getc-getwc.md), [gets](../c-runtime-library/gets-getws.md), [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) и [ungetc](../c-runtime-library/reference/ungetc-ungetwc.md)  
  
-   Функции записи байтов — [fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputc](../c-runtime-library/reference/fputc-fputwc.md), [fputs](../c-runtime-library/reference/fputs-fputws.md), [fwrite](../c-runtime-library/reference/fwrite.md), [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [putc](../c-runtime-library/reference/putc-putwc.md), [putchar](../c-runtime-library/reference/putc-putwc.md), [puts](../c-runtime-library/reference/puts-putws.md), [vfprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md) и [vprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)  
  
-   Функции позиционирования — [fflush](../c-runtime-library/reference/fflush.md), [fseek](../c-runtime-library/reference/fseek-fseeki64.md), [fsetpos](../c-runtime-library/reference/fsetpos.md) и [rewind](../c-runtime-library/reference/rewind.md)  
  
 Функции в оставшихся двух группах объявлены в \<wchar.h>:  
  
-   Функции чтения расширенных символов — [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getwc](../c-runtime-library/reference/getc-getwc.md), [getwchar](../c-runtime-library/reference/getc-getwc.md), [ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md) и [wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)  
  
-   Функции записи расширенных символов — [fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputwc](../c-runtime-library/reference/fputc-fputwc.md), [fputws](../c-runtime-library/reference/fputs-fputws.md), [putwc](../c-runtime-library/reference/putc-putwc.md), [putwchar](../c-runtime-library/reference/fputc-fputwc.md), [vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md) и [wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md),  
  
 Схема состояний показывает, что между большинством операций записи и чтения необходимо вызывать одну из функций позиционирования:  
  
-   Невозможно вызвать функцию чтения, если последняя операция в потоке была операцией записи.  
  
-   Невозможно вызвать функцию записи, если последняя операция в потоке была операцией чтения, если только операция чтения не установила индикатор конца файла.  
  
 Наконец, схема состояний показывает, что операция позиционирования никогда не уменьшает число допустимых вызовов функций, которые могут следовать далее.  
  
## <a name="see-also"></a>См. также  
 [Файлы и потоки](../c-runtime-library/files-and-streams.md)