---
title: "Определения типов &lt;fstream&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 5e0c09cdef9a20d7614f26189f34a5302b46a3ff
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltfstreamgt-typedefs"></a>Определения типов &lt;fstream&gt;
||||  
|-|-|-|  
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|  
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|  
|[wifstream](#wifstream)|[wofstream](#wofstream)|  
  
##  <a name="filebuf"></a>  filebuf  
 Тип `basic_filebuf`, специализированный на параметрах шаблона `char`.  
  
```
typedef basic_filebuf<char, char_traits<char>> filebuf;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_filebuf](../standard-library/basic-filebuf-class.md), специализированного для элементов типа `char` с признаками символа по умолчанию.  
  
##  <a name="fstream"></a>  fstream  
 Тип `basic_fstream`, специализированный на параметрах шаблона `char`.  
  
```
typedef basic_fstream<char, char_traits<char>> fstream;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_fstream](../standard-library/basic-fstream-class.md), специализированного для элементов типа `char` с признаками символа по умолчанию.  
  
##  <a name="ifstream"></a>  ifstream  
 Определяет поток, который используется для последовательного чтения однобайтовых символов из файла. `ifstream` — это определение typedef, которое специализирует класс шаблона `basic_ifstream` для `char`.  
  
 Также существует `wifstream` — определение typedef, которое специализирует `basic_ifstream` для чтения двухбайтовых символов `wchar_t`. Дополнительные сведения см. в описании [wifstream](../standard-library/fstream-typedefs.md#wifstream).  
  
```
typedef basic_ifstream<char, char_traits<char>> ifstream;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона `basic_ifstream`, специализированного для элементов типа char с признаками символа по умолчанию. Пример:  
  
 `using namespace std;`  
  
 `ifstream infile("existingtextfile.txt");`  
  
 `if (!infile.bad())`  
  
 `{`  
  
 `// Dump the contents of the file to cout.`  
  
 `cout << infile.rdbuf();`  
  
 `infile.close();`  
  
 `}`  
  
##  <a name="ofstream"></a>  ofstream  
 Тип `basic_ofstream`, специализированный на параметрах шаблона `char`.  
  
```
typedef basic_ofstream<char, char_traits<char>> ofstream;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_ofstream](../standard-library/basic-ofstream-class.md), специализированного для элементов типа `char` с признаками символа по умолчанию.  
  
##  <a name="wfstream"></a>  wfstream  
 Тип `basic_fstream`, специализированный на параметрах шаблона `wchar_t`.  
  
```
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_fstream](../standard-library/basic-fstream-class.md), специализированного для элементов типа `wchar_t` с признаками символа по умолчанию.  
  
##  <a name="wifstream"></a>  wifstream  
 Тип `basic_ifstream`, специализированный на параметрах шаблона `wchar_t`.  
  
```
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_ifstream](../standard-library/basic-ifstream-class.md), специализированного для элементов типа `wchar_t` с признаками символа по умолчанию.  
  
##  <a name="wofstream"></a>  wofstream  
 Тип `basic_ofstream`, специализированный на параметрах шаблона `wchar_t`.  
  
```
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_ofstream](../standard-library/basic-ofstream-class.md), специализированного для элементов типа `wchar_t` с признаками символа по умолчанию.  
  
##  <a name="wfilebuf"></a>  wfilebuf  
 Тип `basic_filebuf`, специализированный на параметрах шаблона `wchar_t`.  
  
```
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом класса шаблона [basic_filebuf](../standard-library/basic-filebuf-class.md), специализированного для элементов типа `wchar_t` с признаками символа по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [\<fstream>](../standard-library/fstream.md)



