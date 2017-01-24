---
title: "컴파일러 경고(수준 4) C4754 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4754"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4754"
ms.assetid: e0e4606a-754a-4f42-a274-21a34978d21d
caps.latest.revision: 6
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 4) C4754
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비교에 사용된 산술 연산의 변환 규칙은 분기 하나를 실행할 수 없음을 의미합니다.  
  
 비교 결과 항상 동일하므로 C4754 경고가 발생합니다.  대부분 관련된 정수 식이 올바르지 않기 때문에 이 조건 중 하나가 실행되지 않았음을 의미합니다.  64비트 아키텍처에 대한 잘못된 정수 오버플로 검사에서 이 코드 오류가 종종 발생합니다.  
  
 정수 변환 규칙은 복잡하고 많은 미묘한 문제가 있습니다.  각 C4754 경고를 수정하는 대신, [SafeInt 라이브러리](../../windows/safeint-library.md)를 사용하여 코드를 업데이트할 수 있습니다.  
  
## 예제  
 이 샘플은 C2440을 생성합니다:  
  
```cpp  
// C4754a.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int sum_overflow(unsigned long a, unsigned long b)   
{  
   unsigned long long x = a + b; // C4754  
  
   if (x > 0xFFFFFFFF)   
   {  
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 추가  `a + b` 는 결과가 64비트 변수에 업캐스팅되거나, 64비트 값 `x` 으로 할당되기 전에 산술 오버플로가 발생할 수 있습니다.  즉  `x`  체크는 중복되고 절대로 catch 오버플로가 발생하지 않는 것을 의미합니다.  이 경우, 컴파일러가 이 경고를 내보냅니다:  
  
  **경고 C4754: C4754a.cpp \(7\)에 비교에 대한 산술 연산의 변환 규칙은 한 분기를 실행할 수 없음을 의미합니다.  '\(a \+ ...\)'에서 'ULONG64'로\(또는 비슷한 형식의 8바이트\) 캐스팅하십시오.**  8바이트 값으로 피연산자를 캐스팅하는 할당문으로 변경하면 이 경고를 제거할 수 있습니다.  
  
```cpp  
// Casting one operand is sufficient to force all the operands in   
// the addition be upcast according to C/C++ conversion rules, but  
// casting both is clearer.  
unsigned long long x =   
   (unsigned long long)a + (unsigned long long)b;  
```  
  
## 예제  
 다음 샘플에서도 C4754 오류가 발생하는 경우를 보여줍니다.  
  
```cpp  
// C4754b.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int wrap_overflow(unsigned long a)   
{  
   if (a + sizeof(unsigned long) < a) // C4754  
   {   
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 `sizeof()`  연산자는  `size_t` 로 반환되며, 그 크기는 아키텍처에 따라 다릅니다.  예제 코드는  `size_t` 가 32비트 형식인 32 비트 아키텍처에서 작동합니다.  그러나, 64 비트 아키텍처에선  `size_t` 는 64 비트 형식입니다.  정수에 대한 변환 규칙은  `(size_t)a + (size_t)b < (size_t)a` 가 작성 된 경우 처럼,  `a + b < a` 식에서  `a` 가 64 비트 값으로 업캐스팅되는 것을 의미합니다.     `a`  및  `b`  가 32 비트 정수일 때, 64 비트 연산은 오버플로할 수 없으며,  제약 조건을 포함하지 않습니다.  결과적으로, 코드는 64비트 아키텍처에서 정수 오버플로 상태를 검출할 수 없습니다.  컴파일러가 이 경고를 생성하는 예제입니다.  
  
  **경고 C4754: C4754b.cpp \(7\)에 비교에 대한 산술 연산의 변환 규칙은 한 분기를 실행할 수 없음을 의미합니다.  '4' 에서'ULONG'로 캐스팅합니다 \(또는 비슷한 종류의 4 바이트\).**  원래 소스 문자열 대신 경고 메시지가 상수 값 4을 명시적으로 나열하는지 확인하십시오— 경고분석이 문제를 일으키는 코드를 만날 쯤,  `sizeof(unsigned long)` 는 상수로 이미 변환됩니다.  따라서 ,경고 메시지에서 상수값과 연관된 소스에서 어떤 식을 추적해야합니다.  가장 일반적인 소스는  `sizeof(TYPE)`  및  `strlen(szConstantString)`  식과 같은 상수 C4754 경고 메시지에서 해석합니다 .  
  
 이 경우, 고정된 코드는 다음과 같습니다:  
  
```cpp  
// Casting the result of sizeof() to unsigned long ensures  
// that all the addition operands are 32-bit, so any overflow   
// is detected by the check.  
if (a + (unsigned long)sizeof(unsigned long) < a)  
  
```  
  
 **참고** 컴파일러 경고를 참조하는 줄 번호는 문의 마지막 줄입니다.  여러 줄에 걸쳐 분산되어 있어 복잡한 조건문에 대한 경고 메시지에서, 코드 오류가 있는 줄은 보고된 줄 이전의 몇몇의 줄일 수 있습니다.  예를 들면 다음과 같습니다.  
  
```cpp  
unsigned long a;  
  
if (a + sizeof(unsigned long) < a || // incorrect check  
    condition1() ||   
    a == 0) {    // C4754 warning reported on this line  
         // never executes!  
         return INVALID_PARAMETER;  
}  
  
```