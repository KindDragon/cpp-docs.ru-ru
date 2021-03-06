---
title: "-LTCG (Создание кода во время компоновки) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
dev_langs:
- C++
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69e67755ce5015cdd63ad36625e71380a303d2d4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="ltcg-link-time-code-generation"></a>Параметр /LTCG (создание кода во время компоновки)
```  
/LTCG[:INCREMENTAL|:NOSTATUS|:STATUS|:OFF|:PGINSTRUMENT|:PGOPTIMIZE|:PGUPDATE]  
```  
  
## <a name="remarks"></a>Примечания  
 :INCREMENTAL (необязательный)  
 Указывает, что компоновщик применяет только всей программы оптимизации или ссылки во время создания кода (LTCG) в набор файлов, затронутых изменения, а не весь проект. По умолчанию этот флаг не установлен, если указан параметр/LTCG, и весь проект компонуется с помощью оптимизации всей программы.  
  
 : NOSTATUS &#124; : STATUS (необязательный)  
 Указывает, отображает ли компоновщик индикатор хода выполнения, показывающий, какой процент ссылку завершен. По умолчанию эти данные о состоянии не отображаются.  
  
 :OFF (необязательный)  
 Отключает создание кода во время компоновки. Это происходит так же, как когда параметр/LTCG не указан в командной строке.  
  
 :PGINSTRUMENT (необязательный)  
 Этот параметр устарел. Вместо этого используйте **/LTCG** и **/genprofile** или **/fastgenprofile** Чтобы создать инструментированную сборку для профильной оптимизации.  
  
 Данные, собранные из инструментированных запусков используется для создания оптимизированного образа. Дополнительные сведения см. в разделе [профильной оптимизации](../../build/reference/profile-guided-optimizations.md). Краткая форма этого параметра — / LTCG: PGI.  
  
 :PGOPTIMIZE (необязательный)  
 Этот параметр устарел. Вместо этого используйте **/LTCG** и **параметром/useprofile** для сборки оптимизированного образа. Дополнительные сведения см. в разделе [профильной оптимизации](../../build/reference/profile-guided-optimizations.md). Краткая форма этого параметра — LTCG: PGO.  
  
 :PGUPDATE (необязательный)  
 Этот параметр устарел. Вместо этого используйте **/LTCG** и **параметром/useprofile** для сборки оптимизированного образа. Дополнительные сведения см. в разделе [профильной оптимизации](../../build/reference/profile-guided-optimizations.md). Краткая форма этого параметра — /LTCG:PGU.  
  
 Параметр/LTCG предписывает компоновщику вызов компилятора и выполнение оптимизации всей программы. Вы можете также выполнить профильную оптимизацию. Дополнительные сведения см. в разделе [профильной оптимизации](../../build/reference/profile-guided-optimizations.md).  
  
 Со следующими исключениями вы не можете добавлять параметры компилятора в комбинацию PGO /LTCG и /USEPROFILE, которые не были указаны в предыдущей комбинации инициализации PGO параметров /LTCG и /GENPROFILE:  
  
-   [/BASE](../../build/reference/base-base-address.md)  
  
-   [/FIXED](../../build/reference/fixed-fixed-base-address.md)  
  
-   /LTCG  
  
-   [/MAP](../../build/reference/map-generate-mapfile.md)  
  
-   [/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)  
  
-   [/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)  
  
-   [/OUT](../../build/reference/out-output-file-name.md)  
  
-   [/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)  
  
-   [/PDB](../../build/reference/pdb-use-program-database.md)  
  
-   [/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)  
  
-   [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)  
  
