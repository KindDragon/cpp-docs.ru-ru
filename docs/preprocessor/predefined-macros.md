---
title: "Предустановленный макрос | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_VER"
  - "__ATOM__"
  - "__AVX__"
  - "__AVX2__"
  - "_CHAR_UNSIGNED"
  - "__CLR_VER"
  - "_CONTROL_FLOW_GUARD"
  - "__COUNTER__"
  - "__cplusplus"
  - "__cplusplus_cli"
  - "__cplusplus_winrt"
  - "_CPPRTTI"
  - "_CPPUNWIND"
  - "__DATE__"
  - "_DEBUG"
  - "_DLL"
  - "__FILE__"
  - "__FUNCDNAME__"
  - "__FUNCSIG__"
  - "__FUNCTION__"
  - "_INTEGRAL_MAX_BITS"
  - "_ISO_VOLATILE"
  - "_KERNEL_MODE"
  - "__LINE__"
  - "_M_AMD64"
  - "_M_ARM"
  - "_M_ARM_ARMV7VE"
  - "_M_ARM_FP"
  - "_M_ARM64"
  - "_M_CEE"
  - "_M_CEE_PURE"
  - "_M_CEE_SAFE"
  - "_M_FP_EXCEPT"
  - "_M_FP_FAST"
  - "_M_FP_PRECISE"
  - "_M_FP_STRICT"
  - "_M_IX86"
  - "_M_IX86_FP"
  - "_M_X64"
  - "_MANAGED"
  - "_MFC_VER"
  - "_MSC_BUILD"
  - "_MSC_EXTENSIONS"
  - "_MSC_FULL_VER"
  - "_MSC_VER"
  - "_MSVC_LANG"
  - "__MSVC_RUNTIME_CHECKS"
  - "_MT"
  - "_NATIVE_WCHAR_T_DEFINED"
  - "_NO_SIZED_DEALLOCATION"
  - "_OPENMP"
  - "_PREFAST_"
  - "_RESUMABLE_FUNCTIONS_SUPPORTED"
  - "_RTC_CONVERSION_CHECKS_ENABLED"
  - "__STDC__"
  - "__STDC_HOSTED__"
  - "__STDCPP_THREADS__"
  - "__TIME__"
  - "__TIMESTAMP__"
  - "__VA_ARGS__"
  - "_VC_NODEFAULTLIB"
  - "_WCHAR_T_DEFINED"
  - "_WIN32"
  - "_WIN64"
  - "_WINRT_DLL"
  - "__func__"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "отметки времени, макрос препроцессора"
  - "Компилятор CL.exe, номер версии"
  - "номера версий, компилятор C/C++ (cl.exe)"
  - "макросы, предопределенный с ++"
  - "макросы препроцессора,"
  - "предопределенный макрос"
  - "_ATL_VER - макрос"
  - "Макрос __ATOM__"
  - "Макрос __AVX__"
  - "Макрос __AVX2__"
  - "_CHAR_UNSIGNED - макрос"
  - "__CLR_VER - макрос"
  - "Макрос _CONTROL_FLOW_GUARD"
  - "__COUNTER__ - макрос"
  - "__cplusplus - макрос"
  - "Макрос __cplusplus_cli"
  - "Макрос __cplusplus_winrt"
  - "_CPPRTTI - макрос"
  - "_CPPUNWIND - макрос"
  - "__DATE__ - макрос"
  - "_DEBUG - макрос"
  - "_DLL - макрос"
  - "__FILE__ - макрос"
  - "__FUNCDNAME__ - макрос"
  - "__FUNCSIG__ - макрос"
  - "__FUNCTION__ - макрос"
  - "_INTEGRAL_MAX_BITS - макрос"
  - "Макрос _ISO_VOLATILE"
  - "Макрос _KERNEL_MODE"
  - "__LINE__ - макрос"
  - "Макрос _M_AMD64"
  - "Макрос _M_ARM"
  - "Макрос _M_ARM_ARMV7VE"
  - "Макрос _M_ARM_FP"
  - "Макрос _M_ARM64"
  - "_M_CEE - макрос"
  - "_M_CEE_PURE - макрос"
  - "_M_CEE_SAFE - макрос"
  - "Макрос _M_FP_EXCEPT"
  - "Макрос _M_FP_FAST"
  - "Макрос _M_FP_PRECISE"
  - "Макрос _M_FP_STRICT"
  - "_M_IX86 - макрос"
  - "_M_IX86_FP - макрос"
  - "_M_X64 - макрос"
  - "_MANAGED - макрос"
  - "_MFC_VER - макрос"
  - "_MSC_BUILD - макрос"
  - "_MSC_EXTENSIONS - макрос"
  - "_MSC_FULL_VER - макрос"
  - "_MSC_VER - макрос"
  - "Макрос _MSVC_LANG"
  - "__MSVC_RUNTIME_CHECKS - макрос"
  - "_MT - макрос"
  - "_NATIVE_WCHAR_T_DEFINED - макрос"
  - "Макрос _NO_SIZED_DEALLOCATION"
  - "_OPENMP - макрос"
  - "Макрос _PREFAST_"
  - "Макрос _RESUMABLE_FUNCTIONS_SUPPORTED"
  - "Макрос _RTC_CONVERSION_CHECKS_ENABLED"
  - "__STDC__ - макрос"
  - "Макрос __STDC_HOSTED__"
  - "Макрос __STDCPP_THREADS__"
  - "__TIME__ - макрос"
  - "__TIMESTAMP__ - макрос"
  - "__VA_ARGS__-макрос"
  - "_VC_NODEFAULTLIB - макрос"
  - "_WCHAR_T_DEFINED - макрос"
  - "_WIN32 - макрос"
  - "_WIN64 - макрос"
  - "Макрос _WINRT_DLL"
  - "Идентификатор __func__"
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
caps.latest.revision: 75
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 75
---
# Предустановленный макрос
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Компилятор Visual C++ определяется готовый определенные макросы препроцессора, в зависимости от языка (C или C++), целевого объекта компиляции и параметры выбранного компилятора.  
  
 Visual C++ поддерживает необходимые предопределенные макросы препроцессора, определяемый стандартом ANSI/ISO C99 и ISO стандартом C ++ 14. Реализация также поддерживает несколько дополнительных системам Microsoft макросов препроцессора. Некоторые макросы определяются только для определенной сборки сред или параметры компилятора. Если не указано, макросы определяются в записи преобразования, как если бы они были указаны как **/D** аргументов параметра компилятора. При определении, макросы разворачиваются препроцессором перед компиляцией указанные значения. Предопределенные макросы не принимают аргументы и не могут быть переопределены.  
  
