---
title: "부호 없는 정수 계열 형식에서 변환 | Microsoft Docs"
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
  - "데이터 형식 변환[C++], 부호 있는 정수와 부호 없는 정수"
  - "정수, 변환"
  - "정수 계열 변환, unsigned에서 변환"
  - "형식 캐스팅, 정수 계열 관련"
  - "형식 변환[C++], 부호 있는 정수와 부호 없는 정수"
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 부호 없는 정수 계열 형식에서 변환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

부호 없는 정수는 상위 비트를 잘라 더 짧은 부호 없는 정수 또는 부호 있는 정수로 변환되거나 0 확장을 통해 더 긴 부호 없는 정수 또는 부호 있는 정수로 변환됩니다\([부호 없는 정수 계열 형식에서 변환](#_clang_table_4..3) 표 참조\).  
  
 정수 계열 형식의 값이 더 작은 크기의 부호 있는 정수로 강등되거나 부호 없는 정수가 해당 부호 있는 정수로 변환될 때 값을 새 형식으로 표현할 수 있으면 값이 변경되지 않습니다.  그러나 다음 예제와 같이 부호 비트가 설정된 경우 나타내는 값이 변경됩니다.  
  
```  
int j;  
unsigned short k = 65533;  
  
j = k;  
printf_s( "%hd\n", j );   // Prints -3  
```  
  
 값을 표현할 수 없는 경우 결과는 구현 시 정의됩니다.  Microsoft C 컴파일러의 정수 강등 처리에 대한 자세한 내용은 [형식 캐스팅 변환](../c-language/type-cast-conversions.md)을 참조하십시오.  정수를 변환하거나 형식 캐스팅해도 같은 동작이 발생합니다.  
  
 부호 없는 값은 해당 값을 유지하고 C에서 직접 표현할 수 없는 방식으로 변환됩니다.  유일한 예외는 `unsigned long`에서 **float**로의 변환이며, 가장 심한 경우 하위 비트가 손실됩니다.  그렇지 않으면 값이 유지되거나 서명 또는 서명되지 않습니다.  정수 계열 형식의 값이 부동으로 변환되고 해당 값이 표현할 수 있는 범위를 벗어난 경우 결과가 정의되지 않습니다. 정수 계열 및 부동 소수점 형식의 범위에 대한 자세한 내용은 [기본 형식 저장](../c-language/storage-of-basic-types.md)을 참조하십시오.  
  
 다음 표에서는 부호 없는 정수 계열 형식으로부터의 변환을 요약하여 보여 줍니다.  
  
### 부호 없는 정수 계열 형식에서 변환  
  
|전|후|메서드|  
|-------|-------|---------|  
|`unsigned char`|`char`|비트 패턴 유지\(상위 비트가 부호 비트가 됨\)|  
|`unsigned char`|**short**|0 확장|  
|`unsigned char`|**long**|0 확장|  
|`unsigned char`|**unsigned short**|0 확장|  
|`unsigned char`|`unsigned long`|0 확장|  
|`unsigned char`|**float**|**long**으로 변환\(**long**을 **float**로 변환\)|  
|`unsigned char`|**double**|**long**으로 변환\(**long**을 **double**로 변환\)|  
|`unsigned char`|`long double`|**long**으로 변환\(**long**을 **double**로 변환\)|  
|**unsigned short**|`char`|하위 바이트 유지|  
|**unsigned short**|**short**|비트 패턴 유지\(상위 비트가 부호 비트가 됨\)|  
|**unsigned short**|**long**|0 확장|  
|**unsigned short**|`unsigned char`|하위 바이트 유지|  
|**unsigned short**|`unsigned long`|0 확장|  
|**unsigned short**|**float**|**long**으로 변환\(**long**을 **float**로 변환\)|  
|**unsigned short**|**double**|**long**으로 변환\(**long**을 **double**로 변환\)|  
|**unsigned short**|`long double`|**long**으로 변환\(**long**을 **double**로 변환\)|  
|`unsigned long`|`char`|하위 바이트 유지|  
|`unsigned long`|**short**|하위 단어 유지|  
|`unsigned long`|**long**|비트 패턴 유지\(상위 비트가 부호 비트가 됨\)|  
|`unsigned long`|`unsigned char`|하위 바이트 유지|  
|`unsigned long`|**unsigned short**|하위 단어 유지|  
|`unsigned long`|**float**|**long**으로 변환\(**long**을 **float**로 변환\)|  
|`unsigned long`|**double**|직접 **double**로 변환|  
|`unsigned long`|`long double`|**long**으로 변환\(**long**을 **double**로 변환\)|  
  
 **Microsoft 전용**  
  
 Microsoft 32비트 C 컴파일러의 경우 `unsigned int` 형식은 `unsigned long` 형식과 동일합니다.  `unsigned int` 값의 변환은 `unsigned long`의 변환과 동일하게 진행됩니다.  변환되는 값이 최대 양의 부호 있는 **long** 값보다 더 큰 경우 `unsigned long` 값에서 **float**로의 변환이 정확하지 않습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [할당 변환](../c-language/assignment-conversions.md)