---
title: "noalias | Документы Microsoft"
ms.custom: 
ms.date: 02/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- noalias_cpp
dev_langs:
- C++
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fd57b10aba4298ff7facd725ab3ce1934ccf1ab
ms.sourcegitcommit: f3c398b1c7dbf36ab71b5ca89d365b1913afa307
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2018
---
# <a name="noalias"></a>noalias

**Блок, относящийся только к системам Microsoft**

`noalias`означает, что вызов функции не изменять или ссылаться на видимое глобальное состояние и изменяет памяти, на который указывает только *непосредственно* параметры-указатели (косвенные обращения первого уровня).

Если функция отмечена как `noalias`, оптимизатор может считать, что, помимо самих параметров, внутри функции используются или изменяются только косвенные обращения первого уровня для параметров-указателей. Видимое глобальное состояние — это набор всех данных, который не определяются и на которые нет ссылок за пределами области компиляции, и адрес которых не берется. Область компиляции — все исходные файлы ([/LTCG (Создание кода во время компоновки)](../build/reference/ltcg-link-time-code-generation.md) сборок) или единый исходный файл (отличных**/LTCG** сборки).

`noalias` Аннотация применяется только в теле функции заметками. Пометка функции как `__declspec(noalias)` не влияет на сглаживание указателей, возвращаемое функцией.

Другой заметку, которая может повлиять на Совмещение имен, в разделе [__declspec(restrict)](../cpp/restrict.md).

## <a name="example"></a>Пример

В следующем образце показано использование `__declspec(noalias)`.

Когда функция `multiply` помечается, обращается к памяти `__declspec(noalias)`, он сообщает компилятору, что эта функция не изменяет глобальное состояние только через указатели из своего списка параметров.

```C
// declspec_noalias.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

float * init(int m, int n)
{
    float * a;
    int i, j;
    int k=1;

    a = ma(m * n);
    if (!a) exit(1);
    for (i=0; i<m; i++)
        for (j=0; j<n; j++)
            a[i*n+j] = 0.1/k++;
    return a;
}

__declspec(noalias) void multiply(float * a, float * b, float * c)
{
    int i, j, k;

    for (j=0; j<P; j++)
        for (i=0; i<M; i++)
            for (k=0; k<N; k++)
                c[i * P + j] =
                          a[i * N + k] *
                          b[k * P + j];
}

int main()
{
    float * a, * b, * c;

    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));

    if (!mempool)
    {
        puts("ERROR: Malloc returned null");
        exit(1);
    }

    memptr = mempool;
    a = init(M, N);
    b = init(N, P);
    c = init(M, P);
 
    multiply(a, b, c);
}
```

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)  
[Ключевые слова](../cpp/keywords-cpp.md)  
[__declspec(restrict)](../cpp/restrict.md)  
