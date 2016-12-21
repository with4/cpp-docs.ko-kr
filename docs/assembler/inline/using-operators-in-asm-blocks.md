---
title: "__asm 블록에서 연산자 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm 키워드[C++], 연산자"
  - "대괄호 [ ]"
  - "대괄호 [ ], __asm 블록"
  - "연산자[C++], __asm 블록에서 사용"
  - "대괄호 [ ]"
  - "대괄호 [ ], __asm 블록"
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __asm 블록에서 연산자 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 `__asm` 블록은 **\<\<** 연산자와 같은 C 또는 C\+\+ 관련 연산자를 사용할 수 없습니다.  하지만 \* 연산자와 같이 C 및 MASM에서 공유하는 연산자는 어셈블리 언어 연산자로 해석됩니다.  예를 들어, `__asm` 블록 바깥쪽의 닫는 대괄호\(**\[ \]**\)는 C가 배열에 있는 요소의 크기를 자동으로 조정하는 바깥쪽 배열 첨자로 해석됩니다.  `__asm` 블록 안에서 MASM 인덱스 연산자로 표시되며, 이 연산자는 임의의 데이터 개체 또는 레이블\(배열만이 아님\)로부터 크기를 조절하지 않은 바이트 오프셋을 만듭니다.  다음 코드에서는 차이점을 보여 줍니다.  
  
```  
int array[10];  
  
__asm mov array[6], bx ;  Store BX at array+6 (not scaled)  
  
array[6] = 0;         /* Store 0 at array+24 (scaled) */  
```  
  
 `array`에 대한 첫 번째 참조는 크기가 조정되지 않지만 두 번째 참조는 크기가 조정됩니다.  상수를 기반으로 크기 조절을 하기 위해서 **TYPE** 연산자를 사용할 수 있습니다.  예를 들어, 다음 문은 동일합니다.  
  
```  
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24  
  
array[6] = 0;                   /* Store 0 at array + 24 */  
```  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_asm 블록에서 C 또는 C\+\+ 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)