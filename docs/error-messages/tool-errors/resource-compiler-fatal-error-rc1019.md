---
title: "Неустранимая ошибка компилятора ресурсов RC1019 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1019
dev_langs:
- C++
helpviewer_keywords:
- RC1019
ms.assetid: 432fff44-04a9-4e13-91c6-870df6f0b4e4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 457e87d2d62b0960f89f1bd4454624a824d8ef61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1019"></a>Неустранимая ошибка компилятора ресурсов RC1019
Непредвиденная "#else"  
  
 `#else` Директива не отображается в `#if`, **#ifdef**, или **#ifndef** построения.  
  
 Убедитесь, что имеется `#if`, **#ifdef**, или **#ifndef** инструкции фактически перед этим оператором.