-   [/VERBOSE](../../build/reference/verbose-print-progress-messages.md)  
  
 Любые параметры компоновщика, которые были заданы с параметрами /LTCG и /GENPROFILE для инициализации PGO, не должны быть указаны при сборке с помощью /LTCG и /USEPROFILE; они подразумеваются.  
  
 В остальной части раздела описывается параметр /LTCG в условиях создания кода во время компоновки.  
  
 / Параметр LTCG подразумевается с [/GL](../../build/reference/gl-whole-program-optimization.md).  
  
 Компоновщик вызывает создание кода во время компоновки, если он передается модуля, скомпилированного с помощью **/GL** или модуля MSIL (в разделе [.netmodule качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md)). Если не указать явно **/LTCG** при передаче **/GL** или модулей MSIL в компоновщик, в конечном итоге обнаружит это и перезапустит ссылку с помощью **/LTCG**. Явно укажите **/LTCG** при передаче **/GL** и модули MSIL в компоновщик для наивысшей построения производительности.  
  
 Для большей производительности используйте **/LTCG: ДОБАВОЧНОЕ**. Этот параметр указывает компоновщику повторно оптимизировать только набор файлов, затронутый изменениями в исходном файле, а не весь проект. Это может значительно сократить требуемое для компоновки время. Это не тот же параметр как инкрементную компоновку.  
  
 **/LTCG** невозможно использовать с [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md).  
  
 Когда **/LTCG** используется для связывания модули, скомпилированные с помощью [/Og](../../build/reference/og-global-optimizations.md), [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), или [/ox](../../build/reference/ox-full-optimization.md), выполняются следующие оптимизации:  
  
-   кроссмодульное встраивание;  
  
-   межпроцедурное распределение регистров (только 64-разрядные операционные системы);  
  
-   пользовательское соглашение об именовании (только x86)  
  
-   небольшое смещение TLS (только x86);  
  
-   двойное выравнивание стека (только x86);  
  
-   улучшенное устранение неоднозначности памяти (более подробные данные о конфликтах для глобальных переменных и входных параметров).  
  
> [!NOTE]
>  Компоновщик определяет, какие оптимизации использовались для компиляции каждой функции, и применяет те же оптимизации во время компоновки.  
  
 С помощью **/LTCG** и **/Ogt** вызывает оптимизацию двойного выравнивания.  
  
 Если **/LTCG** и **/Ogs** указаны, двойное выравнивание не выполняется. Если большая часть функций в приложении скомпилированы для скорости, некоторые функции, скомпилированные для размера (например, с помощью [оптимизировать](../../preprocessor/optimize.md) pragma), компилятор двойное выравнивание функции, которые оптимизированы для размера, если они вызывают функции, которые требуют двойное выравнивание.  
  
 Если компилятор может определить все вызываемые функцией объекты, компилятор игнорирует модификаторы явного соглашения об именовании в функции и пытается оптимизировать соглашение о вызове функции:  
  
-   передает параметры в регистраторах;  
  
-   переупорядочивает параметры для выравнивания;  
  
-   удаляет неиспользуемые параметры.  
  
 При вызове функции через указатель на функцию, или при вызове функции вне модуля, скомпилированного с помощью **/GL**, компилятор не пытается оптимизировать соглашение о вызовах функции.  
  
> [!NOTE]
>  Если вы используете **/LTCG** и переопределяйте mainCRTStartup, приложение может иметь непредсказуемого поведения, связанного с пользовательским кодом, который выполняется перед инициализацией глобальные объекты.  Существует три способа решения этой проблемы: не переопределяйте mainCRTStartup, не компилируйте файл, который содержит mainCRTStartup, с помощью **/LTCG**, или инициализируйте глобальные переменные и объекты статически.  
  
## <a name="ltcg-and-msil-modules"></a>Модули /LTCG и MSIL  
 Модули, скомпилированные с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) и [/clr](../../build/reference/clr-common-language-runtime-compilation.md) , могут использоваться в качестве входных данных компоновщика, если указан параметр **/LTCG** .  
  
-   **/ Параметр LTCG** может принять машинные файлы объектов и файлами объектов, смешанного управляемого и машинного (скомпилированные с помощью **/CLR**). Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
-   / LTCG: PGI не принимает машинные модули, скомпилированные с помощью **/GL** и   **/CLR**  
  
#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. В разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Свойства конфигурации** .  
  
3.  Выберите страницу свойств **Общие** .  
  
4.  Измените свойство **Оптимизация всей программы** .  
  
 Вы можете также применить **/LTCG** к конкретным сборкам, выбрав **Сборка**, **Профильная оптимизация** в строке меню, или щелкнув один из параметров профильной оптимизации в контекстном меню проекта.  
  
#### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)