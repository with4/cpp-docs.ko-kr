---
title: "부동 소수점 상수에 대한 제한 | Microsoft Docs"
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
  - "FLOAT.H 헤더 파일"
  - "부동 소수점 상수, limits"
  - "부동 소수점 숫자, 부동 제한"
  - "limits, 부동 소수점 상수"
  - "범위, 부동 소수점 상수"
ms.assetid: 2d975868-2af6-45d7-a8af-db79f2c6b67b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 부동 소수점 상수에 대한 제한
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 다음 표에는 부동서 소수점 상수 값에 대한 제한이 나와 있습니다.  이 정보는 FLOAT.H 헤더 파일에 있습니다.  
  
### 부동 소수점 상수에 대한 제한  
  
|상수|의미|값|  
|--------|--------|-------|  
|**FLT\_DIGDBL\_DIGLDBL\_DIG**|자릿수 *q*입니다. 자릿수가 *q* 10진수인 부동 소수점 수는 부동 소수점 표현으로 반올림될 수 있고 정밀도의 손실 없이 다시 복원될 수 있습니다.|6 15 15|  
|**FLT\_EPSILONDBL\_EPSILONLDBL\_EPSILON**|가장 작은 양수가 *x*이므로 *x* \+ 1.0은 1.0과 같지 않습니다.|1.192092896e–07F 2.2204460492503131e–016 2.2204460492503131e–016|  
|**FLT\_GUARD**||0|  
|**FLT\_MANT\_DIGDBL\_MANT\_DIGLDBL\_MANT\_DIG**|부동 소수점 significand의 **FLT\_RADIX**이 지정한 기수의 자릿수입니다.  기수는 2입니다. 따라서 이러한 값이 비트를 지정합니다.|24 53 53|  
|**FLT\_MAXDBL\_MAXLDBL\_MAX**|표현 가능한 최대 부동 소수점 수입니다.|3.402823466e\+38F 1.7976931348623158e\+308 1.7976931348623158e\+308|  
|**FLT\_MAX\_10\_EXPDBL\_MAX\_10\_EXPLDBL\_MAX\_10\_EXP**|숫자에 10이 더해진 최대 정수는 표현 가능한 부동 소수점 숫자입니다.|38 308 308|  
|**FLT\_MAX\_EXPDBL\_MAX\_EXPLDBL\_MAX\_EXP**|숫자에 **FLT\_RADIX**가 더해진 최대 정수는 표현 가능한 부동 소수점 숫자입니다.|128 1024 1024|  
|**FLT\_MINDBL\_MINLDBL\_MIN**|최소 양수 값입니다.|1.175494351e–38F 2.2250738585072014e–308 2.2250738585072014e–308|  
|**FLT\_MIN\_10\_EXPDBL\_MIN\_10\_EXPLDBL\_MIN\_10\_EXP**|숫자에 10이 더해진 최소 음의 정수는 표현 가능한 부동 소수점 숫자입니다.|–37<br /><br /> –307<br /><br /> –307|  
|**FLT\_MIN\_EXPDBL\_MIN\_EXPLDBL\_MIN\_EXP**|숫자에 **FLT\_RADIX**가 더해진 최소 음의 정수는 표현 가능한 부동 소수점 숫자입니다.|–125<br /><br /> –1021<br /><br /> –1021|  
|**FLT\_NORMALIZE**||0|  
|**FLT\_RADIX\_DBL\_RADIX\_LDBL\_RADIX**|지수를 표현하는 기수입니다.|2 2 2|  
|**FLT\_ROUNDS\_DBL\_ROUNDS\_LDBL\_ROUNDS**|부동 소수점 더하기의 반올림 모드입니다.|1 \(near\) 1 \(near\) 1 \(near\)|  
  
 상기 표의 정보는 이후 구현에서 다를 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [C 부동 소수점 상수](../c-language/c-floating-point-constants.md)