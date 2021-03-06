---
title: "Представление с плавающей запятой IEEE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- float keyword
- real*8 value
- floating-point numbers, IEEE representation
- double data type, floating-point representation
- IEEE floating point representation
- real*10 value
- long double
- real*4 value
ms.assetid: 537833e8-fe05-49fc-8169-55fd0314b195
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17fae0cbb16208d5c7e7346f354f3501e4803d96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ieee-floating-point-representation"></a>IEEE-представление с плавающей точкой
Microsoft Visual C++ согласуется со стандартом IEEE числовые. Существует три разновидности внутренних вещественных чисел. Реальные\*4 и действительного числа\*8 используются в Visual C++. Реальные\*4 объявляется с использованием слова **float**. Реальные\*8 объявляется с использованием слова **двойные**. В программировании на 32-разрядной Windows `long double` сопоставляется с типом данных **двойные**. Поддерживается, однако языка ассемблера для вычислений с использованием действительного числа * 10 данных типа.  
  
 Значения хранятся следующим образом:  
  
|Значение|Хранятся в виде|  
|-----------|---------------|  
|real * 4|подписать бит, 8-разрядную экспоненту, 23-битной мантиссы|  
|real * 8|подписать бит, 11-разрядную экспоненту, 52-битной мантиссы|  
|real * 10|подписать бит, 15-разрядной экспонентой, 64-битной мантиссы|  
  
 В реальном * 4 и действительного числа\*8 форматы имеется принятой начального 1 в мантиссе, не сохраняются в памяти, поэтому мантисса на самом деле 24- или 53 бита, несмотря на то, что хранятся только 23 или 52 разряда. Реальная\*10 формат фактически хранит этот бит.  
  
 Степени смещены на половину своего возможного значения. Это означает, что следует вычесть данное смещение из хранимой степени, чтобы получить фактический показатель степени. Если хранимая степень меньше, чем смещение, то это отрицательная степень.  
  
 Степени смещены следующим образом:  
  
|Показатель степени|Смещение|  
|--------------|---------------|  
|8-разрядное (real * 4)|127|  
|11-разрядную (real * 8)|1023|  
|15-разрядной (real * 10)|16383|  
  
 Данные степени не являются степенями числа 10; они представляют собой степени двух. То есть 8-разрядных хранимых степени может доходить до 127. Значение 2 ** 127 примерно равно 10\*\*38, что является реальным ограничением действительного числа\*4.  
  
 Мантисса хранится в виде бинарной доли формы 1.ххх.... Это часть имеет значение больше или равно 1 и меньше, чем 2. Обратите внимание, что вещественных чисел всегда хранятся в нормализованной форме; то есть мантисса сдвинута влево таким образом, что бит высокого порядка мантиссы всегда равен 1. Так как этот бит всегда равен 1, предполагается (но не хранится) в реальном * 4 и действительного числа\*8 форматы. Предполагается, что двоичный (не десятичная) точка находится справа начальные 1.  
  
 , Затем для разного размера имеет следующий формат:  
  
|Формат|1 БАЙТ|БАЙТ 2|БАЙТ 3|4 БАЙТ|...|N БАЙТ|  
|------------|------------|------------|------------|------------|---------|------------|  
|real * 4|`SXXX XXXX`|`XMMM MMMM`|`MMMM MMMM`|`MMMM MMMM`|||  
|real * 8|`SXXX XXXX`|`XXXX MMMM`|`MMMM MMMM`|`MMMM MMMM`|...|`MMMM MMMM`|  
|real * 10|`SXXX XXXX`|`XXXX XXXX`|`1MMM MMMM`|`MMMM MMMM`|...|`MMMM MMMM`|  
  
 `S`представляет бит знака `X`являются разрядами и `M`являются мантиссы. Обратите внимание, что в реальном предполагается, крайний левый разряд * 4 и действительного числа\*8 форматы, однако присутствует как «1» в 3 БАЙТА реальной\*10 формата.  
  
 Чтобы сдвинуть двоичную точку должным образом, вы сначала устранить смещение степени и затем переместить двоичную точку вправо или влево соответствующее количество битов.  
  
## <a name="examples"></a>Примеры  
 Ниже приведены некоторые примеры в реальном * 4 формата:  
  
-   В следующем примере знаковый бит равен нулю, и хранимая степень 128 или 100 0000 в двоичной форме, что равно 127 плюс 1. Хранимая мантисса имеет значение (1). 000 0000 ... 0000 0000, которой имеет неявный начальные и двоичная точку, поэтому в действительности мантисса имеет один.  
  
    ```  
                        SXXX XXXX XMMM MMMM ... MMMM MMMM  
    2   =  1  * 2**1  = 0100 0000 0000 0000 ... 0000 0000 = 4000 0000  
    ```  
  
-   Аналогично + 2, за исключением того, что бит знака. Это верно для всех чисел с плавающей запятой формате IEEE.  
  
    ```  
    -2  = -1  * 2**1  = 1100 0000 0000 0000 ... 0000 0000 = C000 0000  
    ```  
  
-   Та же мантисса, показатель степени увеличивается на единицу при (смещенной значение равно 129 или 10000001 в двоичном формате.  
  
    ```  
    4  =  1  * 2**2  = 0100 0000 1000 0000 ... 0000 0000 = 4080 0000  
    ```  
  
-   Та же степень, мантисса больше на половину — она равна (1). 100 0000... 0000 0000, являющийся, так как это двоичная дробь, 1 1/2 (значения дробных чисел: 1/2, 1/4, 1/8 и т. д).  
  
    ```  
    6  = 1.5 * 2**2  = 0100 0000 1100 0000 ... 0000 0000 = 40C0 0000  
    ```  
  
-   Та же степень, как и другие степени числа 2, мантисса является единственным меньше двух на 127 или 011 1111 1 в двоичном формате.  
  
    ```  
    1  = 1   * 2**0  = 0011 1111 1000 0000 ... 0000 0000 = 3F80 0000  
    ```  
  
-   Смещенной степень имеет значение 126, 011 1111 0 в двоичной форме, а мантисса имеет значение (1). 100 0000 ... 0000 0000 равно 1 1/2.  
  
    ```  
    .75 = 1.5 * 2**-1 = 0011 1111 0100 0000 ... 0000 0000 = 3F40 0000  
    ```  
  
-   Точно так же, как два за исключением бит, который представляет 1/4 задан в мантиссы.  
  
    ```  
    2.5 = 1.25 * 2**1 = 0100 0000 0010 0000 ... 0000 0000 = 4020 0000  
    ```  
  
-   1/10 представляет собой повторяющуюся дробь в двоичной форме. Мантисса просто имеют 1.6 и смещенной экспоненты определяет 1.6 деления 16 (это 1 011 1101 в двоичном формате, который является 123 в десятичном формате). Значение true, показатель степени является 123-127 = - 4, это означает, что коэффициент, на который умножается 2 ** -4 = 1/16. Обратите внимание, что хранимая мантисса округляется в сторону в последнем разряде — попытка представления непредставимое числа в максимально возможной точностью. (Причина 1/10 и 1/100 не точно представить в двоичном формате аналогичен причина точно не может быть представлен в виде десятичного числа, 1/3.)  
  
    ```  
    0.1 = 1.6 * 2**-4 = 0011 1101 1100 1100 ... 1100 1101 = 3DCC CCCD  
    ```  
  
-   `0  = 1.0 * 2**-128 = all zeros--a special case.`  
  
## <a name="see-also"></a>См. также  
 [Почему может уменьшиться точность чисел с плавающей запятой](../../build/reference/why-floating-point-numbers-may-lose-precision.md)