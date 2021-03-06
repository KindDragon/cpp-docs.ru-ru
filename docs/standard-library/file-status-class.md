---
title: "Класс file_status | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
dev_langs:
- C++
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.workload:
- cplusplus
ms.openlocfilehash: 406a747948276aecf30dcfbf88ffc870bb5804a3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="filestatus-class"></a>Класс file_status
Создает оболочку для [file_type](../standard-library/filesystem-enumerations.md#file_type) и [perms](../standard-library/filesystem-enumerations.md#perms).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class file_status;  
```  
  
## <a name="filestatusfilestatus"></a>file_status::file_status  
  
```cpp  
explicit file_status(  
   file_type ftype = file_type::none,  
   perms mask = perms::unknown) noexcept;  
  
file_status(const file_status&) noexcept = default;  
  
file_status(file_status&&) noexcept = default; 

~file_status() noexcept = default; 
```  
  
## <a name="filestatusoperator"></a>file_status::operator=  
  
```cpp  
file_status& operator=(const file_status&) noexcept = default;  
file_status& operator=(file_status&&) nexcept = default;  
```  
  
 Операторы-члены присваивания по умолчанию работают корректно.  
  
## <a name="type"></a>type  
  
```cpp  
file_type type() const noexcept  
void type(file_type ftype) noexcept  
```  
  
 Возвращает или задает file_type.  
  
## <a name="permissions"></a>permissions  
  
```cpp  
perms permissions() const noexcept  
void permissions(perms mask) noexcept   
```  
  
 Возвращает или задает разрешения для файла.  
  
 Используйте метод задания, чтобы сделать файл доступным только для чтения или удалить атрибут "только для чтения".  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<filesystem >  
  
 **Namespace:** std::experimental::filesystem, std::experimental::filesystem  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Класс Path](../standard-library/path-class.md)   
 [\<filesystem>](../standard-library/filesystem.md)

