---
title: "/ DISASM | Документы Microsoft"
ms.date: 1/17/2018
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /disasm
dev_langs:
- C++
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d448b92c3436f3d2875bd8d9b8e0af6a7149e065
ms.sourcegitcommit: ff9bf140b6874bc08718674c07312ecb5f996463
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="disasm"></a>/DISASM

Печать Дизассемблирование разделов кода в выводе DUMPBIN.

## <a name="syntax"></a>Синтаксис

> **/DISASM**{**:**\[**BYTES**|**NOBYTES**]}  

### <a name="arguments"></a>Аргументы

**BYTES**  
Содержится в байтах инструкция вместе с интерпретируемых коды операций и аргументы вывода Дизассемблированный код. Этот параметр используется по умолчанию.

**NOBYTES**  
Не включает инструкции байты в выходных данных Дизассемблированный код.

## <a name="remarks"></a>Примечания

**/DISASM** параметр отображает Дизассемблирование разделов кода в файле. Он использует символы отладки, если они присутствуют в файле.

**/ DISASM** следует использовать только в машинном коде, не управляемых образов. Средство эквивалент для управляемого кода — [ILDASM](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Только [/Headers](../../build/reference/headers.md) параметр программы DUMPBIN доступна для использования на файлы, созданные [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)  
