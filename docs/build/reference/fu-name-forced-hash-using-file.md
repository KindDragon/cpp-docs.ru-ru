---
title: "-FU (имя принудительно #using файла) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
dev_langs:
- C++
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17b62859aaf0c9dc6b3313fbb726602b5b83a82c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fu-name-forced-using-file"></a>/FU (именование файла с принудительно используемым атрибутом #using)
Параметр компилятора, который можно использовать в качестве альтернативы передачи имени файла для [# директива using](../../preprocessor/hash-using-directive-cpp.md) в исходном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/FU file  
```  
  
## <a name="arguments"></a>Аргументы  
 `file`  
 Задает файл метаданных для ссылки в данной компиляции.  
  
## <a name="remarks"></a>Примечания  
 /FU коммутатора принимает только одно имя файла. Чтобы указать несколько файлов, используйте /FU с каждой из них.  
  
 Если вы используете [!INCLUDE[cppcli](../../build/reference/includes/cppcli_md.md)] и ссылаются метаданные, которые используются [дружественных сборок](../../dotnet/friend-assemblies-cpp.md) функции, нельзя использовать **/FU**. Должна ссылаться на метаданные в коде с помощью `#using`— вместе с `[as friend]` атрибута. Дружественные сборки не поддерживаются в [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]).  
  
 Сведения о создании сборки или модуля для общеязыковой среды выполнения (CLR) см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md). Дополнительные сведения о построении [!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)], в разделе [построение приложений и библиотек](../../cppcx/building-apps-and-libraries-c-cx.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++** папки.  
  
3.  Выберите **Дополнительно** страницу свойств.  
  
4.  Изменить **Force #using** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.  
  
## <a name="see-also"></a>См. также  
 [Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)