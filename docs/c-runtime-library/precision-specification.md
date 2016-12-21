---
title: "전체 자릿수 사양 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c.math"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "printf 함수, 형식 사양 필드"
ms.assetid: dc59ea4e-d23a-4f1f-9881-2c919ebefb82
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 전체 자릿수 사양
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 사양에서, 세 번째 선택적 필드는 정밀도 사양입니다.  이것은 변환 종류에 따라, 문자열의 문자 수, 소수 자릿수 또는 출력을 유효 자릿수를 지정 하는 음수가 아닌 십진수, 정수 뒤에 오는 마침표 \(.\)로 구성됩니다.  
  
 너비 지정 달리, 정밀도 사양은 출력 값 잘림 또는 반올림 부동 소수점 값중 하나를 야기할 수 있습니다.  만일 `precision` 이 \(\)로써 지정되고 지정된 값이 \(\)인 경우, 결과는 이 예제에서처럼 문자를 출력하지 않습니다:  
  
 `printf( "%.0d", 0 );      /* No characters output */`  
  
 만일 정밀도 지정이 별표\(\*\)인 경우, 인수 목록으로부터 `int` 인수는 값을 공급합니다.  인수 목록에서, 이 예제와 같이 `precision` 인수는 반드시 형식이 지정된 값 앞에 와야 합니다.  
  
 `printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`  
  
 다음 표에서처럼, 형식은 `precision` 의 반복 또는 `precision` 이 생략될 때 기본 정밀도 중 하나를 결정합니다.  
  
### 정밀도 값이 형식에 영향을 미치는 방법  
  
|형식|의미|기본|  
|--------|--------|--------|  
|`a`, `A`|정밀도는 꼭짓점 뒤의 자릿수를 지정합니다.|기본 정밀도는 6입니다.  만일 정밀도가 \(\)인 경우, 출력된 소수점이 아니면, `#` 플래그를 사용 합니다.|  
|`c`, `C`|정밀도는 영향을 주지 않습니다.|문자가 출력됩니다.|  
|`d`, `i`, `u`, `o`, `x`, `X`|정밀도는 출력될 최소 자릿수를 지정합니다.  만일 인수에서 자릿수가 `precision` 보다 작은경우, 출력 값 0으로 왼쪽을 채웁니다.  자릿수가 `precision` 을 초과할 때, 값은 잘리지 않습니다.|기본 정밀도는 1입니다.|  
|`e`, `E`|정밀도는 소수점 뒤에 출력되는 자릿수를 지정합니다.  마지막으로 출력된 숫자가 반올리됩니다.|기본 정밀도는 6입니다.  만일 `precision` 이 0이거나 이것 다음에 오는 숫자 없이 마침표\(.\)로 나타난 경우, 소수점이 출력되지 않습니다.|  
|`f`|정밀도 값은 소수점 뒤에 자릿수를 지정합니다.  만일 소수점이 나타난다면, 적어도 하나의 숫자가 이전에 표시됩니다.  값은 적절한 자릿수로 반올림 됩니다.|기본 정밀도는 6입니다.  만일 `precision` 이 0이거나 이것 다음에 오는 숫자 없이 마침표\(.\)로 나타난 경우, 소수점이 출력되지 않습니다.|  
|`g`, `G`|정밀도는 출력되는 자릿수의 최대 수를 지정합니다.|6 개의 유효 자릿수가 출력되고, 뒤에 오는 0이 잘립니다.|  
|`s`, `S`|정밀도는 출력되는 문자의 최대 수를 지정합니다.  `precision` 의 초과되는 문자들은 출력되지 않습니다.|Null 문자가 나올 때까지 문자는 출력됩니다.|  
  
## 참고 항목  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [형식 사양 구문: printf 및 wprintf 함수](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [플래그 지시문](../c-runtime-library/flag-directives.md)   
 [printf 너비 사양](../c-runtime-library/printf-width-specification.md)   
 [크기 사양](../c-runtime-library/size-specification.md)   
 [printf 형식 필드 문자](../c-runtime-library/printf-type-field-characters.md)