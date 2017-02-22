---
title: "필수 및 선택적 헤더 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.headers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "헤더 파일, 런타임에 필수"
  - "포함 파일, 런타임에 필수"
ms.assetid: f64d0bf5-e2c3-4b42-97d0-443b3d901d9f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 필수 및 선택적 헤더 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각 런타임 루틴에 대한 설명은 필요로되고 부가적인 목록, 또는 헤더\(H\), 루틴의 파일을 포함합니다.  필수 헤더 파일을 구하는 루틴 또는 내부적으로 호출하는 다른 루틴에 의해 사용되는 정의에 대한 함수 선언을 포함 해야 합니다.  선택적 헤더 파일이 미리 정의된 상수, 형식 정의 또는 인라인 매크로를 활용하기 위해 일반적으로 포함 됩니다.  다음 표에서 몇 가지 선택적 헤더 파일 내용:  
  
|정의|예제|  
|--------|--------|  
|매크로 정의|라이브러리 루틴을 매크로로 구현 되는 경우 원래 루틴에 대한 헤더 파일이 아닌 다른 헤더 파일에 매크로 정의일 수 있습니다.  예를 들어 `_toupper` 매크로는 헤더파일 CTYPE.H에서 정의됩니다, 함수 `toupper` 가 STDLIB.H에서 선언되는 동안입니다.|  
|미리 선언된 상수|많은 라이브러리 루틴 헤더 파일에 정의된 상수를 참조 하십시오.  예를 들어, `_open` 루틴은 헤더파일 FCNTL.H에서 정의된 `_O_CREAT` 와 같은 상수를 사용합니다.|  
|형식 정의|일부 라이브러리 루틴은 구조체를 반환하거나 또는 인수로서 구조체를 취합니다.  예를 들어, 스트림 입\/출력 루틴은 `FILE` 형식의 구조체를 사용합니다, 이는 STDIO.H로 정의되었습니다.|  
  
 런타임 라이브러리 헤더 파일은 ANSI\/ISO C 표준 권장된 스타일 함수 선언을 제공합니다.  컴파일러와 관련된 함수 선언 후에 발생 하는 일상적인 참조에 대해 형식 검사를 수행 합니다.  함수 선언은 특히 기본값인 `int` 가 아닌 일부 형식의 값인 루틴에 대하여 중요합니다.  선언에서 적절한 반환값을 지정하지 않은 루틴은 예기치 않은 결과를 초래할 수 있는 `int` 를 반환한 컴파일에 의해 고려되어 질 수 있습니다.  자세한 내용은 [형식 검사](../c-runtime-library/type-checking-crt.md) 를 참조하십시오.  
  
## 참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)