---
title: "TN059: Использование макросов преобразования MFC из MBCS в Юникоде | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.mbcs
dev_langs:
- C++
helpviewer_keywords:
- MFCANS32.DLL
- Unicode [MFC], conversion macros
- Unicode [MFC], OLE interfaces
- conversion macros [MFC]
- converting Unicode
- MBCS [MFC], conversion macros
- macros [MFC], MBCS conversion macros
- TN059
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 45df45fe3d06e71b33c20ecd88d3f958a5673df1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>TN059. Использование макросов преобразования MFC из MBCS в Юникод
> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
 Эта заметка описывает, как использовать макросы преобразования MBCS в Юникод, который определен в AFXPRIV. З. Эти макросы наиболее полезны в тех случаях, если сделок вашего приложения непосредственно с OLE API или какой-либо причине, часто требуется для преобразования между Юникодом и многобайтовой Кодировки.  
  
## <a name="overview"></a>Обзор  
 В MFC 3.x, специальные библиотеки DLL были используется (MFCANS32. Библиотека DLL) для автоматического преобразования между Юникодом и многобайтовой Кодировки, когда вызов интерфейсов OLE. Эта библиотека DLL была практически прозрачный слой, на котором допускается OLE-приложения для записи так, будто API-интерфейсы OLE и интерфейсы MBCS, даже если они всегда отражают Юникода (за исключением Macintosh). При этом уровне удобный и разрешенные приложения, чтобы быстро перенести из Win16 в Win32 (MFC, Microsoft Word, Microsoft Excel и VBA, являются лишь некоторые из приложений Майкрософт, в которых используется эта технология), существовавший иногда значительно снижают производительность попаданий. По этой причине MFC 4.x не использует эту библиотеку DLL, вместо обращается напрямую к интерфейсов OLE Юникода. Чтобы сделать это, MFC должен преобразовать Юникод для многобайтовой Кодировки при вызовах OLE-интерфейс и часто необходимо преобразовать в MBCS в кодировке Юникод, при реализации интерфейса OLE. Чтобы решить эту проблему и эффективно, ряд макросов были созданы для облегчения этого преобразования.  
  
 Одним из самых серьезных препятствий создания набор макросов является выделения памяти. Так как не удается преобразовать строки в месте, необходимо выделить дополнительную память для хранения преобразованных результатов. Это могло быть сделано с код, аналогичный приведенному ниже:  
  
```  
// we want to convert an MBCS string in lpszA  
int nLen = MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    NULL,
    NULL);

LPWSTR lpszW = new WCHAR[nLen];  
MultiByteToWideChar(CP_ACP,
    0,   
    lpszA, -1,
    lpszW,
    nLen);

// use it to call OLE here  
pI->SomeFunctionThatNeedsUnicode(lpszW);

// free the string  
delete[] lpszW;  
```  
  
 Этот подход как ряд проблем. Основная проблема — это код, чтобы записывать, тестировать и отлаживать. То, что был выполнен вызов простая функция стала гораздо более сложной. Кроме того имеется значительное выполнения издержки при этом. У памяти в куче и освобождения каждый раз, когда выполняется преобразование. Наконец, приведенного выше кода необходимо иметь соответствующие `#ifdefs` добавлены для сборок Юникода и Macintosh (которые не требуют этого преобразования).  
  
 Решение, которое мы выпустили является создание некоторые макросы, которые (1) маска разницу между различными платформами и (2) используется схема распределения использовать память и 3) используются, легко вставить в существующий исходный код. Ниже приведен пример одного из определения:  
  
```  
#define A2W(lpa) (\  
 ((LPCSTR)lpa == NULL) NULL : (\  
    _convert = (strnlen(lpa)+1),\  
    AfxA2WHelper((LPWSTR) alloca(_convert*2),   
    lpa,
    _convert)\)\)  
```  
  
 С помощью этого макроса вместо приведенный выше код и вещи, выполняются гораздо проще:  
  
```  
// use it to call OLE here  
USES_CONVERSION;  
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```  
  
 Существуют дополнительные вызовы преобразование не требуется, когда использование макросов является простым и эффективным.  
  
 Реализация каждый макрос использует функцию _alloca() выделение памяти из стека вместо кучи. Выделение памяти из стека намного быстрее, чем выделение памяти в куче, а память автоматически освобождается при выходе из функции. Кроме того, макросы Избегайте вызова **MultiByteToWideChar** (или **WideCharToMultiByte**) более одного раза. Это делается путем выделения памяти немного больше, чем необходимо. Мы знаем, что MBC будут преобразованы в более одного **WCHAR** и что для каждой **WCHAR** мы будет иметь не более двух MBC байтов. Путем выделения немногим больше, чем необходимо, но достаточно всегда, сколько для обработки преобразования, второй вызов второй вызов функции преобразования позволяет избежать. Вызов вспомогательной функции **AfxA2Whelper** уменьшает количество отправок аргументов, которые необходимо выполнить, чтобы выполнить преобразование (это приведет к меньшего объема кода, чем при ее вызове **MultiByteToWideChar**напрямую).  
  
 Чтобы макросы места для хранения временных длиной, бывает необходимо объявить локальную переменную с именем _преобразовать, который делает это в каждой функции, используются макросы преобразования. Это делается путем вызова **определить USES_CONVERSION** макрос см. в примере выше.  
  
 Существуют макросов универсального преобразования и определенные макросы OLE. Эти два набора макрос, описаны ниже. AFXPRIV находятся все макросы. З.  
  
