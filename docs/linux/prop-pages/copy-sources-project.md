---
title: "Свойства копирования источников проекта (Linux C++) | Документы Майкрософт"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 586244da6cc8c0a682146caf3ea75bdf72b5824e
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="copy-sources-project-properties-linux-c"></a>Свойства копирования источников проекта (Linux C++)

Свойства, заданные на этой странице свойств, применяются ко всем файлам в проекте, за исключением тех, свойства уровня файла которых уже заданы.

Свойство. | Описание:
--- | ---
Источники для копирования | Задает источники для копирования в удаленную систему. Изменение этого списка может сдвинуть или иным способом повлиять на структуру каталогов, в которые файлы будут копироваться на удаленной системе.
Копирование источников | Определяет, требуется ли копировать источники в удаленную систему.
Дополнительные источники для копирования | Задает дополнительные источники для копирования в удаленную систему. При необходимости можно указать список в виде пар сопоставлений локальной и удаленной версии со следующим синтаксисом: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2, где локальный файл можно скопировать в указанное удаленное расположение в удаленной системе.
