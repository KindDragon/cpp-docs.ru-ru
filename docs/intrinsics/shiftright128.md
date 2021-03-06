---
title: "__shiftright128 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __shiftright128
dev_langs:
- C++
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 56fbd52709addbba414d6c6fc839baf96f0b2c02
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="shiftright128"></a>__shiftright128
**Блок, относящийся только к системам Microsoft**  
  
 Сдвигает 128-разрядную величину, представленную в виде двух 64-разрядныхвеличин `HighPart``LowPart`и , `Shift` вправо на количество разрядов, указанное в  и возвращает младшие 64 разряда результата.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned __int64 __shiftright128(   
   unsigned __int64 LowPart,   
   unsigned __int64 HighPart,   
   unsigned char Shift   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `LowPart`  
 Младшие 64 разряда 128-разрядной величины для сдвига.  
  
 [in] `HighPart`  
 Старшие 64 разряда 128-разрядной величины для сдвига.  
  
 [in] `Shift`  
 Число разрядов для поворота.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Младшие 64 разряда результата.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__shiftright128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Это значение `Shift` всегда берется по модулю 64, и, например, при вызове `__shiftright128(0, 1, 64)`, функция будет сдвигать вправо старшую часть `0` разрядов и возвращать младшую часть `0`, а не `1`, как в противном случае можно было ожидать.  
  
## <a name="example"></a>Пример  
 Пример см. в разделе [__shiftleft128](../intrinsics/shiftleft128.md).  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__shiftleft128](../intrinsics/shiftleft128.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)