---
title: "Параллельные библиотеки шаблонов (PPL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Parallel Patterns Library (PPL)
ms.assetid: 40fd86b2-69fa-45e5-93d8-98a75636c242
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a13acdf07e2f6055326aea2097cb923baa153a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="parallel-patterns-library-ppl"></a>Библиотека параллельных шаблонов
Библиотека параллельных шаблонов (PPL) предоставляет императивную модель программирования, обеспечивающую масштабируемость и повышающую удобство разработки параллельных приложений. Библиотека PPL основана на компонентах планирования и управления ресурсами среды выполнения с параллелизмом. Она создает уровень абстракции между кодом приложения и базовым потоковым механизмом, предоставляя универсальные типобезопасные алгоритмы и контейнеры, работающие с данными параллельно. Кроме того, PPL позволяет разрабатывать приложения с возможностью масштабирования, предоставляя альтернативы состоянию с общим доступом.  
  
 PPL обеспечивает следующие возможности.  
  
- *Параллелизм задач*: механизм, работающий на основе Windows ThreadPool, для параллельного выполнения нескольких рабочих элементов (задач)  
  
- *Параллельные алгоритмы*: универсальные алгоритмы, работающий на основе среда выполнения с параллелизмом для работы с коллекциями данных в параллельном режиме  
  
- *Параллельные контейнеры и объекты*: универсальные типы контейнеров, предоставляющие безопасный одновременный доступ к своим элементам  
  
## <a name="example"></a>Пример  
 PPL предоставляет модель программирования, которая напоминает стандартной библиотеки C++. В следующем примере показаны различные возможности PPL. В нем последовательно и параллельно вычисляется несколько чисел Фибоначчи. Оба вычисления работают с [std::array](../../standard-library/array-class-stl.md) объекта. В этом примере в консоль также выводится время, необходимое на выполнение обоих вычислений.  
  
 Последовательный версия использует стандартную библиотеку C++ [std::for_each](../../standard-library/algorithm-functions.md#for_each) алгоритм для обхода массива и сохраняет результаты в [std::vector](../../standard-library/vector-class.md) объекта. Параллельная версия выполняет ту же задачу, но использует Алгоритм [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм и сохраняет результаты в [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) объекта. Класс `concurrent_vector` позволяет каждой итерации цикла одновременно добавлять элементы, не требуя синхронизации доступа на запись в контейнер.  
  
 Поскольку `parallel_for_each` действует одновременно, версия программы для параллельного вычисления, используемая в данном примере, должна выполнить сортировку объекта `concurrent_vector`, чтобы получить те же результаты, что и версия программы для последовательного вычисления.  
  
 Обратите внимание, что в примере используется упрощенный метод вычисления чисел Фибоначчи, однако этот метод показывает, как с помощью среды выполнения с параллелизмом можно повысить производительность системы при выполнении длинных вычислений.  
  
 [!code-cpp[concrt-parallel-fibonacci#1](../../parallel/concrt/codesnippet/cpp/parallel-patterns-library-ppl_1.cpp)]  
  
 В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.  
  
```Output  
serial time: 9250 ms  
parallel time: 5726 ms  
 
fib(24): 46368  
fib(26): 121393  
fib(41): 165580141  
fib(42): 267914296  
```  
  
 Все итерации цикла различаются по продолжительности. Производительность `parallel_for_each` ограничивается операцией, которая завершается последней. Следовательно, не стоит ожидать линейного повышения производительности системы в зависимости от версий, используемых в данном примере (для последовательных и параллельных вычислений).  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание:|  
|-----------|-----------------|  
|[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Описывает роль задач и групп задач в PPL.|  
|[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)|Описывает способы использования алгоритмов параллельной обработки, таких как `parallel_for` и `parallel_for_each`.|  
|[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)|Описывает различные параллельные контейнеры и объекты, предоставляемые PPL.|  
|[Отмена в библиотеке параллельных шаблонов](cancellation-in-the-ppl.md)|Объясняет, как отменить работу, выполняемую алгоритмом параллельной обработки.|  
|[Среда выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime.md)|Описывает среду выполнения с параллелизмом, которая упрощает процесс параллельного программирования и содержит ссылки на соответствующие разделы.|