## <a name="standard-predefined-identifier"></a>Стандартная предопределенный идентификатор  
 Компилятор поддерживает это предопределенный идентификатор, определяемый C99 стандарта ISO и ISO C ++ 11.  
  
-   **__func\_\_** неполное и недекорируемое имя включающей функции в виде функции локальной `static``const` массив `char`.  
  
    ```cpp  
    void example(){  
        printf("%s\n", __func__);  
    } // prints "example"  
    ```  
  
## <a name="standard-predefined-macros"></a>Стандартные предопределенные макросы  
 Компилятор поддерживает следующие предопределенные макросы, определяемый ISO C99 и C ++ 14 стандартов ISO.  
  
-   **__cplusplus** определен как значение целочисленного литерала, когда записи преобразования компилируется как C++. В противном случае не определено.  
  
-   **__DATE\_\_** Дата компиляции текущего файла исходного кода. Дата — это строка константы длиной литерал в формате *ммм дд гггг*. Название месяца *Mmm* совпадает сокращенное название месяца в дат, созданных библиотекой времени выполнения C [asctime](../c-runtime-library/reference/asctime-wasctime.md) функции. Дата первого символа *дд* — это пространство, если значение меньше 10. Этот макрос определяется всегда.  
  
-   **__FILE\_\_** имя текущего файла исходного кода. **__FILE\_\_** разворачивается для символьного литерала. Чтобы убедиться, что отображается полный путь к файлу, используйте [/FC (полный путь для файла исходного кода в диагностики)](../Topic/-FC%20\(Full%20Path%20of%20Source%20Code%20File%20in%20Diagnostics\).md). Этот макрос определяется всегда.  
  
-   **__LINE\_\_** определяется как целое число номер строки в текущем исходном файле. Значение **__LINE\_\_** макрос может быть изменен с помощью `#line` директивы. Этот макрос определяется всегда.  
  
-   **__STDC\_\_** определен как 1 только в том случае, если компилируется как C и [/Za](../build/reference/za-ze-disable-language-extensions.md) указан параметр компилятора. В противном случае не определено.  
  
-   **__STDC_HOSTED\_\_** определен как 1, если реализация *hosted реализацию*, поддерживает все необходимые стандартной библиотеки. В противном случае — определяется как 0.  
  
