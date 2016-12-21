---
title: "&lt; codecvt &gt; | Microsoft Docs"
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
  - "codecvt"
  - "std::<codecvt>"
  - "std.<codecvt>"
  - "<codecvt>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt 헤더"
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; codecvt &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스를 기반으로 하는 개체를 설명 하는 여러 템플릿 클래스 정의 [codecvt](../standard-library/codecvt-class.md)합니다. 이러한 개체 역할도 할 수 있습니다 [로캘 패싯에](../standard-library/locale-class.md#facet_class) 형식 값의 시퀀스 사이의 변환을 제어 하는 `Elem` 형식의 값의 시퀀스와 `char`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <codecvt>  
  
```  
  
## <a name="remarks"></a>주의  
 이 헤더에 선언 된 로캘 패싯에 여러 문자 인코딩 간 변환 합니다. 와이드 문자 (고정 크기의 정수에는 프로그램 내에서 저장 됨):  
  
-   U c S-4는 유니코드 (ISO 10646)는 프로그램 내에서 인코딩  
  
-   U c S 4는 유니코드 (ISO 10646) 32 비트 정수로 프로그램 내에 인코딩된입니다.  
  
-   U c S-2는 유니코드로 인코딩된 프로그램 내에서  
  
-   U c S 2는 16 비트 정수로 프로그램 내에 인코딩된 유니코드입니다.  
  
-   U t F-16이 중 하나는 프로그램 내에 인코딩된 유니코드  
  
-   U t F-16은 프로그램 내에서 하나 또는 두 개의 16 비트 정수로 인코딩된 유니코드입니다. (표준 C 또는 표준 c + +에 대 한 올바른 와이드 문자 인코딩을의 모든 요구 사항을 충족 하지 않는이 note 합니다. 그럼에도 불구 하 고 널리 사용 됩니다 따라서.)  
  
 Byte 함수에 대 한 (파일에 저장, 바이트 시퀀스로 전송 또는 배열에는 프로그램 안에 저장 `char`):  
  
-   U t F-8은 유니코드 인코딩  
  
-   U t F-8은 바이트 스트림 내에서 결정적 바이트 순서를 가진 하나 이상의 8 비트 바이트 형식으로 인코딩된 유니코드입니다.  
  
-   U t F-16LE는 유니코드 인코딩  
  
-   U t F-16LE은 바이트 스트림에서 u t F-16으로 인코딩된 유니코드 먼저 덜 중요 한 바이트의 두 개의 8 비트 바이트 형식으로 표시 하는 각 16 비트 정수를 사용 합니다.  
  
-   U t F-16BE는 유니코드 인코딩  
  
-   U t F-16BE 바이트 스트림에서 u t F-16으로 인코딩된 유니코드는 먼저 두 개의 8 비트 바이트, 더 중요 한 바이트 형식으로 표시 하는 각 16 비트 정수를 사용 합니다.  
  
### <a name="enumerations"></a>열거형  
  
|||  
|-|-|  
|[codecvt_mode](../Topic/%3Ccodecvt%3E%20enums.md#codecvt_mode_enumeration)|로캘 패싯에 대 한 구성 정보를 지정합니다.|  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[codecvt_utf8](../Topic/%3Ccodecvt%3E%20functions.md#codecvt_utf8)|Ucs-2 또는 u c S-4로 인코딩된 와이드 문자 및 u t F-8로 인코딩된 바이트 스트림 간에 변환 되는 로캘 패싯을 나타냅니다.|  
|[codecvt_utf8_utf16](%3Ccodecvt%3E%20functions.md#codecvt_utf8_utf16)|U t F-16으로 인코딩된 와이드 문자 및 u t F-8로 인코딩된 바이트 스트림 간에 변환 되는 로캘 패싯을 나타냅니다.|  
|[codecvt_utf16](../Topic/%3Ccodecvt%3E%20functions.md#codecvt_utf16)|Ucs-2 또는 u c S-4로 인코딩된 와이드 문자 및 u t F-16LE 또는 u t F-16BE로 인코딩된 바이트 스트림 간에 변환 되는 로캘 패싯을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< codecvt>  
  
 **네임 스페이스:** stdt  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)




