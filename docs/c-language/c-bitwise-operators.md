---
title: "C 비트 연산자 | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "& 연산자, 비트 연산자"
  - "^ 연산자"
  - "^ 연산자, 비트 연산자"
  - "| 연산자, 비트 연산자"
  - "앰퍼샌드 연산자(&)"
  - "AND 연산자"
  - "비트 연산자"
  - "비트 연산자, Visual C"
  - "연산자[C], 비트"
ms.assetid: e22127b1-9a2d-4876-b01d-c8f72cec3317
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 비트 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비트 연산자는 비트 수행\-고 \(**&**\), 비트 배타적 OR \(**^**\), 및\-이상\-OR \(       **&#124;** \) 작업.  
  
 **구문**  
  
 *AND\-expression*:  
 *equality\-expression*  
  
 *AND\-expression*  **&**  *equality\-expression*  
  
 *exclusive\-OR\-expression*:  
 *AND\-expression*  
  
 *exclusive\-OR\-expression*  **^**  *AND\-expression*  
  
 *inclusive\-OR\-expression*:  
 *exclusive\-OR\-expression*  
  
 *inclusive\-OR\-expression* &#124; *exclusive\-OR\-expression*  
  
 비트 연산자의 피연산자는 정수 계열 형식이 있어야 하지만 그 종류는 다를 수 있습니다.  이 연산자들은 통상적인 연산 변환을 실행하며, 결과의 유형은 변환 이후 좌측 피연산 함수의 유형입니다.  
  
 C 논리 연산자는 다음과 같습니다.  
  
|연산자|설명|  
|---------|--------|  
|**&**|비트 단위의 AND 연산자\(&\)는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교합니다.  양쪽 비트가 모두 1이면 해당 결과 비트는 1로 설정됩니다.  그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.|  
|**^**|비트 단위의 독점적 OR 연산자\(^\)는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교합니다.  한 비트가 0이고 다른 비트가 1인 경우 해당 결과 비트는 1로 설정됩니다.  그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.|  
|**&#124;**|비트 단위의 독점적 OR 연산자\(^\)는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교합니다.  어느 한쪽 비트가 1이면 해당 결과 비트는 1로 설정됩니다.  그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.|  
  
## 예제  
 이러한 선언은 다음 세 가지 예에 사용 됩니다.  
  
```  
short i = 0xAB00;  
short j = 0xABCD;  
short n;  
  
n = i & j;  
```  
  
 `n` 이 첫 번째 예제에서 할당된 값은 `i` \(16 진수 0xAB00\)와 같습니다.  
  
```  
n = i | j;  
  
n = i ^ j;  
```  
  
 두 번째 예제에서 포함 비트 OR는 0xABCD \(16 진수\) 값에서 결과가 나오는 반면, 예제 3 비트 배타적 OR은 0xCD\(16 진수\)를 낳습니다.  
  
 **Microsoft 전용**  
  
 부호 있는 정수에 비트 연산의 결과는 ANSI C 표준에 따라 구현 시 정의 됩니다.  Microsoft C 컴파일러에서, 부호 없는 정수에서 비트 연산은 같은 부호 있는 정수의 비트 연산과 작동이 같습니다.  예를 들어, `-16 & 99`는 이진 형식으로 다음과 같이 표현될 수 있습니다.  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 비트 AND의 결과는 10진수 96입니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [비트 AND 연산자: &](../cpp/bitwise-and-operator-amp.md)   
 [배타적 비트 OR 연산자: ^](../cpp/bitwise-exclusive-or-operator-hat.md)   
 [포괄적 비트 OR 연산자: &#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)