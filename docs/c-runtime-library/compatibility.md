---
title: "Совместимость | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "совместимость"
  - "совместимость, библиотеки времени выполнения С"
  - "CRT - библиотека, совместимость"
ms.assetid: 346709cb-edda-4909-9a19-3d253eddb6b7
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Совместимость
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Универсальная библиотека времени выполнения C \(UCRT\) поддерживает большую часть стандартной библиотеки C, необходимой для соответствия стандарту C\+\+. Она реализует библиотеку C99 \(ISO\/IEC 9899:1999\) за исключением макросов универсального типа, определенных в \<tgmath.h\>, и строгой совместимости типов в \<complex.h\>. Библиотека UCRT также реализует большое подмножество библиотеки C POSIX.1 \(ISO\/IEC 9945\-1:1996, интерфейс прикладного программирования системы POSIX\), но не полностью соответствует какому\-либо стандарту POSIX.  Кроме того, UCRT реализует несколько функций и макросов Майкрософт, которые не входят в стандарт.  
  
 Функции, относящиеся к реализации Майкрософт Visual C\+\+, находятся в библиотеке vcruntime.  Многие из этих функций предназначены только для внутреннего использования, и их невозможно вызвать с помощью пользовательского кода. Некоторые предназначены для использования при отладке и проверке совместимости реализаций.  
  
 Стандартная библиотека C\+\+ резервирует имена, которые начинаются с символа подчеркивания в глобальном пространстве имен, в реализации. Так как функции POSIX находятся в глобальном пространстве имен, но не являются частью стандартной библиотеки среды выполнения C, реализации Майкрософт этих функций содержат символ подчеркивания в начале. Для переносимости библиотека UCRT также поддерживает имена по умолчанию, но компилятор Visual C\+\+ выдает предупреждение об устаревании при компиляции кода, который использует их. Устаревшими считаются только имена POSIX по умолчанию, но не функции. Чтобы подавить предупреждение, задайте `_CRT_NONSTDC_NO_WARNINGS` перед включением каких\-либо заголовков в код, использующий исходные имена POSIX.  
  
 Про некоторые функции в стандартной библиотеке C известно, что имеется тенденция к их небезопасному использованию из\-за неправильно используемых параметров и непроверенных буферов. Эти функции часто являются источником проблем с безопасностью в коде. Майкрософт создала набор более безопасных версий этих функций, которые проверяют использование параметров и вызывают обработчик недопустимых параметров при обнаружении проблемы в ходе выполнения.  По умолчанию компилятор Visual C\+\+ выдает предупреждение об устаревании, когда используется функция, для которой имеется более безопасный вариант. При компиляции кода в C\+\+ можно задать для `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` значение 1, чтобы устранить большинство предупреждений. Перегрузки шаблонов используются для вызова более безопасных вариантов, сохраняя переносимость исходного кода. Чтобы подавить предупреждение, определите `_CRT_SECURE_NO_WARNINGS` перед тем, как включить какие\-либо заголовки в код, который использует эти функции. Для получения дополнительной информации см. [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
 За исключением указанного в документации по конкретным функциям библиотека UCRT совместима с Windows API.  Некоторые функции не поддерживаются в приложениях Магазина для Windows 8 или в универсальных приложениях Windows в Windows 10. Эти функции перечислены в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx), в которой перечислены функции, не поддерживающиеся [средой выполнения Windows](http://msdn.microsoft.com/ru-ru/9a1a18b8-9802-4ec5-b9de-0d2dfdf414e9).  
  
## Связанные статьи  
  
|Заголовок|Описание|  
|---------------|--------------|  
|[Приложения для Магазина Windows, среда выполнения Windows и среда выполнения C](../c-runtime-library/windows-store-apps-the-windows-runtime-and-the-c-run-time.md)|Описывает, когда процессы UCRT несовместимы с универсальными приложениями Windows или приложениями Магазина Windows.|  
|[Совместимость ANSI с C](../c-runtime-library/ansi-c-compliance.md)|Описывает именования, совместимые со стандартами, в UCRT.|  
|[UNIX](../Topic/UNIX.md)|Рекомендации по переносу программ в UNIX.|  
|[Платформы Windows \(CRT\)](../Topic/Windows%20Platforms%20\(CRT\).md)|Перечисление операционных систем, поддерживающих CRT.|  
|[Обратная совместимость](../c-runtime-library/backward-compatibility.md)|Описание сопоставлений старых имен CRT с новыми.|  
|[Особенности библиотеки CRT](../c-runtime-library/crt-library-features.md)|Общие сведения о файлах библиотеки CRT \(LIB\) и соответствующих параметрах компилятора.|