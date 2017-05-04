---
title: "기본 형식(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c9f82907-25f2-440b-91d6-afb8dbd46ea6
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 14
---
# 기본 형식(C++/CX)
표준 C\+\+ 기본 제공 형식 이외에 [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]\([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\)에서는 표준 C\+\+ 형식에 매핑되는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 기본 형식에 대한 형식 정의를 제공하여 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 아키텍처에서 정의된 형식 시스템을 지원합니다.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에서는 부울, 문자 및 숫자 기본 형식을 구현합니다. 이러한 형식 정의는 명시적으로 지정할 필요가 없는 `default` 네임스페이스에서 정의됩니다. 또한 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에서는 특정 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식 및 인터페이스에 대한 래퍼 및 구체적 구현을 제공합니다.  
  
## 부울 및 문자 형식  
 다음 표에는 기본 제공 부울 및 문자 형식과 표준 C\+\+ 해당 항목이 나와 있습니다.  
  
|네임스페이스|[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 이름|정의|표준 C\+\+ 이름|값의 범위|  
|------------|---------------------------------------------------------------------|--------|-----------------|-----------|  
|플랫폼|부울|8비트 부울 값입니다.|bool|`true`\(0이 아님\) 및 `false`\(0\)|  
|default|char16|유니코드\(UTF\-16\) 코드 포인트를 나타내는 숫자가 아닌 16비트 값입니다.|wchar\_t<br /><br /> 또는<br /><br /> L'c'|\(유니코드 표준으로 지정됨\)|  
  
## 숫자 형식  
 다음 표에는 기본 제공 숫자 형식이 나와 있습니다. 숫자 형식은 `default` 네임스페이스에서 선언되고 해당 C\+\+ 기본 제공 형식의 형식 정의입니다. 일부 C\+\+ 기본 제공 형식\(예: long\)은 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]에서 지원되지 않습니다. 일관성을 유지하고 쉽게 구별하도록 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 이름을 사용하는 것이 좋습니다.  
  
|[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 이름|정의|표준 C\+\+ 이름|값의 범위|  
|---------------------------------------------------------------------|--------|-----------------|-----------|  
|int8|8비트 부호 있는 숫자 값입니다.|signed char|–128 ~ 127|  
|uint8|8비트 부호 없는 숫자 값입니다.|unsigned char|0 ~ 255|  
|int16|16비트 부호 있는 정수입니다.|short|–32,768 ~ 32,767|  
|uint16|16비트 부호 없는 정수입니다.|unsigned short|0 ~ 65,535|  
|int32|32비트 부호 있는 정수입니다.|int|–2,147,483,648 ~ 2,147,483,647|  
|uint32|32비트 부호 없는 정수입니다.|unsigned int|0 ~ 4,294,967,295|  
|int64|64비트 부호 있는 정수입니다.|long long \-또는\- \_\_int64|–9,223,372,036,854, 775,808 ~ 9,223,372,036,854,775,807|  
|uint64|64비트 부호 없는 정수입니다.|unsigned long long \-또는\- unsigned \_\_int64|0 ~ 18,446,744,073,709,551,615|  
|float32|32비트 IEEE 754 부동 소수점 숫자입니다.|float|3.4E\+\/\-38\(7개의 자릿수\)|  
|float64|64비트 IEEE 754 부동 소수점 숫자입니다.|double|1.7E\+\/\-308\(15개의 자릿수\)|  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식  
 다음 표에서는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 아키텍처에서 정의되고 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에 빌드되는 몇 가지 추가 형식을 보여 줍니다. 개체 및 문자열은 참조 형식입니다. 기타 항목은 값 형식입니다. 이러한 형식은 모두 `Platform` 네임스페이스에서 선언됩니다. 전체 목록은 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)를 참조하세요.  
  
|이름|정의|  
|--------|--------|  
|개체|[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식을 나타냅니다.|  
|문자열|텍스트를 나타내는 일련의 문자입니다.|  
|Rect|사각형의 위치와 크기를 나타내는 네 부동 소수점 숫자 집합입니다.|  
|SizeT|높이와 너비를 지정하는 부동 소수점 숫자의 순서가 지정된 쌍입니다.|  
|요소|2차원 평면에서 점을 정의하는 부동 소수점 X 좌표 및 Y 좌표의 순서가 지정된 쌍입니다.|  
|Guid|고유 식별자로 사용되는 128비트 숫자가 아닌 값입니다.|  
|UIntPtr|내부 전용입니다. 포인터로 사용되는 부호 없는 64비트 값입니다.|  
|IntPtr|내부 전용입니다.  포인터로 사용되는 부호 있는 64비트 값입니다.|  
  
## 참고 항목  
 [형식 시스템](../cppcx/type-system-c-cx.md)