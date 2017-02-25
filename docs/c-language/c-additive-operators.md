---
title: "C 가감 연산자 | Microsoft Docs"
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
  - "+ 연산자, 가감 연산자"
  - "가감 연산자"
  - "산술 연산자[C++], 가감 연산자"
  - "연산자[C], 더하기"
  - "일반적인 산술 변환"
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# C 가감 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

가감 연산자는 더하기\(**\+**\)와 빼기\(**\-**\)를 수행합니다.  
  
## 구문  
 *additive\-expression*:  
 *multiplicative\-expression*  
  
 *additive\-expression*  **\+**  *multiplicative\-expression*  
  
 *additive\-expression*  **–**  *multiplicative\-expression*  
  
> [!NOTE]
>  *additive\-expression*의 구문에 *multiplicative\-expression*이 포함되지만 곱하기를 사용하는 식이 필요하다는 의미는 아닙니다.  *multiplicative\-expression*, *cast\-expression* 및 *unary\-expression*에 대한 구문은 [C 언어 구문 요약](../c-language/c-language-syntax-summary.md)을 참조하십시오.  
  
 피연산자는 정수 계열 또는 부동 형식 값일 수 있습니다.  일부 가감 연산은 포인터 값을 대상으로 수행될 수도 있습니다. 이에 대한 내용은 각 연산자에 대한 설명에 나와 있습니다.  
  
 가감 연산자는 정수 계열 및 부동 형식 피연산자에 대한 일반적인 산술 변환을 수행합니다.  결과 형식은 변환 후의 피연산자 형식과 동일합니다.  가감 연산자로 수행된 변환은 오버플로 또는 언더플로 조건을 지원하지 않으므로 변환 후 가감 연산 결과가 피연산자 형식으로 표현될 수 없는 경우 정보가 손실될 수 있습니다.  
  
## 참고 항목  
 [가감 연산자: \+ 및 \-](../cpp/additive-operators-plus-and.md)