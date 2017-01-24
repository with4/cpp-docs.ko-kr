---
title: "C 부동 소수점 상수 | Microsoft Docs"
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
  - "상수, 부동 소수점"
  - "double 데이터 형식, 부동 소수점 상수"
  - "부동 소수점 상수"
  - "부동 소수점 상수, 부동 소수점 상수 정보"
  - "부동 소수점 숫자, 부동 소수점 상수"
  - "형식[C], 상수"
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 부동 소수점 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"부동 소수점 상수"는 부호 있는 실수를 나타내는 10진수입니다.  부호 있는 실수의 표현에는 정수 부분, 소수 부분 및 지수가 포함됩니다.  부동 소수점 상수는 변경할 수 없는 부동 소수점 값을 나타낼 때 사용합니다.  
  
## 구문  
 *floating\-point\-constant*:  
 *fractional\-constant exponent\-part*  opt *floating\-suffix* opt  
  
 *digit\-sequence exponent\-part floating\-suffix*  opt  
  
 *fractional\-constant*:  
 *digit\-sequence*  opt **.** *digit\-sequence*  
  
 *digit\-sequence*  **.**  
  
 *exponent\-part*:  
 **e**  *sign*  opt *digit\-sequence*  
  
 **E**  *sign*  opt *digit\-sequence*  
  
 *기호* : ~ 중의 하나  
 **\+ –**  
  
 *digit\-sequence*:  
 *digit*  
  
 *digit\-sequence digit*  
  
 *floating\-suffix* : one of  
 **f l F L**  
  
 소수점 앞자리 \(값의 정수 부분\) 또는 소수점 뒷자리 \(소수 부분\)를 생략할 수 있지만, 두 개 모두는 생략할 수 없습니다.  지수를 포함하는 경우에만 소수점을 남겨둘 수 있습니다.  공백 문자로 정상수의 자리 또는 문자를 구분할 수 없습니다.  
  
 다음 예제에서는 일부 형식의 부동 소수점 상수 및 식을 보여 줍니다.  
  
```  
15.75  
1.575E1   /* = 15.75   */  
1575e-2   /* = 15.75   */  
-2.5e-3   /* = -0.0025 */  
25E-4     /* =  0.0025 */  
```  
  
 빼기 기호가 앞에 없을 경우 부동 소수점 상수는 양수입니다\(**–**\).  이 경우 빼기 기호는 단항 산술 부정 연산자로 간주됩니다.  부동 소수점 상수의 형식은 **float**, **double**, 또는 `long double`입니다.  
  
 **f**, **F**, **l** 또는 **L** 접미사가 없는 부동 소수점 상수의 형식은 **double**입니다.  문자 **f** 또는 **F**가 접미사이면 상수 형식은 **float**입니다.  접미사가 **l** 또는 **L** 문자인 경우 `long double` 형식을 사용합니다.  예를 들면 다음과 같습니다.  
  
```  
100L  /* Has type long double  */  
100F  /* Has type float        */  
```  
  
 Microsoft C 컴파일러는 **long double** 을 **이중** 입력하도록 매핑합니다.  **double**, **float** 및 **long** 유형에 대한 정보는 [기본 유형 저장소@@](../c-language/storage-of-basic-types.md)를 참조하십시오.  
  
 다음 예와 같이 부동 소수점 상수는 정수 부분을 생략할 수 있습니다.  숫자 .75는 다음과 같은 다양한 방법으로 나타낼 수 있습니다.  
  
```  
.0075e2  
0.075e1  
.075e1  
75e-2  
```  
  
## 참고 항목  
 [C 상수](../c-language/c-constants.md)