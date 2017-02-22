---
title: "printf 너비 사양 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "printf 함수, 형식 사양 필드"
  - "printf 함수, 너비 사양"
ms.assetid: 8b4a1b1e-bf6e-414f-a1b6-a9b6f1b6ce92
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# printf 너비 사양
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 지정에서 두 번째 선택적 필드는 너비 지정입니다.  `width` 인수는 출력 문자의 최소 수를 제어하는 음수가 아닌 10진 정수입니다.  출력값 내 문자의 수가 지정된 너비보다 작은 경우, 최소 너비 값에 도달할 때까지 왼쪽 정렬 플래그 \(`-`\)가 지정되었는지의 여부에 따라 값의 왼쪽 또는 오른쪽에 공백이 더해집니다.  `width`이 0으로 시작하는 경우, 변환이 무한대 또는 NAN인 경우를 제외하고 최소 너비에 도달할 때까지 정수 또는 부동 소수점 변환 앞에 0이 추가됩니다.  
  
 너비 지정은 결코 값이 잘리게 하지 않습니다.  출력 값 내 문자의 수가 지정된 너비보다 크거나 `width`가 주어지지 않은 경우, 값의 모든 문자가 출력되며, [precision](../c-runtime-library/precision-specification.md) 지정에 종속됩니다.  
  
 너비 지정이 별표 \(`*`\)인 경우, 인수 목록의 `int` 인수가 값을 공급합니다.  이 예제와 같이, `width` 인수는 반드시 인수 목록에 형식이 지정된 값 앞에 와야 합니다.  
  
 `printf("%0*f", 5, 3);  /* 00003 is output */`  
  
 형식 지정에서 `width`가 작거나 누락된 경우 출력값의 잘림이 발생하지 않습니다.  변환의 결과가 `width` 값보다 더 큰 경우, 변환 결과를 포함하기 위하여 필드가 확장됩니다.  
  
## 참고 항목  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [형식 사양 구문: printf 및 wprintf 함수](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [플래그 지시문](../c-runtime-library/flag-directives.md)   
 [전체 자릿수 사양](../c-runtime-library/precision-specification.md)   
 [크기 사양](../c-runtime-library/size-specification.md)   
 [printf 형식 필드 문자](../c-runtime-library/printf-type-field-characters.md)