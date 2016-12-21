---
title: "가감 연산자 사용 | Microsoft Docs"
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
  - "가감 연산자"
  - "연산자[C++], 더하기"
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 가감 연산자 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

더하기 및 빼기 연산자를 보여 주는 다음 예제는 이러한 선언을 사용합니다.  
  
```  
int i = 4, j;  
float x[10];  
float *px;  
```  
  
 이 문은 다음에 해당합니다.  
  
```  
px = &x[4 + i];  
px = &x[4] + i;    
```  
  
 값 `i`는 **float**의 길이로 곱해지고 `&x[4]`에 더해집니다.  결과 포인터 값은 `x[8]`의 주소입니다.  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 이 예제에서는 `x`의 세 번째 요소의 주소\(`x[i–2]`에서 지정\)가 `x`의 다섯 번째 요소의 주소\(`x[i]`에서 지정\)에서 차감됩니다.  차이는 **float**의 길이로 나눠지며 결과는 정수 값 2입니다.  
  
## 참고 항목  
 [C 가감 연산자](../c-language/c-additive-operators.md)