-   **__STDCPP_THREADS\_\_** определяется как 1 только в том случае, если в программе может присутствовать более чем один поток исполнения и скомпилирован как C++. В противном случае не определено.  
  
-   **__TIME\_\_** время перевод записи преобразования предварительной обработки. Время представляет собой строку символов литерал в формате *чч*, таким же, как время, возвращенное библиотекой времени выполнения C [asctime](../c-runtime-library/reference/asctime-wasctime.md) функции. Этот макрос определяется всегда.  
  
## <a name="microsoft-specific-predefined-macros"></a>Предопределенные макросы характерные для Майкрософт  
 Microsoft Visual C++ поддерживает следующие дополнительные предопределенные макросы.  
  
-   **__ATOM\_\_** определяется как 1, если [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md) задан параметр компилятора, и компилятор должен x86 или x64. В противном случае не определено.  
  
-   **__AVX\_\_** определяется как 1, если [/arch: AVX](../build/reference/arch-x86.md) или [/arch:AVX2](../build/reference/arch-x86.md) установлены параметры компилятора и компилятор должен x86 или x64. В противном случае не определено.  
  
-   **__AVX2\_\_** определяется как 1, если [/arch:AVX2](../build/reference/arch-x86.md) задан параметр компилятора, и компилятор должен x86 или x64. В противном случае не определено.  
  
-   **_CHAR_UNSIGNED** определяется как 1, если значение по умолчанию `char` тип без знака. Когда устанавливается [/J (по умолчанию — тип unsigned char)](../build/reference/j-default-char-type-is-unsigned.md) задан параметр компилятора. В противном случае не определено.  
  
-   **__CLR_VER** определяется как целочисленный литерал, представляющую версию общеязыковой среды выполнения, используемой при компиляции приложения. Значение кодируется в виде `Mmmbbbbb`, где `M` — Основная версия среды выполнения, `mm` — Дополнительная версия среды выполнения, и `bbbbb` — номер сборки. **__CLR_VER** определяется, если [/CLR](../build/reference/clr-common-language-runtime-compilation.md) задан параметр компилятора. В противном случае не определено.  
  
    ```cpp  
    // clr_ver.cpp  
    // compile with: /clr  
    using namespace System;  
    int main() {  
       Console::WriteLine(__CLR_VER);  
    }  
    ```  
  
-   **_CONTROL_FLOW_GUARD** определяется как 1, если [/guard:cf (Включение защиты потока управления)](../build/reference/guard-enable-control-flow-guard.md) задан параметр компилятора. В противном случае не определено.  
  
-   **__COUNTER\_\_** Expands целочисленный литерал, который начинается с 0 и увеличивается на 1 каждый раз, он используется в исходном файле или во включенных заголовках исходного файла. **__COUNTER\_\_** запоминает свое состояние при использовании предкомпилированных заголовков. Этот макрос определяется всегда.  
  
     В этом примере используется `__COUNTER__` присваивает уникальные идентификаторы трем различным объектам одного типа.  `exampleClass` Конструктор принимает целое число как параметр. В `main`, приложение объявляет три объекта типа `exampleClass`, используя `__COUNTER__` в качестве параметра уникального идентификатора:  
  
    ```cpp  
    // macro__COUNTER__.cpp  
    // Demonstration of __COUNTER__, assigns unique identifiers to  
    // different objects of the same type.  
    // Compile by using: cl /EHsc /W4 macro__COUNTER__.cpp  
    #include <stdio.h>  
  
    class exampleClass {  
        int m_nID;  
    public:  
        // initialize object with a read-only unique ID  
        exampleClass(int nID) : m_nID(nID) {}  
        int GetID(void) { return m_nID; }  
    };  
  
    int main()  
    {  
        // __COUNTER__ is initially defined as 0  
        exampleClass e1(__COUNTER__);  
  
        // On the second reference, __COUNTER__ is now defined as 1  
        exampleClass e2(__COUNTER__);  
  
        // __COUNTER__ is now defined as 2  
        exampleClass e3(__COUNTER__);  
  
        printf("e1 ID: %i\n", e1.GetID());  
        printf("e2 ID: %i\n", e2.GetID());  
        printf("e3 ID: %i\n", e3.GetID());  
  
        // Output  
        // ------------------------------  
        // e1 ID: 0  
        // e2 ID: 1  
        // e3 ID: 2  
  
        return 0;  
    }  
    ```  
  
