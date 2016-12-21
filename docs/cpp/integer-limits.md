---
title: "정수 제한 | Microsoft Docs"
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
  - "정수 제한"
  - "정수 계열 제한"
  - "limits, 정수"
  - "LIMITS.H 헤더 파일"
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 정수 제한
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 다음 표에서는 정수 형식에 대한 제한 사항을 보여 줍니다.  이러한 제한은 표준 헤더 파일 LIMITS.H에도 정의되어 있습니다.  
  
### 정수 상수에 대한 제한  
  
|상수|의미|값|  
|--------|--------|-------|  
|**CHAR\_BIT**|비트 필드가 없는 가장 작은 변수의 비트 수입니다.|8|  
|**SCHAR\_MIN**|**signed char** 형식 변수의 최소값입니다.|–128|  
|**SCHAR\_MAX**|**signed char** 형식 변수의 최대 값입니다.|127|  
|**UCHAR\_MAX**|`unsigned char` 형식 변수의 최대값입니다.|255\(0Xff\)|  
|**CHAR\_MIN**|`char` 형식 변수의 최소값입니다.|\/J 옵션이 사용된 경우, –128; 0|  
|**CHAR\_MAX**|`char` 형식 변수의 최대값입니다.|\/J 옵션이 사용된 경우, –127; 255|  
|**MB\_LEN\_MAX**|여러 문자 상수에서의 최대 바이트 수입니다.|5|  
|**SHRT\_MIN**|**short** 형식 변수의 최소값입니다.|–32768|  
|**SHRT\_MAX**|**short** 형식 변수의 최대 값입니다.|32767|  
|**USHRT\_MAX**|**unsigned short** 형식 변수의 최대 값입니다.|65535\(0xffff\)|  
|**INT\_MIN**|`int` 형식 변수의 최소값입니다.|–2147483648|  
|**INT\_MAX**|`int` 형식 변수의 최대값입니다.|2147483647|  
|**UINT\_MAX**|`unsigned int` 형식 변수의 최대값입니다.|4294967295\(0xffffffff\)|  
|**LONG\_MIN**|**long** 형식 변수의 최소값입니다.|–2147483648|  
|**LONG\_MAX**|**long** 형식 변수의 최대값입니다.|2147483647|  
|**ULONG\_MAX**|`unsigned long` 형식 변수의 최대값입니다.|4294967295\(0xffffffff\)|  
|**\_I64\_MIN**|`__int64` 형식의 변수에 대한 최소값입니다.|\-9223372036854775808|  
|**\_I64\_MAX**|`__int64` 형식의 변수에 대한 최대값입니다.|9223372036854775807|  
|**\_UI64\_MAX**|**unsigned \_\_int64** 형식의 변수에 대한 최대값입니다.|18446744073709551615\(0xffffffffffffffff\)|  
  
 값이 최대 정수 표현을 초과하는 경우 Microsoft 컴파일러에서 오류가 발생합니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [부동 한계](../cpp/floating-limits.md)