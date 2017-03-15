---
title: "인라인 어셈블리로 함수 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm 키워드[C++], in 함수"
  - "어셈블러[C++], 함수 작성"
  - "함수[C++], 인라인 어셈블리"
  - "인라인 어셈블리[C++], 함수 작성"
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 인라인 어셈블리로 함수 작성
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 관련  
 인라인 어셈블리 코드를 사용 하 여 함수를 작성 하면 함수에 인수를 전달 하 고 값을 반환 하기 쉽습니다.  다음 예제에서는 인라인 어셈블러를 다시 작성 한 다음 먼저 다른 어셈블러 용으로 작성 된 함수를 비교 합니다.  호출 되는 함수를  `power2`, 2의 두 번째 매개 변수를 첫 번째 매개 변수를 곱하는 매개 변수로 받습니다.  별도 어셈블러를 작성 함수는 다음과 같습니다.  
  
```  
; POWER.ASM  
; Compute the power of an integer  
;  
       PUBLIC _power2  
_TEXT SEGMENT WORD PUBLIC 'CODE'  
_power2 PROC  
  
        push ebp        ; Save EBP  
        mov ebp, esp    ; Move ESP into EBP so we can refer  
                        ;   to arguments on the stack  
        mov eax, [ebp+4] ; Get first argument  
        mov ecx, [ebp+6] ; Get second argument  
        shl eax, cl     ; EAX = EAX * ( 2 ^ CL )  
        pop ebp         ; Restore EBP  
        ret             ; Return with sum in EAX  
  
_power2 ENDP  
_TEXT   ENDS  
        END  
```  
  
 별도 어셈블러를 작성 하므로 함수는 별도 소스 파일 및 어셈블리와 연결 단계가 필요 합니다.  C 및 c \+ \+ 함수 인수는 스택에 전달 일반적으로 지금이 버전은  `power2`인수는 스택의 해당 위치에 액세스 하는 함수.  \(이때의  **모델** 기타 조립 및 MASM 지시문도 스택의 인수 및 지역 스택 변수를 이름으로 액세스할 수 있습니다.\)  
  
## 예제  
 이 프로그램이 기록 된  `power2`인라인 어셈블리 코드를 사용 하 여 함수:  
  
```  
// Power2_inline_asm.c  
// compile with: /EHsc  
// processor: x86  
  
#include <stdio.h>  
  
int power2( int num, int power );  
  
int main( void )  
{  
    printf_s( "3 times 2 to the power of 5 is %d\n", \  
              power2( 3, 5) );  
}  
int power2( int num, int power )  
{  
   __asm  
   {  
      mov eax, num    ; Get first argument  
      mov ecx, power  ; Get second argument  
      shl eax, cl     ; EAX = EAX * ( 2 to the power of CL )  
   }  
   // Return with result in EAX  
}  
```  
  
 인라인 버전의  `power2`함수 인수를 이름으로 참조 하 고 프로그램의 나머지와 동일한 소스 파일에 표시 합니다.  이 버전 어셈블리 명령을 더 적게 필요합니다.  
  
 때문에 인라인 버전의  `power2`는 C를 실행 하지 않습니다  `return`문 하면 무해 한 경고 2 또는 더 높은 경고 수준에서 컴파일하면.  반환 값을 않습니다 있지만 컴파일러가 없을 경우에는 알 수 없습니다에  `return`문.  사용할 수  [\#pragma 경고](../../preprocessor/warning.md) 이 경고를 생성 하지 않으려면.  
  
 **Microsoft 특정 끝**  
  
## 참고 항목  
 [\_\_asm 블록에서 C 또는 C\+\+ 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)