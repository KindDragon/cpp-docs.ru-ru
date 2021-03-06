---
title: "mbrtowc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- mbrtowc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbrtowc
dev_langs:
- C++
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f3446132532fbf212294c0176b697359572b235
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="mbrtowc"></a>mbrtowc
Преобразуют многобайтовый символ в текущем языковом стандарте в эквивалентный расширенный символ с возможностью перезапуска в середине многобайтового символа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t mbrtowc(  
   wchar_t *wchar,  
   const char *mbchar,  
   size_t count,  
   mbstate_t *mbstate  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `wchar`  
 Адрес расширенного символа для получения преобразованной строки расширенных символов (тип `wchar_t`). Это значение может быть пустым указателем, если не требуется возвращать расширенный символ.  
  
 `mbchar`  
 Адрес последовательности байтов (многобайтовый символ).  
  
 `count`  
 Число проверяемых байтов.  
  
 `mbstate`  
 Указатель на объект состояния преобразования. Если это значение является пустым указателем, функция использует статичный внутренний объект состояния преобразования. Так как внутренний объект `mbstate_t` не является потокобезопасным, мы рекомендуем всегда передавать собственный аргумент `mbstate`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений:  
  
 0  
 Если следующие `count` или менее байт составляют многобайтовый символ, представляющий расширенный символ NULL, который хранится в `wchar`, если `wchar` не является пустым указателем.  
  
 от 1 до `count` включительно  
 Если следующие `count` или менее байт составляют допустимый многобайтовый символ. Возвращаемое значение равно количеству байтов, составляющих многобайтовый символ. Эквивалентный расширенный символ хранится в `wchar`, если `wchar` не является пустым указателем.  
  
 (size_t)(-1)  
 Произошла ошибка кодирования. Следующие `count` или менее байт не составляют полный и допустимый многобайтовый символ. В этом случае значение `errno` будет EILSEQ, а состояние сдвига преобразования в `mbstate` будет не определено.  
  
 (size_t)(-2)  
 Если следующие `count` байт складываются в неполный, но потенциально допустимый многобайтовый символ и все байты `count` были обработаны. Значение в `wchar` не сохраняется, но `mbstate` обновляется для перезапуска функции.  
  
## <a name="remarks"></a>Примечания  
 Если параметр `mbchar` является пустым указателем, функция эквивалентна вызову:  
  
 `mbrtowc(NULL, "", 1, &mbstate)`  
  
 В этом случае значение аргументов `wchar` и `count` игнорируется.  
  
 Если значение параметра `mbchar` не является пустым указателем, функция проверяет `count` байт из параметра `mbchar` для определения числа байтов, требуемых для получения следующего многобайтового символа. Если следующий символ является допустимым, соответствующий многобайтовый символ сохраняется в параметре `wchar`, если он не является пустым указателем. Если символ соответствует расширенному нуль-символу, результирующее состояние `mbstate` является начальным состоянием преобразования.  
  
 Функция `mbrtowc` отличается от функций [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md) возможностью перезапуска. Состояние преобразования хранится в переменной `mbstate` для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, в приложении необходимо использовать функцию `wcsrlen` вместо функции `wcslen`, если в последующем вызове используется функция `wcsrtombs`, а не функция `wcstombs`.  
  
## <a name="example"></a>Пример  
 Преобразует многобайтовый символ в эквивалентный расширенный символ.  
  
```  
// crt_mbrtowc.cpp  
  
#include <stdio.h>  
#include <mbctype.h>  
#include <string.h>  
#include <locale.h>  
#include <wchar.h>  
  
#define BUF_SIZE 100  
  
int Sample(char* szIn, wchar_t* wcOut, int nMax)  
{  
    mbstate_t   state = {0}; // Initial state  
    size_t      nConvResult,   
                nmbLen = 0,  
                nwcLen = 0;  
    wchar_t*    wcCur = wcOut;  
    wchar_t*    wcEnd = wcCur + nMax;  
    const char* mbCur = szIn;  
    const char* mbEnd = mbCur + strlen(mbCur) + 1;  
    char*       szLocal;  
  
    // Sets all locale to French_Canada.1252  
    szLocal = setlocale(LC_ALL, "French_Canada.1252");  
    if (!szLocal)  
    {  
        printf("The fuction setlocale(LC_ALL, \"French_Canada.1252\") failed!\n");  
        return 1;  
    }  
  
    printf("Locale set to: \"%s\"\n", szLocal);  
  
    // Sets the code page associated current locale's code page  
    // from a previous call to setlocale.  
    if (_setmbcp(_MB_CP_SBCS) == -1)  
    {  
        printf("The fuction _setmbcp(_MB_CP_SBCS) failed!");  
        return 1;  
    }  
  
    while ((mbCur < mbEnd) && (wcCur < wcEnd))  
    {  
        //  
        nConvResult = mbrtowc(wcCur, mbCur, 1, &state);  
        switch (nConvResult)  
        {  
            case 0:  
            {  // done  
                printf("Conversion succeeded!\nMultibyte String: ");  
                printf(szIn);  
                printf("\nWC String: ");  
                wprintf(wcOut);  
                printf("\n");  
                mbCur = mbEnd;  
                break;  
            }  
  
            case -1:  
            {  // encoding error  
                printf("The call to mbrtowc has detected an encoding error.\n");  
                mbCur = mbEnd;  
                break;  
            }  
  
            case -2:  
            {  // incomplete character  
                if   (!mbsinit(&state))  
                {  
                    printf("Currently in middle of mb conversion, state = %x\n", state);  
                    // state will contain data regarding lead byte of mb character  
                }  
  
                ++nmbLen;  
                ++mbCur;  
                break;  
            }  
  
            default:  
            {  
                if   (nConvResult > 2) // The multibyte should never be larger than 2  
                {  
                    printf("Error: The size of the converted multibyte is %d.\n", nConvResult);  
                }  
  
                ++nmbLen;  
                ++nwcLen;  
                ++wcCur;  
                ++mbCur;  
            break;  
            }  
        }  
    }  
  
   return 0;  
}  
  
int main(int argc, char* argv[])  
{  
    char    mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";  
    wchar_t wcBuf[BUF_SIZE] = {L''};  
  
    return Sample(mbBuf, wcBuf, BUF_SIZE);  
}  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
Locale set to: "French_Canada.1252"  
Conversion succeeded!  
Multibyte String: AaBbCcÜïα∩≡xXyYzZ  
WC String: AaBbCcÜïα∩≡xXyYzZ  
```  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`mbrtowc`|\<wchar.h>|  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)