---
title: "데이터 형식 지정자 및 해당 항목 | Microsoft Docs"
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
  - "데이터 형식[C++], 해당 항목"
  - "데이터 형식[C++], 지정자"
  - "식별자, 데이터 형식"
  - "부호 확장 정수 계열 형식"
  - "단순 형식, 이름"
  - "형식 이름[C++], 단순"
  - "형식 지정자[C++], 목록"
  - "정수 확장"
  - "0 확장"
ms.assetid: 0d4b515a-4f68-4786-83cf-a5d43c7cb6f3
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 데이터 형식 지정자 및 해당 항목
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 책에서는 일반적으로 긴 형태보다 다음 표에 나열되어 있는 형식 지정자의 형태를 사용하며, 기본적으로 `char` 형식이 서명되어 있다고 가정합니다.  따라서 이 책에 나온 `char`는 **signed char**와 동일합니다.  
  
### 형식 지정자 및 해당 값  
  
|형식 지정자|해당 값|  
|------------|----------|  
|**signed char**1|`char`|  
|**signed int**|**signed**, `int`|  
|**signed short int**|**short**, `signed short`|  
|**signed long int**|**long**, **signed long**|  
|`unsigned char`|—|  
|`unsigned int`|`unsigned`|  
|**unsigned short int**|**unsigned short**|  
|**unsigned long int**|`unsigned long`|  
|**float**|—|  
|`long double`2|—|  
  
 1   기본적으로 부호 없는 `char` 형식을 만들면\(\/J 컴파일러 옵션 지정\) **signed char**를 `char`로 줄여 표현할 수 없습니다.  
  
 2   32비트 운영 체제에서 Microsoft C 컴파일러는 **long double**을 **double** 형식에 매핑합니다.  
  
 **Microsoft 전용**  
  
 \/J 컴파일러 옵션을 지정하여 기본 `char` 형식을 서명됨에서 서명되지 않음으로 변경할 수 있습니다.  이 옵션이 적용되면, `char`는 `unsigned char`와 같은 의미가 되기 때문에, 부호 있는 문자 값을 선언하는 **signed** 키워드를 사용해야 합니다.  `char` 값이 명시적으로 signed로 선언되면, \/J 옵션은 이 값에 영향을 주지 않으며, 이 값이 `int` 형식으로 확장되는 경우에는 부호가 확장됩니다.  `char` 형식은 `int` 형식으로 확장되면 제로 확장합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [C 형식 지정자](../c-language/c-type-specifiers.md)