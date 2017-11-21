---
title: "/Zc:threadSafeInit (потокобезопасной локальной статичной инициализации) | Документы Microsoft"
ms.custom: 
ms.date: 12/13/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- threadSafeInit
- /Zc:threadSafeInit
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- threadSafeInit
- Thread-safe Local Static Initialization
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: a0fc4b34-2cf0-45a7-a642-b8afc4ca19f2
caps.latest.revision: "1"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3e1476369a798228361b89fdef12c94624ca4a70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/Zc:threadSafeInit (потокобезопасной локальной статичной инициализации)  
`/Zc:threadSafeInit` Компилятора указывает компилятору для инициализации статических локальных (область видимости функции) переменных потокобезопасным способом, устраняя необходимость в синхронизации вручную. Только инициализация является потокобезопасной. Использование и изменение статических локальных переменных в нескольких потоках необходимо по-прежнему выполнять синхронизацию вручную. Этот параметр доступен, начиная с Visual Studio 2015. По умолчанию Visual Studio включает этот параметр.  
  
## <a name="syntax"></a>Синтаксис  
  
`/Zc:threadSafeInit`[`-`]  
  
## <a name="remarks"></a>Примечания  
  
В C ++ 11 standard переменных области видимости блока со статическим или длительности хранилища потока должен быть нулями перед любой другой инициализация выполняется. Инициализация происходит, когда элемент управления сначала проходит через объявления переменной. Если исключение создается во время инициализации, переменная считается не инициализирована и инициализации повторена к следующему элементу управления время проходит через объявление. Если элемент управления входит объявление параллельно с инициализации блоки параллельного выполнения во время выполнения инициализации. Если элемент управления повторно входит в объявлении рекурсивно во время инициализации, поведение не определено. По умолчанию Visual Studio, начиная с Visual Studio 2015 реализует это стандартное поведение. Это поведение может быть явно указано, задав `/Zc:threadSafeInit` параметр компилятора.  
  
Код, реализованный в библиотеке времени выполнения универсальной C (UCRT) использует поточно ориентированного инициализации статических локальных переменных. Чтобы избежать создания зависимости UCRT или сохранить поведение не потокобезопасной инициализации версий Visual Studio до Visual Studio 2015, используйте `/Zc:threadSafeInit-` параметр. Если известно, что поток уровня безопасности не требуется, используйте этот параметр для создания кода немного меньше, чтобы повысить вокруг объявления статической локальной переменной.  
  
Статические локальные переменные поточно ориентированного внутренним образом используют локальное хранилище потока (TLS) чтобы обеспечить эффективное выполнение, если статический уже инициализирован. Реализация этой функции, зависит от функции поддержки операционной системы Windows в Windows Vista и более поздних операционных системах. Windows XP, Windows Server 2003 и более старых операционных систем нет такая поддержка, они не получают более эффективно использовать имеющиеся. Эти операционные системы также иметь нижний предел на число разделов TLS, которые могут быть загружены. Превышение TLS предел раздел может вызвать сбой. Если это проблема в коде, особенно в код, который должен выполняться в старых операционных системах, используйте `/Zc:threadSafeInit-` отключение код инициализации потокобезопасной.  
  
Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).
2.  Из **конфигурации** раскрывающееся меню, выберите **все конфигурации**.
3.  Выберите **свойства конфигурации**, **C/C++**, **командной строки** страницу свойств.
4.  Изменить **Дополнительные параметры** включив `/Zc:threadSafeInit` или `/Zc:threadSafeInit-` и выберите **ОК**.

## <a name="see-also"></a>См. также  
[Параметры компилятора](../../build/reference/compiler-options.md)  
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)  
[/Zc (соответствие)](../../build/reference/zc-conformance.md)  