## <a name="generic-conversion-macros"></a>Макросы преобразования универсального  
 Макросы преобразования универсального образуют базового механизма. Пример макроса и реализации, показанный в предыдущем разделе, A2W, имеет один такой макрос «универсальный». Оно не связано с OLE специально. Набор макросов универсального перечисленные ниже.  
  
```  
A2CW      (LPCSTR) -> (LPCWSTR)  
A2W      (LPCSTR) -> (LPWSTR)  
W2CA      (LPCWSTR) -> (LPCSTR)  
W2A      (LPCWSTR) -> (LPSTR)  
```  
  
 Помимо выполнения преобразования текста, существуют также макросов и вспомогательные функции для преобразования `TEXTMETRIC`, `DEVMODE`, `BSTR`и OLE, выделенной строки. Эти макросы выходят за рамки данного обсуждения - ссылаться на AFXPRIV. H Дополнительные сведения об этих макросов.  
  
## <a name="ole-conversion-macros"></a>Макросы преобразования OLE  
 Макросы преобразования OLE предназначены специально для функций, которые ожидают обработки **OLESTR** символов. Если посмотреть на заголовках OLE, вы увидите много ссылок на **LPCOLESTR** и **olechar, КОТОРЫЕ**. Эти типы используются для ссылки на тип символов, используемых в интерфейсах OLE в виде, не относится к платформе. **Olechar, КОТОРЫЕ** сопоставляется `char` на платформах на базе Win16 и Macintosh и **WCHAR** в Win32.  
  
 Чтобы свести число **#ifdef** директивы в MFC в код как минимум у нас есть аналогичные макрос для каждого преобразования, включающих строки OLE. Наиболее часто используются следующие макросы:  
  
```  
T2COLE   (LPCTSTR) -> (LPCOLESTR)  
T2OLE   (LPCTSTR) -> (LPOLESTR)  
OLE2CT   (LPCOLESTR) -> (LPCTSTR)  
OLE2T   (LPCOLESTR) -> (LPCSTR)  
```  
  
 Опять же, существуют аналогичные макросы для этого `TEXTMETRIC`, `DEVMODE`, `BSTR`и OLE, выделенной строки. Обратитесь к AFXPRIV. H для получения дополнительной информации.  
  
## <a name="other-considerations"></a>Другие вопросы  
 Не используйте макросы в непрерывном цикле. Например не требуется написать следующий тип кода:  
  
```  
void BadIterateCode(LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    for (int ii = 0; ii <10000; ii++)  
    pI->SomeMethod(ii, T2COLE(lpsz));

}  
```  
  
 Приведенный выше код может привести к выделение памяти в стеке в зависимости от того, какое содержимое строки в мегабайтах `lpsz` —! Также требуется времени для преобразования строки для каждой итерации цикла. Вместо этого переместите таких преобразований константы из цикла:  
  
```  
void MuchBetterIterateCode(LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)  
    pI->SomeMethod(ii, lpszT);

}  
```  
  
 Если строка не является константой, затем инкапсулируют вызова метода в функцию. Это позволит буфера преобразования для освобождения каждый раз. Пример:  
  
```  
void CallSomeMethod(int ii, LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    pI->SomeMethod(ii, T2COLE(lpsz));

}  
 
void MuchBetterIterateCode2(LPCTSTR* lpszArray)  
{  
    for (int ii = 0; ii <10000; ii++)  
    CallSomeMethod(ii, lpszArray[ii]);

}  
```  
  
 Никогда не возвращают результат один из макросов, если возвращаемое значение подразумевает создание копии данных до возврата. Например этот код — плохо:  
  
```  
LPTSTR BadConvert(ISomeInterface* pI)  
{  
    USES_CONVERSION; 
    LPOLESTR lpsz = NULL;  
    pI->GetFileName(&lpsz);

 LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

 return lpszT; // bad! returning alloca memory  
}  
```  
  
 Приведенный выше код можно исправить, изменив значение в то, что копирует значение:  
  
```  
CString BetterConvert(ISomeInterface* pI)  
{  
    USES_CONVERSION; 
    LPOLESTR lpsz = NULL;  
    pI->GetFileName(&lpsz);

 LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

 return lpszT; // CString makes copy  
}  
```  
  
 Они просты в использовании и легко вставить в код, но как можно видеть из предупреждения выше, необходимо соблюдать осторожность при их использовании.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

