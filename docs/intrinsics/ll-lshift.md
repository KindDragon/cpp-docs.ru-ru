---
title: "__ll_lshift | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
dev_langs:
- C++
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df8aed34d31fe1675dc13d0c040c1a9f0b1f208e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="lllshift"></a>__ll_lshift
**Блок, относящийся только к системам Microsoft**  
  
 Сдвигает указанное 64-разрядное значение влево на указанное число битов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned __int64 __ll_lshift(  
   unsigned __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Mask`  
 64-разрядное целое значение для сдвига влево.  
  
 [in] `nBit`  
 Число разрядов для поворота.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Маска сдвиг влево по `nBit` bits.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__ll_lshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 При компиляции программы с помощью 64-разрядной архитектуры и `nBit` больше, чем 63, число разрядов для поворота `nBit` по модулю 64. При компиляции программы с помощью 32-разрядной архитектуры и `nBit` больше, чем 31, число разрядов для поворота `nBit` остаток от деления 32.  
  
 `ll` В имени указывает, что операции на `long long` (`__int64`).  
  
## <a name="example"></a>Пример  
  
```  
// ll_lshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_lshift)  
  
int main()  
{  
   unsigned __int64 Mask = 0x100;  
   int nBit = 8;  
   Mask = __ll_lshift(Mask, nBit);  
   cout << hex << Mask << endl;  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
10000  
```  
  
 **Примечание** отсутствует версия без знака операции сдвига влево. Это вызвано `__ll_lshift` уже использует неподписанные входной параметр. В отличие от сдвига вправо отсутствует зависимость входа для сдвига влево, так как младший значащий бит в результате всегда равно нулю, независимо от знака значения сдвиг.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)