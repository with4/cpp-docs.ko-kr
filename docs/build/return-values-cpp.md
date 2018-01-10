---
title: "반환 값 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 53583524-b337-4228-a9c6-c9bf516babe8
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cdd02ab9c30e641ba7389923062f46dbbed534ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="return-values-c"></a>반환 값(C++)
64비트에 맞는 스칼라 반환 값은 RAX를 통해 반환됩니다(__m64 형식 포함). Float, double 및 벡터 형식 등을 포함 하는 스칼라 이외의 형식은 [__m128](../cpp/m128.md), [__m128i](../cpp/m128i.md), [__m128d](../cpp/m128d.md) m m 0에 반환 됩니다. RAX 또는 XMM0에 반환되는 값에서 사용되지 않는 비트의 상태는 정의되지 않습니다.  
  
 사용자 정의 형식은 전역 함수 및 정적 멤버 함수 값으로 반환될 수 있습니다. RAX에서 값으로 반환되려면 사용자 정의 형식의 길이가 1, 2, 4, 8, 16, 32 또는 64비트여야 하고 사용자 정의 생성자, 소멸자 또는 복사 할당 연산자, 전용 또는 보호된 비정적 데이터 멤버, 참조 형식의 비정적 데이터 멤버, 기본 클래스, 가상 함수나 이러한 요구를 충족하지 않는 데이터 멤버도 없어야 합니다. 이것은 기본적으로 C++03 POD 형식의 정의입니다. 이 정의는 C++11 표준에서 변경되었으므로 이 테스트에는 `std::is_pod`를 사용하지 않는 것이 좋습니다. 그렇지 않은 경우 호출자는 메모리를 할당하고 반환 값에 대한 포인터를 첫 번째 인수로 전달할 책임이 있다고 간주됩니다. 그런 다음 후속 인수가 오른쪽으로 하나씩 이동됩니다. RAX에서 호출 수신자에 의해 동일한 포인터가 반환되어야 합니다.  
  
 이러한 예에서는 지정된 선언을 사용하여 함수에 대해 매개 변수 및 반환 값이 전달되는 방식을 보여 줍니다.  
  
## <a name="example-of-return-value-1---64-bit-result"></a>반환 값 1-64 비트 결과의 예  
  
```Output  
__int64 func1(int a, float b, int c, int d, int e);  
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,  
// callee returns __int64 result in RAX.  
```  
  
## <a name="example-of-return-value-2---128-bit-result"></a>예 2-128 비트 결과 반환 값  
  
```Output  
__m128 func2(float a, double b, int c, __m64 d);   
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,   
// callee returns __m128 result in XMM0.  
```  
  
## <a name="example-of-return-value-3---user-type-result-by-pointer"></a>반환 값 3-포인터 별 사용자 형식 결과의 예  
  
```Output  
struct Struct1 {  
   int j, k, l;    // Struct1 exceeds 64 bits.   
};  
Struct1 func3(int a, double b, int c, float d);   
// Caller allocates memory for Struct1 returned and passes pointer in RCX,   
// a in RDX, b in XMM2, c in R9, d pushed on the stack;   
// callee returns pointer to Struct1 result in RAX.  
```  
  
## <a name="example-of-return-value-4---user-type-result-by-value"></a>반환 값 4-값별 사용자 형식 결과의 예  
  
```Output  
struct Struct2 {  
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.  
};  
Struct2 func4(int a, double b, int c, float d);   
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;   
// callee returns Struct2 result by value in RAX.  
```  
  
## <a name="see-also"></a>참고 항목  
 [호출 규칙](../build/calling-convention.md)