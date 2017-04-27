---
title: "&lt;random&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <random>
dev_langs:
- C++
helpviewer_keywords:
- random header
ms.assetid: 60afc25c-b162-4811-97c1-1b65398d4c57
caps.latest.revision: 58
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c7f3b346bc8abeab0c6bd913fc0b554bef4ed208
ms.openlocfilehash: a817bc264a762d6043b80a68d966a9e8420c72b5
ms.lasthandoff: 02/24/2017

---
# <a name="ltrandomgt"></a>&lt;random&gt;
Определяет средства для генерации случайных чисел с равномерным распределением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <random>  
```  
  
## <a name="summary"></a>Сводка  
 *Генератор случайных чисел* — это объект, формирующий последовательность из псевдослучайных чисел. Генератор, который выдает значения с равномерным распределением в указанном диапазоне, называют *равномерным генератором случайных чисел* (РГСЧ). Класс-шаблон, созданный для работы в качестве РГСЧ, называют *механизмом*, если этот класс обладает определенными общими признаками, которые описаны далее. РГСЧ может объединяться и обычно объединяется с *распределением* путем передачи РГСЧ в качестве аргумента в `operator()` распределения для получения значений, распределенных в соответствии с заданным распределением.  
  
 Эти ссылки ведут к основным разделам статьи.  
  
- [Примеры](#code)  
  
- [Списки по категориям](#listing)  
  
- [Механизмы и распределения](#engdist)  
  
- [Примечания](#comments)  
  
### <a name="quick-tips"></a>Краткие советы  
 Вот несколько советов по использованию `<random>`.  
  
-   В большинстве случаев РГСЧ формируют необработанные значения, которые упорядочиваются распределением. (Исключением служит функция [std::shuffle()](../standard-library/algorithm-functions.md#std__shuffle), так как она использует РГСЧ напрямую.)  
  
-   Один экземпляр РГСЧ или распределения не может безопасно вызываться параллельно, так как использование РГСЧ или распределения — это операция изменения. Дополнительные сведения см. в разделе [Потоковая безопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md).  
  
- Предлагаются [предварительно заданные определения типов](#typedefs) для нескольких механизмов. Это рекомендуемый способ создания РГСЧ при использовании механизма.  
  
-   Самое полезное сочетание для большинства приложений — это механизм `mt19937` с `uniform_int_distribution`, как показано в [примере кода](#code) далее в этой статье.  
  
 В заголовке можно выбрать различные варианты `<random>`; любой из них предпочтительнее устаревшей функции библиотеки времени выполнения C `rand()`. Для информации о недостатках `rand()` и о том, как `<random>` работает с этими недостатками, см. [это видео](http://go.microsoft.com/fwlink/LinkId=397615).  
  
##  <a name="a-namecodea-examples"></a><a name="code"></a> Примеры  
 В следующем примере кода показана генерация случайных чисел; в этом случае пять из них используют генератор, созданный с недетерминистическим начальным значением.  
  
```cpp  
#include <random>  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    random_device rd;   // non-deterministic generator  
    mt19937 gen(rd());  // to seed mersenne twister.  
                        // replace the call to rd() with a  
                        // constant value to get repeatable  
                        // results.  
  
    for (int i = 0; i < 5; ++i) {  
        cout << gen() << " "; // print the raw output of the generator.  
    }  
    cout << endl;  
}  
```  
  
```Output  
2430338871 3531691818 2723770500 3252414483 3632920437  
```  
  
 Это высококачественные случайные числа, они разные при каждом запуске этой программы, но не обязательно находятся в полезном диапазоне. Для управления диапазоном следует использовать однородное распределение, как показано в следующем коде:  
  
```cpp  
#include <random>  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    random_device rd;   // non-deterministic generator  
    mt19937 gen(rd());  // to seed mersenne twister.  
    uniform_int_distribution<> dist(1,6); // distribute results between 1 and 6 inclusive.  
  
    for (int i = 0; i < 5; ++i) {  
        cout << dist(gen) << " "; // pass the generator to the distribution.  
    }  
    cout << endl;  
}  
```  
  
```Output  
5 1 6 1 2  
```  
  
 В следующем примере кода показан более реалистичный набор случаев использования с однородно распределенными генераторами случайных чисел, перемешивающих содержимое векторов и массивов.  
  
```cpp  
// cl.exe /EHsc /nologo /W4 /MTd  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <random>  
#include <string>  
#include <vector>  
#include <functional> // ref()  
  
