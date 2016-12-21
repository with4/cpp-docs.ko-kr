---
title: "인라인 어셈블리에서 형식 및 변수 크기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "length"
  - "Type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인라인 어셈블리, 연산자"
  - "LENGTH 연산자"
  - "크기"
  - "SIZE 연산자"
  - "크기, 인라인 어셈블리에서 가져오기"
  - "TYPE 연산자"
  - "변수, 길이"
  - "변수, 크기"
  - "변수, 형식"
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 인라인 어셈블리에서 형식 및 변수 크기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft 관련**  
  
 **길이**,  **크기**, 및  **형식** 연산자는 인라인 어셈블리에서 제한 된 의미 합니다.  전혀 사용할 수 없습니다는  `DUP`연산자 \(MASM 지시문 또는 연산자를 사용 하 여 데이터를 정의할 수 없습니다\) 때문입니다.  그러나 C 나 c \+ \+ 변수 또는 형식의 크기를 찾을 사용할 수 있습니다.  
  
-   **길이** 운영자 배열에 있는 요소의 수를 반환할 수 있습니다.  배열이 아닌 변수에 대 한 값 1을 반환합니다.  
  
-   **크기** 연산자는 C 또는 c \+ \+ 변수의 크기를 반환할 수 있습니다.  변수의 크기는 제품의 해당  **길이** 및  **유형**.  
  
-   **유형** 연산자 C 또는 c \+ \+ 형식 또는 변수 크기를 반환할 수 있습니다.  배열 변수가  **유형** 배열의 단일 요소 크기를 반환 합니다.  
  
 예를 들어, 프로그램에는 8 요소  `int`배열  
  
```  
int arr[8];  
```  
  
 다음 C 및 어셈블리 식 산출 크기  `arr`와 구성 요소입니다.  
  
|\_\_asm|C|크기|  
|-------------|-------|--------|  
|**길이** arr|`sizeof`\(arr\)\/`sizeof`\(arr\[0\]\)|8|  
|**크기** arr|`sizeof`\(arr\)|32|  
|**TYPE** arr|`sizeof`\(arr\[0\]\)|4|  
  
 **Microsoft 특정 끝**  
  
## 참고 항목  
 [\_\_asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)