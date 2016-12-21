---
title: "C++ 정수 제한 | Microsoft Docs"
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
  - "정수 제한"
  - "limits, 정수"
  - "limits, 정수 상수"
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 정수 제한
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 다음 표에서는 정수 형식에 대한 제한 사항을 보여 줍니다.  이 제한 사항은 표준 헤더 파일 LIMITS.H에도 정의되어 있습니다.  Microsoft C에서는 정수 변수를 8비트, 16비트 또는 32비트의 정수 계열 형식으로 크기를 지정하여 선언할 수 있습니다.  크기가 지정된 정수에 대한 자세한 내용은 [크기 지정 정수 형식](../c-language/c-sized-integer-types.md)을 참조하십시오.  
  
### 정수 상수에 대한 제한  
  
|**상수**|의미|값|  
|------------|--------|-------|  
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
|**INT\_MIN**|`int` 형식 변수의 최소값입니다.|–2147483647 – 1|  
|**INT\_MAX**|`int` 형식 변수의 최대값입니다.|2147483647|  
|**UINT\_MAX**|`unsigned int` 형식 변수의 최대값입니다.|4294967295\(0xffffffff\)|  
|**LONG\_MIN**|**long** 형식 변수의 최소값입니다.|–2147483647 – 1|  
|**LONG\_MAX**|**long** 형식 변수의 최대값입니다.|2147483647|  
|**ULONG\_MAX**|`unsigned long` 형식 변수의 최대값입니다.|4294967295\(0xffffffff\)|  
  
 값이 최대 정수 표현을 초과하는 경우 Microsoft 컴파일러에서 오류가 발생합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [C 정수 상수](../c-language/c-integer-constants.md)