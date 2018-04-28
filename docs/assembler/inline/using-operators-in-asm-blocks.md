---
title: __Asm 블록에서 연산자를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e1c7c4b8415655aff36327db9c6a9f866d82683
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="using-operators-in-asm-blocks"></a>__asm 블록에서 연산자 사용
## <a name="microsoft-specific"></a>Microsoft 전용  
 `__asm` 블록은와 같은 C 또는 c + + 특정 연산자를 사용할 수 없습니다는 **<<** 연산자입니다. 그러나 공유 하는 연산자 C 및 MASM에서와 같은 \* 연산자를 어셈블리 언어 연산자로 해석 됩니다. 예를 들어, 외부 프로그램 `__asm` 대괄호를 차단 (**[]**) 바깥쪽 C 배열에 있는 요소의 크기를 자동으로 배율을 조정 하는 배열 첨자로 해석 됩니다. `__asm` 블록 안에서 MASM 인덱스 연산자로 표시되며, 이 연산자는 임의의 데이터 개체 또는 레이블(배열만이 아님)로부터 크기를 조절하지 않은 바이트 오프셋을 만듭니다. 다음 코드에서는 차이점을 보여 줍니다.  
  
```  
int array[10];  
  
__asm mov array[6], bx ;  Store BX at array+6 (not scaled)  
  
array[6] = 0;         /* Store 0 at array+24 (scaled) */  
```  
  
 `array`에 대한 첫 번째 참조는 크기가 조정되지 않지만 두 번째 참조는 크기가 조정됩니다. 사용할 수 있는 참고는 **형식** 연산자 크기 조절을 하기 위해서를 상수에 기반 합니다. 예를 들어, 다음 문은 동일합니다.  
  
```  
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24  
  
array[6] = 0;                   /* Store 0 at array + 24 */  
```  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__asm 블록에서 C 또는 C++ 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)