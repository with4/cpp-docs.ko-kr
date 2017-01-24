---
title: "부동 한계 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FLOAT.H 헤더 파일"
  - "부동 소수점 상수, limits"
  - "부동 소수점 숫자, 부동 제한"
  - "limits, 부동 소수점 상수"
  - "범위, 부동 소수점 상수"
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 부동 한계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 다음 표에는 부동 소수점 상수의 값에 대한 제한이 나와 있습니다.  이러한 제한은 표준 헤더 파일 FLOAT.H에서도 정의됩니다.  
  
### 부동 소수점 상수에 대한 제한  
  
|상수|의미|값|  
|--------|--------|-------|  
|FLT\_DIG DBL\_DIG LDBL\_DIG|소수 자릿수가 q인 부동 소수점 수가 부동 소수점 표현으로 반올림되고 정밀도의 손실 없이 다시 복원될 수 있는 자릿수 q입니다.|6 15 15|  
|FLT\_EPSILON DBL\_EPSILON LDBL\_EPSILON|x \+ 1.0이 1.0과 같지 않은 가장 작은 양수 x입니다.|1.192092896e–07F 2.2204460492503131e–016 2.2204460492503131e–016|  
|FLT\_GUARD||0|  
|FLT\_MANT\_DIG DBL\_MANT\_DIG LDBL\_MANT\_DIG|부동 소수점 유효 숫자에서 FLT\_RADIX로 지정된 기수의 자릿수입니다.  기수는 2입니다. 따라서 이러한 값이 비트를 지정합니다.|24 53 53|  
|FLT\_MAX DBL\_MAX LDBL\_MAX|표현 가능한 최대 부동 소수점 수입니다.|3.402823466e\+38F 1.7976931348623158e\+308 1.7976931348623158e\+308|  
|FLT\_MAX\_10\_EXP DBL\_MAX\_10\_EXP LDBL\_MAX\_10\_EXP|10을 해당 수만큼 거듭제곱한 값이 표현 가능한 부동 소수점 수인 최대 정수입니다.|38 308 308|  
|FLT\_MAX\_EXP DBL\_MAX\_EXP LDBL\_MAX\_EXP|FLT\_RADIX를 해당 수만큼 거듭제곱한 값이 표현 가능한 부동 소수점 수인 최대 정수입니다.|128 1024 1024|  
|FLT\_MIN DBL\_MIN LDBL\_MIN|최소 양수 값입니다.|1.175494351e–38F 2.2250738585072014e–308 2.2250738585072014e–308|  
|FLT\_MIN\_10\_EXP DBL\_MIN\_10\_EXP LDBL\_MIN\_10\_EXP|10을 해당 수만큼 거듭제곱한 값이 표현 가능한 부동 소수점 수인 최소 음의 정수입니다.|–37<br /><br /> –307<br /><br /> –307|  
|FLT\_MIN\_EXP DBL\_MIN\_EXP LDBL\_MIN\_EXP|FLT\_RADIX를 해당 수만큼 거듭제곱한 값이 표현 가능한 부동 소수점 수인 최소 음의 정수입니다.|–125<br /><br /> –1021<br /><br /> –1021|  
|FLT\_NORMALIZE||0|  
|FLT\_RADIX \_DBL\_RADIX \_LDBL\_RADIX|지수를 표현하는 기수입니다.|2 2 2|  
|FLT\_ROUNDS \_DBL\_ROUNDS \_LDBL\_ROUNDS|부동 소수점 더하기의 반올림 모드입니다.|1 \(near\) 1 \(near\) 1 \(near\)|  
  
> [!NOTE]
>  표의 정보는 제품의 이후 버전에서 달라질 수 있습니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [정수 제한](../cpp/integer-limits.md)