using namespace std;  
  
template <typename C> void print(const C& c) {  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
template <class URNG>  
void test(URNG& urng) {  
  
    // Uniform distribution used with a vector  
    // Distribution is [-5, 5] inclusive  
    uniform_int_distribution<int> dist(-5, 5);  
    vector<int> v;  
  
    for (int i = 0; i < 20; ++i) {  
        v.push_back(dist(urng));  
    }  
  
    cout << "Randomized vector: ";  
    print(v);  
  
    // Shuffle an array   
    // (Notice that shuffle() takes a URNG, not a distribution)  
    array<string, 26> arr = { { "H", "He", "Li", "Be", "B", "C", "N", "O", "F",  
        "Ne", "Na", "Mg", "Al", "Si", "P", "S", "Cl", "Ar", "K", "Ca", "Sc",  
        "Ti", "V", "Cr", "Mn", "Fe" } };  
  
    shuffle(arr.begin(), arr.end(), urng);  
  
    cout << "Randomized array: ";  
    print(arr);  
    cout << "--" << endl;  
}  
  
int main()  
{  
    // First run: non-seedable, non-deterministic URNG random_device  
    // Slower but crypto-secure and non-repeatable.  
    random_device rd;  
    cout << "Using random_device URNG:" << endl;  
    test(rd);  
  
    // Second run: simple integer seed, repeatable results  
    cout << "Using constant-seed mersenne twister URNG:" << endl;  
    mt19937 engine1(12345);  
    test(engine1);  
  
    // Third run: random_device as a seed, different each run  
    // (Desirable for most purposes)  
    cout << "Using non-deterministic-seed mersenne twister URNG:" << endl;  
    mt19937 engine2(rd());  
    test(engine2);  
  
    // Fourth run: "warm-up" sequence as a seed, different each run  
    // (Advanced uses, allows more than 32 bits of randomness)  
    cout << "Using non-deterministic-seed \"warm-up\" sequence mersenne twister URNG:" << endl;  
    array<unsigned int, mt19937::state_size> seed_data;  
    generate_n(seed_data.begin(), seed_data.size(), ref(rd));  
    seed_seq seq(begin(seed_data), end(seed_data));  
    mt19937 engine3(seq);  
    test(engine3);  
}  
```  
  
```Output  
Using random_device URNG:  
Randomized vector: 5 -4 2 3 0 5 -2 0 4 2 -1 2 -4 -3 1 4 4 1 2 -2  
Randomized array: O Li V K C Ti N Mg Ne Sc Cl B Cr Mn Ca Al F P Na Be Si Ar Fe S He H  
--  
Using constant-seed mersenne twister URNG:  
Randomized vector: 3 -1 -5 0 0 5 3 -4 -3 -4 1 -3 0 -3 -2 -4 5 1 -1 -1  
Randomized array: Al O Ne Si Na Be C N Cr Mn H V F Sc Mg Fe K Ca S Ti B P Ar Cl Li He  
--  
Using non-deterministic-seed mersenne twister URNG:  
Randomized vector: 5 -4 0 2 1 -2 4 4 -4 0 0 4 -5 4 -5 -1 -3 0 0 3  
Randomized array: Si Fe Al Ar Na P B Sc H F Mg Li C Ti He N Mn Be O Ca Cr V K Ne Cl S  
--  
Using non-deterministic-seed "warm-up" sequence mersenne twister URNG:  
Randomized vector: -1 3 -2 4 1 3 0 -5 5 -5 0 0 5 0 -3 3 -4 2 5 0  
Randomized array: Si C Sc H Na O S Cr K Li Al Ti Cl B Mn He Fe Ne Be Ar V P Ca N Mg F  
--  
```  
  
Этот код показывает два разных метода рандомизации (вектора целых чисел и перемешивания массива индексированных данных) с помощью тестовой функции шаблона. В первом вызове тестовой функции используется криптобезопасный, недетерминистический, неповторяющийся РГСЧ `random_device` без начального значения. Во втором вызове в качестве РГСЧ используется `mersenne_twister_engine` с детерминистическим 32-разрядным постоянным начальным значением; это означает, что результаты повторяются. В третьем вызове для `mersenne_twister_engine` используется 32-разрядное недетерминистическое значение — результат выполнения `random_device`. В четвертом вызове применяется [последовательность начальных значений](../standard-library/seed-seq-class.md), заполненная результатами выполнения `random_device`, что обеспечивает рандомизацию лучше, чем 32-разрядный недетерминистический подход (но все еще не обеспечивает криптобезопасность). Чтобы узнать больше, читайте дальше.  
  
##  <a name="a-namelistinga-categorized-listing"></a><a name="listing"></a> Списки по категориям  
  
###  <a name="a-nameurngsa-uniform-random-number-generators"></a><a name="urngs"></a> Равномерные генераторы случайных чисел  
 РГСЧ часто описываются следующими свойствами.  
  
1. **Длина периода**: число итераций до повторения последовательности чисел. Чем период длиннее, тем лучше.  
  
2. **Производительность**: сколько времени и памяти требуется для получения чисел. Чем меньше, тем лучше.  
  
3. **Качество**: насколько полученная последовательность близка к реальным случайным числам. Часто это называется "*стохастичностью*".  
  
 В следующих разделах перечислены РГСЧ, доступные в заголовке `<random>`.  
  
####  <a name="a-namerda-non-deterministic-generator"></a><a name="rd"></a> Недетерминистический генератор  
  
|||  
|-|-|  
|[Класс random_device](../standard-library/random-device-class.md)|Формирует недетерминистическую, криптографическую безопасную случайную последовательность с помощью внешнего устройства. Обычно используется для получения начального значения для механизма случайных чисел. Низкая производительность, очень высокое качество. Дополнительные сведения см. в разделе [Замечания](#comments).|  
  
####  <a name="a-nametypedefsa-engine-typedefs-with-predefined-parameters"></a><a name="typedefs"></a> Определения типа механизма с предварительно заданными параметрами  
 Для инициации механизмов и адаптеров. Дополнительные сведения см. в разделе [Механизмы и распределения](#engdist).  
  
- `default_random_engine`Механизм по умолчанию.   
 `typedef mt19937 default_random_engine;`  
  
- `knuth_b` Механизм Кнута.   
 `typedef shuffle_order_engine<minstd_rand0, 256> knuth_b;`  
  
- `minstd_rand0` Минимальный стандартный механизм 1988 (Льюис, Гудмэн и Миллер [Lewis, Goodman, and Miller], 1969).   
 `typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;`  
  
- `minstd_rand` Обновленный минимальный стандартный механизм `minstd_rand0` (Парк, Миллер и Стокмайер [Park, Miller, and Stockmeyer], 1993).   
 `typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;`  
  
- `mt19937` 32-разрядный механизм типа "Вихрь Мерсенна" (Матсумото и Нишимура [Matsumoto and Nishimura], 1998).   
 `typedef mersenne_twister_engine<unsigned int, 32, 624, 397,      31, 0x9908b0df,      11, 0xffffffff,      7, 0x9d2c5680,      15, 0xefc60000,      18, 1812433253> mt19937;`  
  
- `mt19937_64` 64-разрядный механизм типа "Вихрь Мерсенна" (Матсумото и Нишимура [Matsumoto and Nishimura], 2000).   
 `typedef mersenne_twister_engine<unsigned long long, 64, 312, 156,      31, 0xb5026f5aa96619e9ULL,      29, 0x5555555555555555ULL,      17, 0x71d67fffeda60000ULL,      37, 0xfff7eee000000000ULL,      43, 6364136223846793005ULL> mt19937_64;`  
  
- `ranlux24` 24-разрядный механизм RANLUX (Мартин Люшер и Фред Джеймс [Martin Lüscher and Fred James], 1994).   
 `typedef discard_block_engine<ranlux24_base, 223, 23> ranlux24;`  
  
- `ranlux24_base` Используется в качестве основания для `ranlux24`.   
 `typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`  
  
- `ranlux48` 48-разрядный механизм RANLUX (Мартин Люшер и Фред Джеймс [Martin Lüscher and Fred James], 1994).   
 `typedef discard_block_engine<ranlux48_base, 389, 11> ranlux48;`  
  
- `ranlux48_base` Используется в качестве основания для `ranlux48`.   
 `typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`  
  
####  <a name="a-nameenga-engine-templates"></a><a name="eng"></a> Шаблоны механизмов  
 Шаблоны механизмов используются как автономные РГСЧ или как базовые механизмы, которые передаются [адаптерам механизмов](#engadapt). Обычно они создаются с [предварительно заданным определением типа механизма](#typedefs) и передаются в [распределение](#distributions). Дополнительные сведения см. в разделе [Механизмы и распределения](#engdist).  
  
|||  
|-|-|  
|[Класс linear_congruential_engine](../standard-library/linear-congruential-engine-class.md)|Создает случайную последовательность, используя линейный конгруэнтный алгоритм. Самый простой с самым низким качеством.|  
|[Класс mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md)|Создает случайную последовательность, используя алгоритм "Вихрь Мерсенна". Самый сложный с самым высоким качеством (кроме класса random_device). Очень высокая производительность.|  
|[Класс subtract_with_carry_engine](../standard-library/subtract-with-carry-engine-class.md)|Создает случайную последовательность, используя алгоритм вычитания с переносом. Улучшение `linear_congruential_engine`, но с более низким качеством и производительностью, чем у `mersenne_twister_engine`.|  
  
####  <a name="a-nameengadapta-engine-adaptor-templates"></a><a name="engadapt"></a> Шаблоны адаптеров механизмов  
 Адаптеры механизмов — это шаблоны, адаптирующие другие (базовые) механизмы. Обычно они создаются с [предварительно заданным определением типа механизма](#typedefs) и передаются в [распределение](#distributions). Дополнительные сведения см. в разделе [Механизмы и распределения](#engdist).  
  
|||  
|-|-|  
|[Класс discard_block_engine](../standard-library/discard-block-engine-class.md)|Создает случайную последовательность, удаляя значения, возвращенные базовым механизмом.|  
|[Класс independent_bits_engine](../standard-library/independent-bits-engine-class.md)|Создает случайную последовательность с указанным числом разрядов, перемешивая разряды из значений, возвращенных базовым механизмом.|  
|[Класс shuffle_order_engine](../standard-library/shuffle-order-engine-class.md)|Создает случайную последовательность, изменяя порядок значений, возвращенных базовым механизмом.|  
  
 [[Шаблоны механизмов](#eng)]  
  
###  <a name="a-namedistributionsa-random-number-distributions"></a><a name="distributions"></a> Распределения случайных чисел  
 В следующих разделах перечислены распределения, доступные в заголовке `<random>`. Распределения — это механизмы постобработки, которые обычно используют результаты РГСЧ в качестве входа и распределяют выходные данные с помощью заданной функции плотности статистической вероятности. Дополнительные сведения см. в разделе [Механизмы и распределения](#engdist).  
  
#### <a name="uniform-distributions"></a>Равномерные распределения  
  
|||  
|-|-|  
|[Класс uniform_int_distribution](../standard-library/uniform-int-distribution-class.md)|Формирует равномерное распределение целых чисел в диапазоне, заданном замкнутым интервалом \[a, b] (a и b входят в диапазон).|  
|[Класс uniform_real_distribution](../standard-library/uniform-real-distribution-class.md)|Формирует равномерное распределение вещественных чисел (с плавающей запятой) в диапазоне, заданном полузамкнутым интервалом [a, b) (a включено, b не входит в диапазон).|  
|[generate_canonical](../standard-library/random-functions.md#generate_canonical)|Формирует равномерное распределение вещественных чисел (с плавающей запятой) с заданной точностью в диапазоне [0, 1) (0 входит в диапазон, 1 не входит).|  
  
 [[Распределения случайных чисел](#distributions)]  
  
#### <a name="bernoulli-distributions"></a>Распределения Бернулли  
  
|||  
|-|-|  
|[Класс bernoulli_distribution](../standard-library/bernoulli-distribution-class.md)|Формирует распределение Бернулли значений типа `bool`.|  
|[Класс binomial_distribution](../standard-library/binomial-distribution-class.md)|Формирует биномиальное распределение целых значений.|  
|[Класс geometric_distribution](../standard-library/geometric-distribution-class.md)|Формирует геометрическое распределение целых значений.|  
|[Класс negative_binomial_distribution](../standard-library/negative-binomial-distribution-class.md)|Формирует отрицательное биномиальное распределение целых значений.|  
  
 [[Распределения случайных чисел](#distributions)]  
  
#### <a name="normal-distributions"></a>Нормальные распределения  
  
|||  
|-|-|  
|[Класс cauchy_distribution](../standard-library/cauchy-distribution-class.md)|Формирует распределение Коши вещественных значений (с плавающей запятой).|  
|[Класс chi_squared_distribution](../standard-library/chi-squared-distribution-class.md)|Формирует распределение хи-квадрат вещественных значений (с плавающей запятой).|  
|[Класс fisher_f_distribution](../standard-library/fisher-f-distribution-class.md)|Формирует F-распределение (также известное как F-распределение Снедекора или распределение Фишера-Снедекора) вещественных значений (с плавающей запятой).|  
|[Класс lognormal_distribution](../standard-library/lognormal-distribution-class.md)|Формирует логарифмически нормальное распределение вещественных значений (с плавающей запятой).|  
|[Класс normal_distribution](../standard-library/normal-distribution-class.md)|Формирует нормальное (Гауссово) распределение вещественных значений (с плавающей запятой).|  
|[Класс student_t_distribution](../standard-library/student-t-distribution-class.md)|Формирует *t*-распределение Стьюдента вещественных значений (с плавающей запятой).|  
  
 [[Распределения случайных чисел](#distributions)]  
  
#### <a name="poisson-distributions"></a>Распределения Пуассона  
  
|||  
|-|-|  
|[Класс exponential_distribution](../standard-library/exponential-distribution-class.md)|Формирует экспоненциальное распределение вещественных значений (с плавающей запятой).|  
|[Класс extreme_value_distribution](../standard-library/extreme-value-distribution-class.md)|Формирует распределение экстремальных вещественных значений (с плавающей запятой).|  
|[Класс gamma_distribution](../standard-library/gamma-distribution-class.md)|Формирует гамма-распределение вещественных значений (с плавающей запятой).|  
|[Класс poisson_distribution](../standard-library/poisson-distribution-class.md)|Формирует распределение Пуассона целых значений.|  
|[Класс weibull_distribution](../standard-library/weibull-distribution-class.md)|Формирует распределение Вейбулла вещественных значений (с плавающей запятой).|  
  
 [[Распределения случайных чисел](#distributions)]  
  
#### <a name="sampling-distributions"></a>Выборочные распределения  
  
|||  
|-|-|  
|[Класс discrete_distribution](../standard-library/discrete-distribution-class.md)|Формирует дискретное распределение целых чисел.|  
|[Класс piecewise_constant_distribution](../standard-library/piecewise-constant-distribution-class.md)|Формирует кусочно-постоянное распределение вещественных значений (с плавающей запятой).|  
|[Класс piecewise_linear_distribution](../standard-library/piecewise-linear-distribution-class.md)|Формирует кусочно-линейное распределение вещественных значений (с плавающей запятой).|  
  
 [[Распределения случайных чисел](#distributions)]  
  
### <a name="utility-functions"></a>Служебные функции  
 В этом разделе перечислены основные служебные функции, доступные в заголовке `<random>`.  
  
|||  
|-|-|  
|[Класс seed_seq](../standard-library/seed-seq-class.md)|Создает шифрованную порождающую последовательность без смещения. Используется для предотвращения повтора потоков случайных чисел. Полезно, если на основе механизмов инициализируется множество РГСЧ.|  
  
### <a name="operators"></a>Операторы  
 В этом разделе перечислены операторы, доступные в заголовке `<random>`.  
  
|||  
|-|-|  
|`operator==`|Проверка на то, что РГСЧ с левой стороны оператора равен механизму с правой стороны.|  
|`operator!=`|Проверка на то, что РГСЧ с левой стороны оператора не равен механизму с правой стороны.|  
|`operator<<`|Запись сведений о состоянии в поток.|  
|`operator>>`|Извлечение сведений о состоянии из потока.|  
  
##  <a name="a-nameengdista-engines-and-distributions"></a><a name="engdist"></a> Механизмы и распределения  
 Сведения о каждой категории класса шаблонов, заданных в `<random>`, см. в следующих разделах. Обе категории принимают тип в качестве аргумента и используют общие имена параметров шаблона для описания свойств типа, которые можно использовать как тип фактического аргумента, как показано далее.  
  
- `IntType` обозначает `short`, `int`, `long`, `long long`, `unsigned short`, `unsigned int`, `unsigned long` или `unsigned long long`.  
  
- `UIntType` обозначает `unsigned short`, `unsigned int`, `unsigned long` или `unsigned long long`.  
  
- `RealType` обозначает `float`, `double` или `long double`.  
  
### <a name="engines"></a>Механизмы  
 [Шаблоны механизмов](#eng) и [шаблоны адаптеров механизмов](#engadapt) — это шаблоны, параметры которых настраивают созданный генератор.  
  
 *Механизм* — это класс или класс-шаблон, экземпляры которого (генераторы) служат источником случайных чисел, равномерно распределенных между минимальным и максимальным значениями. *Адаптер механизма* предоставляет последовательность значений с различной стохастичностью, беря значения, сформированные другим механизмом случайных чисел, и применяя к ним определенный алгоритм.  
  
 Каждый механизм и адаптер механизма содержат следующие члены.  
  
- `typedef` `numeric-type` `result_type` — это тип, возвращаемый `operator()` генератора. `numeric-type` передается как параметр шаблона при создании экземпляра.  
  
- `result_type operator()` возвращает значения, которые равномерно распределены между `min()` и `max()`.  
  
- `result_type min()` возвращает минимальное значение, полученное от функции `operator()` генератора. Адаптеры механизма используют результат функции `min()` базового механизма.  
  
- `result_type max()` возвращает максимальное значение, полученное от функции `operator()` генератора. Если `result_type` — это целочисленный тип, то `max()` — это максимальное значение, которое может быть возвращено (инклюзивное). Если `result_type` — это вещественное значение, то `max()` — это наименьшее значение, превышающее все значения, которые могут быть возвращены (неинклюзивное). Адаптеры механизма используют результат функции `max()` базового механизма.  
  
- `void seed(result_type s)` задает для генератора начальное значение `s`. Для механизмов используется сигнатура `void seed(result_type s = default_seed)` для поддержки параметров по умолчанию (в адаптерах механизмов определена отдельная функция `void seed()`, как показано далее).  
  
- `template <class Seq> void seed(Seq& q)` задает для генератора начальное значение, используя [seed_seq](../standard-library/seed-seq-class.md)`Seq`.  
  
-   Явный конструктор с аргументом `result_type x`, который создает генератор, начальное значение которого определяется так же, как при вызове функции `seed(x)`.  
  
-   Явный конструктор с аргументом `seed_seq& seq`, который создает генератор, начальное значение которого определяется так же, как при вызове функции `seed(seq)`.  
  
- `void discard(unsigned long long count)` вызывает функцию `operator()``count` раз и отбрасывает каждое значение.  
  
 **Адаптеры механизмов** также поддерживают следующие члены (`Engine` — это первый параметр шаблона адаптера механизма, обозначающий тип базового механизма):  
  
-   Конструктор по умолчанию, который инициализирует генератор так же, как конструктор базового механизма по умолчанию.  
  
-   Явный конструктор с аргументом `const Engine& eng`. Это необходимо для поддержки конструкции копирования с использованием базового механизма.  
  
-   Явный конструктор с аргументом `Engine&& eng`. Это необходимо для поддержки конструкции перемещения с использованием базового механизма.  
  
- `void seed()` инициализирует генератор с использованием начального значения базового механизма по умолчанию.  
  
- Функция свойства `const Engine& base()` возвращает базовый механизм, который использовался для создания генератора.  
  
 Каждый механизм поддерживает *состояние*, определяющее последовательность значений, которые будут созданы последующими вызовами `operator()`. Состояние двух генераторов, созданных на основе механизмов одного типа, можно сравнить с помощью операторов `operator==` и `operator!=`. Если два состояния равны, генераторы будут получать одинаковые последовательности значений. Состояние объекта можно сохранить в поток как последовательность 32-разрядных беззнаковых значений, используя оператор `operator<<` генератора. Состояние после сохранения не изменяется. Сохраненное состояние можно считать в генератор, созданный на основе механизма того же типа, используя оператор `operator>>`.  
  
### <a name="distributions"></a>Распределения  
 [Распределения случайных чисел](#distributions) — это класс или класс-шаблон, экземпляры которого преобразуют поток равномерно распределенных случайных чисел, полученных от механизма, в поток случайных чисел с определенным распределением. У каждого распределения есть следующие члены.  
  
- `typedef` `numeric-type` `result_type` — это тип, возвращаемый функцией `operator()` распределения. `numeric-type` передается как параметр шаблона при создании экземпляра.  
  
- `template <class URNG> result_type operator()(URNG& gen)` возвращает значения, которые распределяются в соответствии с определением распределения, используя `gen` в качестве источника равномерно распределенных случайных значений и сохраненные *параметры распределения*.  
  
- `template <class URNG> result_type operator()(URNG& gen, param_type p)` возвращает значения, которые распределены в соответствии с определением распределения, используя `gen` в качестве источника случайных значений с равномерным распределением и структуру параметров `p`.  
  
- `typedef` `unspecified-type` `param_type` — это пакет параметров, которые могут передаваться функции `operator()` и использоваться вместо сохраненных параметров для формирования возвращаемого значения.  
  
-   Конструктор `const param&` инициализирует сохраненные параметры на основе своего аргумента.  
  
- `param_type param() const` получает сохраненные параметры.  
  
- `void param(const param_type&)` задает сохраненные параметры на основе своего аргумента.  
  
- `result_type min()` возвращает минимальное значение, полученное от функции `operator()` распределения.  
  
- `result_type max()` возвращает максимальное значение, полученное от функции `operator()` распределения. Если `result_type` — это целочисленный тип, то `max()` — это максимальное значение, которое может быть возвращено (инклюзивное). Если `result_type` — это вещественное значение, то `max()` — это наименьшее значение, превышающее все значения, которые могут быть возвращены (неинклюзивное).  
  
- `void reset()` удаляет любые кэшированные значения, чтобы результат следующего вызова `operator()` не зависел от любых значений, полученных от механизма перед вызовом.  
  
 Структура параметров — это объект, в котором хранятся все параметры, необходимые для распределения. Она содержит следующее.  
  
- `typedef` `distribution-type` `distribution_type`, тип распределения.  
  
-   Один или несколько конструкторов, которые принимают такие же наборы параметров, что и конструкторы распределения.  
  
-   Такие же функции параметров и доступа, как у распределения.  
  
-   Операторы сравнения равенства и неравенства.  
  
 Дополнительные сведения см. ниже в справочных подразделах, указанных ранее в этой статье.  
  
##  <a name="a-namecommentsa-remarks"></a><a name="comments"></a> Примечания  
 В Visual Studio есть два очень полезных РГСЧ — `mt19937` и `random_device`, которые показаны в следующей таблице.  
  
|РГСЧ|Быстрый|Криптобезопасный|С начальным значением|Детерминированный|  
|----------|-----------|---------------------|---------------|--------------------|  
|`mt19937`|Да|Нет|Да|Да<sup>*</sup>|  
|`random_device`|Нет|Да|Нет|Нет|  
  
 <sup>* Если предоставлено известное начальное значение.</sup>  
  
 Хотя согласно стандарту ISO для C++ функция `random_device` не обязана быть криптографически безопасной, в Visual Studio она реализована как криптобезопасная. (Термин "криптографически безопасный" не подразумевает каких-то гарантий, но обозначает минимальный уровень энтропии, а значит, и уровень предсказуемости данного алгоритма рандомизации. Дополнительные сведения см. в статье Википедии [Криптографически стойкий генератор псевдослучайных чисел](http://go.microsoft.com/fwlink/LinkId=398017).) Так как в стандарте ISO для C++ нет такого требования, на других платформах функция `random_device` может быть реализована как простой генератор псевдослучайных чисел (не криптобезопасный) и может использоваться как источник начальных значений для другого генератора. При использовании `random_device` в коде для разных платформ изучите документацию по этим платформам.  
  
 По определению, результаты `random_device` не воспроизводятся повторно; это значит, что эта функция может работать значительно медленнее, чем другие РГСЧ. Большинство приложений, которые не должны быть криптобезопасными, используют `mt19937` или аналогичный механизм, хотя для заполнения начального значения можно вызвать `random_device`, как показано в [примере кода](#code).  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)

