---
title: "Предупреждение средств компоновщика LNK4086 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4086
dev_langs:
- C++
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcd701401c798d7126be4f4239ee533b14d90652
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4086"></a>Предупреждение средств компоновщика LNK4086
точка входа «функция» не является __stdcall с 'number' байт аргументов; образ нельзя запустить  
  
 Точка входа для библиотеки DLL должна быть `__stdcall`. Либо повторите компиляцию функцию с [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) параметр или указать `__stdcall` или WINAPI при определении функции.