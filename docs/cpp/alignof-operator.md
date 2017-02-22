---
title: "__alignof 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__alignof"
  - "alignof"
  - "alignas"
  - "__alignof_cpp"
  - "alignof_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__alignof 키워드[C++]"
  - "alignas"
  - "구조체 맞춤"
  - "alignof"
  - "형식[C++], 맞춤 요구 사항"
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# __alignof 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+11에서는 지정된 형식의 맞춤\(바이트\)을 반환하는 `alignof` 연산자를 소개합니다.  최대 이식성을 제공하려면 Microsoft 전용 \_\_alignof 연산자가 아닌 alignof 연산자를 사용해야 합니다.  
  
 **Microsoft 전용**  
  
 형식의 맞춤 요구 사항인 **size\_t** 형식의 값을 반환합니다.  
  
## 구문  
  
```  
  
        __alignof(   
   type    
)  
```  
  
## 설명  
 예:  
  
|식|값|  
|-------|-------|  
|**\_\_alignof\( char \)**|1|  
|**\_\_alignof\( short \)**|2|  
|**\_\_alignof\( int \)**|4|  
|**\_\_alignof\( \_\_int64 \)**|8|  
|**\_\_alignof\( float \)**|4|  
|**\_\_alignof\( double \)**|8|  
|**\_\_alignof\( char\* \)**|4|  
  
 `__alignof` 값은 기본 유형에 대해 `sizeof`의 값과 동일합니다.  그러나 다음과 같은 예제를 고려해야 합니다.  
  
```  
typedef struct { int a; double b; } S;  
// __alignof(S) == 8  
```  
  
 이 경우 `__alignof` 값은 구조에서 가장 큰 요소의 맞춤 요구 사항입니다.  
  
 마찬가지로  
  
```  
typedef __declspec(align(32)) struct { int a; } S;  
```  
  
 `__alignof(S)`가 `32`와 같은 경우  
  
 `__alignof`를 한 번 사용하면 자신의 메모리 할당 루틴 중 하나의 매개 변수가 됩니다.  예를 들어, 다음의 정의된 구조인 `S`가 지정된 경우 `aligned_malloc`이라는 메모리 할당 루틴을 호출하여 특정한 할당 경계에서 메모리를 할당할 수 있습니다.  
  
```  
typedef __declspec(align(32)) struct { int a; double b; } S;  
int n = 50; // array size  
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));  
```  
  
 맞춤 수정에 대한 자세한 내용은 다음을 참조하세요.  
  
-   [pack](../preprocessor/pack.md)  
  
-   [맞춤](../cpp/align-cpp.md)  
  
-   [\_\_unaligned](../cpp/unaligned.md)  
  
-   [\/Zp\(구조체 멤버 맞춤\)](../build/reference/zp-struct-member-alignment.md)  
  
-   [구조체 맞춤 예제](../build/examples-of-structure-alignment.md)\(x64 전용\)  
  
 X86 및 x64 관련 코드에서 맞춤의 차이점에 대한 자세한 내용은 다음을 참조하세요.  
  
-   [x86 컴파일러와 충돌](../build/conflicts-with-the-x86-compiler.md)  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)