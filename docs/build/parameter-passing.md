---
title: "매개 변수 전달 | Microsoft Docs"
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
ms.assetid: e838ee5f-c2fe-40b0-9a23-8023c949c820
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 매개 변수 전달
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

처음 네 개의 정수 인수는 레지스터에 전달 됩니다.  정수 값 RCX, RDX, R8 및 R9 왼쪽에서 오른쪽으로 순서 대로 전달 됩니다.  5 인수가 높을수록 스택에 전달 됩니다.  모든 인수는 레지스터에서 오른쪽 정렬입니다.  이렇게 하면 필요한 경우 호출 수신자가 레지스터의 상위 비트를 무시하고 레지스터의 필요한 부분에만 액세스할 수 있습니다.  
  
 부동 소수점 및 배정밀도 인수는 무시되는 해당 카디널 슬롯\(예제 참조\)에 일반적으로 사용되는 정수 슬롯\(RCX, RDX, R8 및 R9\)의 XMM0 – XMM3\(최대 4\)에 전달됩니다. 그 반대의 경우도 마찬가지입니다.  
  
 [\_\_m128](../cpp/m128.md)형식, 배열 및 문자열은 직접 값으로 전달 되지 않지만 호출자가 할당 한 메모리에 포인터가 대신 전달 됩니다.  같은 크기의 정수 처럼 구조체\/공용 구조체의 크기가 8, 16, 32 또는 64 비트 및 \_\_m64 전달 됩니다.  이 크기가 이와 다른 구조체\/공용 구조체는 호출자가 할당 한 메모리에 포인터로 전달 됩니다.  \_\_m128을 비롯하여 포인터로 전달되는 이와 같은 집합체 형식의 경우 호출자가 할당하는 임시 메모리는 16바이트로 맞춰집니다.  
  
 컴파일러와 내장 함수 구현은 서로 밀접하게 연관되어 있으므로 스택 공간을 할당하지 않고 다른 함수를 호출하지도 않는 내장 함수는 다른 volatile 레지스터를 사용하여 레지스터 인수를 추가로 전달할 수 있습니다.  이를 활용하면 성능을 더욱 향상시킬 수 있습니다.  
  
 호출 수신자는 필요한 경우 레지스터 매개 변수를 숨겨진 공간으로 덤프해야 합니다.  
  
 다음 표에는 매개 변수가 전달되는 방식에 대한 설명이 간략하게 나와 있습니다.  
  
|매개 변수 형식|전달 방법|  
|--------------|-----------|  
|부동 소수점|처음 4개의 매개 변수 – XMM0에서 XMM3까지.  다른 매개 변수는 스택에 전달됩니다.|  
|Integer|처음 4개의 매개 변수 \- RCX, RDX, R8, R9.  다른 매개 변수는 스택에 전달됩니다.|  
|집합체\(8, 16, 32 또는 64비트\) 및 \_\_m64|처음 4개의 매개 변수 \- RCX, RDX, R8, R9.  다른 매개 변수는 스택에 전달됩니다.|  
|집합체\(기타\)|포인터로 전달.  처음 4개의 매개 변수는 RCX, RDX, R8 및 R9에 포인터로 전달됩니다.|  
|\_\_m128|포인터로 전달.  처음 4개의 매개 변수는 RCX, RDX, R8 및 R9에 포인터로 전달됩니다.|  
  
## 인수 전달 예제 1 \- 모두 정수  
  
```  
func1(int a, int b, int c, int d, int e);    
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack  
```  
  
## 인수 전달 예제 2 \- 모두 부동 소수점  
  
```  
func2(float a, double b, float c, double d, float e);    
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack  
```  
  
## 인수 전달 예제 3 \- 정수 및 부동 소수점 혼합  
  
```  
func3(int a, double b, int c, float d);    
// a in RCX, b in XMM1, c in R8, d in XMM3  
```  
  
## 인수 전달 예제 4 –\_\_m64, \_\_m128 및 집합체  
  
```  
func4(__m64 a, _m128 b, struct c, float d);  
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3  
```  
  
## 참고 항목  
 [호출 규칙](../build/calling-convention.md)