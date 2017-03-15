---
title: "반환 값(C++) | Microsoft Docs"
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
ms.assetid: 53583524-b337-4228-a9c6-c9bf516babe8
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 반환 값(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

64비트에 맞는 스칼라 반환 값은 RAX를 통해 반환됩니다\(\_\_m64 형식 포함\).  Float, double 및 벡터 형식\(예: [\_\_m128](../cpp/m128.md), [\_\_m128i](../cpp/m128i.md), [\_\_m128d](../cpp/m128d.md)\)을 포함하는 스칼라 이외의 형식은 XMM0에 반환됩니다.  RAX 또는 XMM0에 반환되는 값에서 사용되지 않는 비트의 상태는 정의되지 않습니다.  
  
 사용자 정의 형식은 전역 함수 및 정적 멤버 함수 값으로 반환될 수 있습니다.  RAX에서 값으로 반환되려면 사용자 정의 형식의 길이가 1, 2, 4, 8, 16, 32 또는 64비트여야 하고 사용자 정의 생성자, 소멸자 또는 복사 할당 연산자, 전용 또는 보호된 비정적 데이터 멤버, 참조 형식의 비정적 데이터 멤버, 기본 클래스, 가상 함수나 이러한 요구를 충족하지 않는 데이터 멤버도 없어야 합니다.  이것은 기본적으로 C\+\+03 POD 형식의 정의입니다.  이 정의는 C\+\+11 표준에서 변경되었으므로 이 테스트에는 `std::is_pod`를 사용하지 않는 것이 좋습니다. 그렇지 않은 경우 호출자는 메모리를 할당하고 반환 값에 대한 포인터를 첫 번째 인수로 전달할 책임이 있다고 간주됩니다.  그런 다음 후속 인수가 오른쪽으로 하나씩 이동됩니다.  RAX에서 호출 수신자에 의해 동일한 포인터가 반환되어야 합니다.  
  
 이러한 예에서는 지정된 선언을 사용하여 함수에 대해 매개 변수 및 반환 값이 전달되는 방식을 보여 줍니다.  
  
## 반환 값 1의 예 – 64비트 결과  
  **\_\_int64 func1\(int a, float b, int c, int d, int e\);**  
**\/\/ 호출자는 RCX에서 a, XMM1에서 b, R8에서 c, R9에서 d, 스택에 푸시된 e를 전달합니다.**  
**\/\/ 호출 수신자가 RAX에서 \_\_int64 결과를 반환합니다.**   
## 반환 값 2의 예 – 128비트 결과  
  **\_\_m128 func2\(float a, double b, int c, \_\_m64 d\);**   
**\/\/ 호출자가 XMM0의 a, XMM1의 b, R8의 c, R9의 d를 전달합니다.**   
**\/\/ 호출 수신자가 XMM0에서 \_\_m128 결과를 반환합니다.**   
## 반환 값 3의 예 – 포인터별 사용자 형식 결과  
  **struct Struct1 {**  
 **int j, k, l;    \/\/ Struct1이 64비트를 초과합니다.  };**  
**Struct1 func3\(int a, double b, int c, float d\);**   
**\/\/ 호출자가 반환된 Struct1에 대한 메모리를 할당하고 RCX에서 포인터,**   
**\/\/ RDX에서 a, XMM2에서 b, R9에서 c, 스택에 푸시된 d를 전달합니다.**   
**\/\/ 호출 수신자가 RAX에서 Struct1 결과에 대한 포인터를 반환합니다.**    
## 반환 값 4의 예 – 값별 사용자 형식 결과  
  **struct Struct2 {**  
 **int j, k;    \/\/ Struct2는 64비트에 맞으며 값으로 반환에 대한 요구 사항을 충족합니다.  };**  
**Struct2 func4\(int a, double b, int c, float d\);**   
**\/\/ 호출자가 RCX에 a, XMM1b, R8에 c 및 XMM3에 d를 전달합니다.**   
**\/\/ 호출 수신자가 RAX에서 값으로 Struct2 결과를 반환합니다.**    
## 참고 항목  
 [호출 규칙](../build/calling-convention.md)