-   **__cplusplus_cli** определяется как целочисленное литеральное значение 200406 при компиляции как C++ и [/CLR](../build/reference/clr-common-language-runtime-compilation.md), [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), или [/CLR: safe](../build/reference/clr-common-language-runtime-compilation.md) задан параметр компилятора. В противном случае не определено. Если определено, **__cplusplus_cli** действует во всем блоке преобразования.  
  
    ```cpp  
    // cplusplus_cli.cpp  
    // compile by using /clr  
    #include "stdio.h"  
    int main() {  
       #ifdef __cplusplus_cli  
          printf("%d\n", __cplusplus_cli);  
       #else  
          printf("not defined\n");  
       #endif  
    }  
    ```  
  
-   **__cplusplus_winrt** определяется как целочисленное литеральное значение 201009 при компиляции как C++ и [/ZW (компиляция среды выполнения Windows)](../build/reference/zw-windows-runtime-compilation.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_CPPRTTI** определяется как 1, если [/GR (включить информацию о типах времени выполнения)](../Topic/-GR%20\(Enable%20Run-Time%20Type%20Information\).md) задан параметр компилятора. В противном случае не определено.  
  
-   **_CPPUNWIND** определяется как 1, если один или несколько [/GX (Включить обработку исключений)](../Topic/-GX%20\(Enable%20Exception%20Handling\).md), [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md), или [/EH (модель обработки исключений)](../build/reference/eh-exception-handling-model.md) установлены параметры компилятора. В противном случае не определено.  
  
-   **_DEBUG** определен как 1, если [/LDd](../build/reference/md-mt-ld-use-run-time-library.md), [/MDd](../build/reference/md-mt-ld-use-run-time-library.md), или [/MTd](../build/reference/md-mt-ld-use-run-time-library.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_DLL** определяется как 1, если [/MD](../build/reference/md-mt-ld-use-run-time-library.md) или [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) задан параметр компилятора (Многопоточная DLL). В противном случае не определено.  
  
-   **__FUNCDNAME\_\_** определяется как строковый литерал, содержащий [декорированное имя](../Topic/Decorated%20Names.md) внешней функции. Макрос определяется только в пределах функции.  **__FUNCDNAME\_\_** макрос не разворачивается при использовании [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) или [/P](../build/reference/p-preprocess-to-a-file.md) параметр компилятора.  
  
     В этом примере используется `__FUNCDNAME__`, `__FUNCSIG__`, и `__FUNCTION__` макросы для отображения сведений о функции.  
  
     [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]  
  
-   **__FUNCSIG\_\_** определяется как строковый литерал, содержащий сигнатуру включающей функции. Макрос определяется только в пределах функции.  **__FUNCSIG\_\_** макрос не разворачивается при использовании [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) или [/P](../build/reference/p-preprocess-to-a-file.md) параметр компилятора. При компиляции для 64-разрядных конечных соглашение о вызовах — `__cdecl` по умолчанию. Пример использования см. в разделе `__FUNCDNAME__` макрос.  
  
-   **__FUNCTION\_\_** определяется как строковый литерал, содержащий внешнее имя включающей функции. Макрос определяется только в пределах функции.  **__FUNCTION\_\_** макрос не разворачивается при использовании [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) или [/P](../build/reference/p-preprocess-to-a-file.md) параметр компилятора. Пример использования см. в разделе `__FUNCDNAME__` макрос.  
  
-   **_INTEGRAL_MAX_BITS** определенные как целое 64 литеральное значение, максимальный размер (в битах) для целочисленный тип не вектор. Этот макрос определяется всегда.  
  
    ```cpp  
    // integral_max_bits.cpp  
    #include <stdio.h>  
    int main() {  
       printf("%d\n", _INTEGRAL_MAX_BITS);  
    }  
    ```  
  
-   **__INTELLISENSE\_\_** определен как 1 во время компилятора IntelliSense передайте в Интегрированной среде разработки Visual Studio. В противном случае не определено. Этот макрос можно использовать для защиты кода компилятор IntelliSense не понимать и использовать его для переключения между сборки и компилятора IntelliSense. Дополнительные сведения см. в разделе [Советы по устранению неполадок для IntelliSense быстродействием](https://blogs.msdn.microsoft.com/vcblog/2011/03/29/troubleshooting-tips-for-intellisense-slowness/).  
  
-   **_ISO_VOLATILE** определяется как 1, если [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_KERNEL_MODE** определяется как 1, если [/kernel (Создание двоичного режима ядра)](../build/reference/kernel-create-kernel-mode-binary.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_M_AMD64** определен как целочисленный литерал, процессоров x64 значение 100 для компиляции. В противном случае не определено.  
  
-   **_M_ARM** определяется как целочисленное литеральное значение 7 для компиляций, предназначенных для процессоров ARM. В противном случае не определено.  
  
-   **_M_ARM_ARMV7VE** определяется как 1, если [/arch:ARMv7VE](../build/reference/arch-arm.md) задан параметр компилятора для компиляций, предназначенных для процессоров ARM. В противном случае не определено.  
  
-   **_M_ARM_FP** определяется как значение целочисленного литерала, указывающее, что [/arch](../build/reference/arch-arm.md) был задан параметр компилятора, если целевого объекта компиляции для процессоров ARM. В противном случае не определено.  
  
    -   В диапазоне 30-39, если не **/arch** был указан параметр ARM, установлено значение, указывающее, по умолчанию архитектура для ARM (`VFPv3`).  
  
    -   В диапазоне 40-49, если **/arch:VFPv4** был установлен.  
  
    -   В разделе [/arch (ARM)](../build/reference/arch-arm.md) для получения дополнительной информации.  
  
-   **_M_ARM64** определен как 1 для компиляций, предназначенных для 64-разрядных процессоров ARM. В противном случае не определено.  
  
-   **_M_CEE** определяется как 001 Если любой [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_M_CEE_PURE** определяется как 001 Если [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_M_CEE_SAFE** определяется как 001 Если [/CLR: safe](../build/reference/clr-common-language-runtime-compilation.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_M_FP_EXCEPT** определяется как 1, если [/fp: за исключением](../build/reference/fp-specify-floating-point-behavior.md) или [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_M_FP_FAST** определяется как 1, если [/fp: fast](../build/reference/fp-specify-floating-point-behavior.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_M_FP_PRECISE** определяется как 1, если [/fp: точный](../build/reference/fp-specify-floating-point-behavior.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_M_FP_STRICT** определяется как 1, если [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_M_IX86** определен как целочисленный литерал, процессоров x86 значение 600 компиляций. Этот макрос не определен для x64 или целевых объектов компиляции ARM.  
  
-   **_M_IX86_FP** определяется как значение целочисленного литерала, указывающее [/arch](../build/reference/arch-arm.md) параметра компилятора, который был установлен, или значение по умолчанию. Этот макрос определяется всегда, когда целевого объекта компиляции x86 процессора. В противном случае не определено. Если определена, значение равно:  
  
    -   0, если **/arch:IA32** был установлен параметр компилятора.  
  
    -   1, если **/arch:SSE** был установлен параметр компилятора.  
  
    -   2, если **/arch:SSE2**, **/arch: AVX** или **/arch:AVX2** был установлен параметр компилятора. Это значение используется по умолчанию, если **/arch** не был указан параметр компилятора. Когда **/arch: AVX** указан, макрос **__AVX\_\_** также определены. Когда **/arch:AVX2** указано, как **__AVX\_\_** и **__AVX2\_\_** также определены.  
  
    -   В разделе [/arch (x86)](../build/reference/arch-x86.md) Подробнее.  
  
-   **_M_X64** определен как целочисленный литерал, процессоров x64 значение 100 для компиляции. В противном случае не определено.  
  
-   **_MANAGED** определен как 1, если [/CLR](../build/reference/clr-common-language-runtime-compilation.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_MSC_BUILD** определяется как целочисленный литерал, содержащий элемент номер редакции номера версии компилятора. Номер редакции — номер версии разделенного четвертый элемент. Например, если номер версии компилятора Visual C++ 15.00.20706.01 **_MSC_BUILD** макрос равен 1. Этот макрос определяется всегда.  
  
-   **_MSC_EXTENSIONS** определяется как 1, если [/Ze (включить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) задан параметр компилятора, который используется по умолчанию. В противном случае не определено.  
  
-   **_MSC_FULL_VER** определен как целочисленный литерал, кодирует основной, вспомогательной и построения количество элементов номера версии компилятора. Номер версии, разделенного на первый элемент является основной номер, дополнительный номер — второй элемент и номер сборки — третий элемент. Например, если номер версии компилятора Visual C++ 15.00.20706.01 **_MSC_FULL_VER** макрос принимает значение 150020706. Введите **cl /?** из командной строки для просмотра номера версии компилятора. Этот макрос определяется всегда.  
  
-   **_MSC_VER** определяется как целочисленный литерал, кодирует количество элементов основной и дополнительный номера версии компилятора. Основной номер — номер версии, разделенного на первый элемент и дополнительный номер — второй элемент. Например, 17.00.51106.1 номер версии компилятора Visual C++ **_MSC_VER** макрос возвращает значение 1700. Введите **cl /?** из командной строки для просмотра номера версии компилятора. Этот макрос определяется всегда.  
  
-   **_MSVC_LANG** определяется как целочисленный литерал, указывающее стандарта языка C++, предназначенные для компилятора. При компиляции как C++ макрос при целочисленное литеральное значение 201402 [/std:c ++ 14](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) параметр компилятора задается значение, или по умолчанию и задано на более высокий, этот параметр не указан значения при [/std:c ++ последнюю](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) задан параметр компилятора. В противном случае — макроса не определено.  **_MSVC_LANG** макрос и [/std (укажите Стандартная версия языка)](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) Параметры компилятора, начиная с Visual Studio 2015 г. обновление 3.  
  
-   **__MSVC_RUNTIME_CHECKS** определяется как 1, если в одном из [/RTC](../build/reference/rtc-run-time-error-checks.md) задать параметры компилятора. В противном случае не определено.  
  
-   **_MT** определен как 1, если [/MD или/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (Многопоточная DLL) или [/MT или/MTd](../build/reference/md-mt-ld-use-run-time-library.md) указано (многопоточный). В противном случае не определено.  
  
-   **_NATIVE_WCHAR_T_DEFINED** определяется как 1, если [/Zc:](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_OPENMP** определяется как целого литерала 200203 дату спецификации OpenMP, реализуемой Visual C++, если [/OpenMP (Включение поддержки OpenMP 2.0)](../build/reference/openmp-enable-openmp-2-0-support.md) задан параметр компилятора. В противном случае не определено.  
  
    ```cpp  
    // _OPENMP_dir.cpp  
    // compile with: /openmp   
    #include <stdio.h>   
    int main() {  
       printf("%d\n", _OPENMP);  
    }  
    ```  
  
-   **_PREFAST\_** определяется как 1, если [/ analyze](../build/reference/analyze-code-analysis.md) задан параметр компилятора. В противном случае не определено.  
  
-   **__TIMESTAMP\_\_** определяется как строковый литерал, содержащий дату и время последнего изменения текущего файла исходного кода, в форме сокращенное, постоянное длину возвращаемых библиотеки времени выполнения C [asctime](../c-runtime-library/reference/asctime-wasctime.md) функции, например, `Fri 19 Aug 13:32:58 2016`. Этот макрос определяется всегда.  
  
-   **_VC_NODEFAULTLIB** определяется как 1, если [/Zl (опустить имя библиотеки по умолчанию)](../build/reference/zl-omit-default-library-name.md) задан параметр компилятора. В противном случае не определено.  
  
-   **_WCHAR_T_DEFINED** определяется как 1, если значение по умолчанию [/Zc:](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) задан параметр компилятора.  **_WCHAR_T_DEFINED** макрос определен, но не имеет значения при **/Zc:wchar_t-** задан параметр компилятора, и `wchar_t` определяется в системном файле заголовка, включенном в проект. В противном случае не определено.  
  
-   **_WIN32** определенные как 1, если целевого объекта компиляции не ARM 32-разрядной, 64-разрядных ARM, x86, или x 64. В противном случае не определено.  
  
-   **_WIN64** определен как 1 при 64-разрядной ARM или x64 целевого объекта компиляции. В противном случае не определено.  
  
-   **_WINRT_DLL** определен как 1, если скомпилировать как C++ и оба [/ZW (компиляция среды выполнения Windows)](../build/reference/zw-windows-runtime-compilation.md) и [/LD или /LDd](../build/reference/md-mt-ld-use-run-time-library.md) установлены параметры компилятора. В противном случае не определено.  
  
 Макросы препроцессора, используемый для определения версии библиотеки ATL и MFC, не являются предопределенными компилятором. Эти макросы определяются в заголовки, библиотеки, поэтому они не определены в директивах препроцессора до обязательный заголовок.  
  
-   **_ATL_VER** определен в \< atldef.h > как целочисленный литерал, кодирует ATL номер версии.  
  
-   **_MFC_VER** определен в \< afxver_.h > как целочисленный литерал, кодирует номером версии MFC.  
  
## <a name="see-also"></a>См. также  
 [Макросы (C/C++)](../Topic/Macros%20\(C-C++\).md)   
 [Операторы препроцессора](../preprocessor/preprocessor-operators.md)   
 [Директивы препроцессора](../preprocessor/preprocessor-directives.md)