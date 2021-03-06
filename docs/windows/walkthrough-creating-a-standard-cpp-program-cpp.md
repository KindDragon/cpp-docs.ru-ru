---
title: "Пошаговое руководство: Создание стандартной программы C++ (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords:
- vcfirstapp
- vccreatefirst
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 52066be1d67bddb7173841e9df6c5013c86ac0dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>Пошаговое руководство: Создание стандартной программы C++ (C++)
Для создания программ Standard C++ можно использовать Visual C++ в среде разработки Visual Studio (IDE). Выполнив действия, описанные в этом пошаговом руководстве, можно создать проект, добавьте в проект новый файл, измените файл для добавления кода C++ и последующей компиляции и запустите программу с помощью [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
 Можно ввести собственную программу C++ или использовать один из примеров программ. Образец программы в этом пошаговом руководстве представляет собой консольное приложение. В данном приложении используется `set` контейнера в стандартной библиотеке C++.  
  
 Visual C++ соответствует стандарту языка C++ 2003, со следующими основными исключениями: поиск имени в два этапа, а также спецификации исключений и экспорт. Кроме того Visual C++ поддерживает несколько функций C ++ 0 x, например, лямбда-выражения, auto, static_assert, ссылки rvalue и шаблоны extern.  
  
> [!NOTE]
>  Если требуется совместимость со стандартом, используйте **/Za** параметр компилятора, чтобы отключить расширения Microsoft к стандарту. Дополнительные сведения см. в разделе [/Za, /Ze (отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения этого пошагового руководства читатель должен владеть основами языка C++.  
  
### <a name="to-create-a-project-and-add-a-source-file"></a>Создание проекта и добавление исходного файла  
  
1.  Создайте проект, выбрав пункт **New** на **файл** меню и выбрав **проекта**.  
  
2.  В **Visual C++** проекта «типы», нажмите кнопку **Win32**, а затем нажмите кнопку **консольное приложение Win32**.  
  
3.  Введите имя для проекта.  
  
     По умолчанию, содержащее проект решение имеет имя, совпадающее с именем проекта, но можно ввести другое имя. Можно также ввести другое расположение для проекта.  
  
     Нажмите кнопку **ОК** для создания проекта.  
  
4.  В **мастер приложений Win32**, нажмите кнопку **Далее**выберите **пустой проект**, а затем нажмите кнопку **Готово**.  
  
5.  Если **обозревателе решений** не отображается, в **представление** меню, нажмите кнопку **обозревателе решений**.  
  
6.  Добавьте новый исходный файл в проект, следующим образом.  
  
    1.  В **обозреватель решений**, щелкните правой кнопкой мыши **исходные файлы** папку, выберите пункт **добавить**, а затем нажмите кнопку **новый элемент**.  
  
    2.  В **кода** узел, щелкните **файл C++ (.cpp)**, введите имя файла и нажмите кнопку **добавить**.  
  
     В CPP-файл появится в папке исходных файлов в **обозревателе решений**, и файл открыт в редакторе Visual Studio.  
  
7.  В файл в редакторе введите допустимый программы C++, которая использует стандартную библиотеку C++, или скопировать один из примеров программ и вставьте его в файл.  
  
8.  Сохраните файл.  
  
9. В меню **Сборка** выберите **Собрать решение**.  
  
     **Вывода** окне отображаются сведения о ходе выполнения компиляции, например, расположение журнала построения и сообщение о состоянии построения.  
  
10. На **отладки** меню, нажмите кнопку **Запуск без отладки**.  
  
     Если используется пример программы, окно командной строки отображается и показывает, находятся ли определенные целые числа в наборе.  
  
## <a name="next-steps"></a>Следующие шаги  
 **Предыдущие:** [консольных приложений в Visual C++](../windows/console-applications-in-visual-cpp.md). **Далее:**[Пошаговое руководство: компиляция программы на машинном коде C++ в командной строке](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)