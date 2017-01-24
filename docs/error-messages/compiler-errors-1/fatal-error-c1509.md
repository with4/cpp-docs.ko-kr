---
title: "심각한 오류 C1509 | Microsoft Docs"
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
  - "C1509"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1509"
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1509
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 한계 : 함수 단순화 'function' 함수에 예외 처리기 상태가 너무 많습니다.  
  
 코드가 예외 처리기 상태의 내부 한계\(32,768상태\)를 초과합니다.  
  
 가장 일반적인 원인으로는 함수에 사용자 정의 클래스 변수 및 산술 연산자로 구성된 복잡한 식이 들어 있는 경우를 들 수 있습니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  임시 변수에 공용 하위 식을 할당하여 식을 간단하게 만듭니다.  
  
2.  함수를 좀 더 작은 여러 개의 함수로 분할합니다.