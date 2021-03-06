---
title: "Двоичные выходные файлы | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 932b2bdd756309fa4fb84f9cf2b06d171d299a43
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="binary-output-files"></a>Двоичные выходные файлы
Потоки изначально были разработаны для текста, поэтому по умолчанию установлен режим вывода текста. В текстовом режиме символ перевода строки (шестнадцатеричное 10) расширяется для возврата каретки (только 16-разрядный). Расширение может вызвать проблемы, как показано ниже:  
  
```  
// binary_output_files.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
int main( )  
{  
    ofstream os( "test.dat" );  
    os.write( (char *) iarray, sizeof( iarray ) );  
}  
```  
  
 Можно предположить, что эта программа будет выводить байтовую последовательность {99, 0, 10, 0}; вместо этого она выводит {99, 0, 13, 10, 0}, что приводит к проблемам в программе, ожидающей ввод двоичных данных. Если требуются настоящие двоичные входные денные, в которых символы записаны непреобразованными, можно указать вывод двоичных данных с помощью аргумента openmode конструктора [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream):  
  
```  
// binary_output_files2.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
  
int main()  
{  
   ofstream ofs ( "test.dat", ios_base::binary );  
  
   // Exactly 8 bytes written  
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );   
}  
```  
  
## <a name="see-also"></a>См. также  
 [Потоки вывода](../standard-library/output-streams.md)

