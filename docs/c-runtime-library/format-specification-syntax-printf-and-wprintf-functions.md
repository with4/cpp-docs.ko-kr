---
title: "형식 사양 구문: printf 및 wprintf 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wprintf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "플래그 지시문 printf 함수"
  - "printf 함수의 형식 사양 필드"
  - "전체 자릿수 필드"
  - "인쇄 플래그 지시문"
  - "printf 함수, 형식 사양 필드"
  - "printf 함수, 전체 자릿수"
  - "형식 필드"
  - "형식 필드, printf 함수"
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# 형식 사양 구문: printf 및 wprintf 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`printf`, `wprintf` 및 관련 함수에 대한 문자열 인수 형식에 대한 구문을 설명합니다.  이러한 함수의 더 안전한 버전을 사용할 수 있습니다. 자세한 내용은 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md)을 참조하세요.  개별 함수에 대한 정보는 해당 함수에 대한 설명서를 참조하세요.  이러한 함수의 목록을 보려면 [스트림 I\/O](../c-runtime-library/stream-i-o.md)를 참조하세요.  
  
 필수 및 선택적 필드를 구성하는 형식 지정의 형식은 다음과 같습니다.  
  
 `%`\[[flags](../c-runtime-library/flag-directives.md)\] \[[width](../c-runtime-library/printf-width-specification.md)\] \[**.**[precision](../c-runtime-library/precision-specification.md)\] \[{`h` &#124; `l` &#124; `ll` &#124; `w` &#124; `I` &#124; `I32` &#124; `I64`}\] [type](../c-runtime-library/printf-type-field-characters.md)  
  
 각 형식 지정 필드는 특정 형식 옵션 또는 변환 지정자를 의미하는 문자와 숫자입니다.  필수 `type` 문자는 인수에 적용되는 변환 종류를 지정합니다.  선택적 `flags`, `width` 및 `precision` 필드는 추가 형식 요소를 제어합니다.  기본 형식 지정에는 백분율 기호 및 `type` 문자만 포함됩니다. 예를 들어 `%s`는 문자열 변환을 지정합니다.  안전한 버전의 함수에서는 백분율 기호 뒤에 형식 필드로서의 의미가 없는 문자가 나오는 경우 잘못된 매개 변수 처리기가 호출됩니다.  자세한 내용은 [매개 변수 유효성 검사](../c-runtime-library/parameter-validation.md)를 참조하세요.  안전하지 않은 버전에서는 문자가 변경되지 않은 채로 출력에 복사됩니다.  백분율 기호를 인쇄하려면 `%%`를 사용합니다.  
  
 형식 지정 필드는 인수 변환과 형식 지정의 다음과 같은 측면을 제어합니다.  
  
 `type`  
 관련된 `argument`가 문자, 문자열, 정수 또는 부동 소수점 숫자로 변환되는지 여부를 결정하는 필수 변환 지정자 문자입니다.  자세한 내용은 [printf 형식 필드 문자](../c-runtime-library/printf-type-field-characters.md)를 참조하세요.  
  
 `flags`  
 선택적 문자나 출력 양쪽 맞춤 및 기호 출력, 공백, 선행 0, 소수점 및 8진수 및 16진수 접두사의 출력을 제어하는 문자입니다.  자세한 내용은 [플래그 지시문](../c-runtime-library/flag-directives.md)를 참조하세요.  둘 이상의 플래그가 형식 지정에 나타날 수 있고 플래그는 임의의 순서로 나타날 수 있습니다.  
  
 `width`  
 출력된 문자의 최소 개수를 지정하는 선택적 10진수 숫자입니다.  자세한 내용은 [printf 너비 사양](../c-runtime-library/printf-width-specification.md)을 참조하세요.  
  
 `precision`  
 문자열, 유효 자릿수 또는 부동 소수점 값의 소수점 뒷자리수에 대해 인쇄되는 최대 자릿수 또는 정수 값에 대해 인쇄되는 최소 자릿수를 지정하는 선택적 10진수 숫자입니다.  자세한 내용은 [전체 자릿수 사양](../c-runtime-library/precision-specification.md)의 "정밀도 값이 형식에 영향을 미치는 방법"을 참조하세요.  
  
 `h` &#124; `l` &#124; `ll` &#124; `w` &#124; `I` &#124; `I32` &#124; `I64`  
 해당 인수의 크기를 지정하는 `type`에 대한 선택적 접두사입니다.  자세한 내용은 [크기 사양](../c-runtime-library/size-specification.md)의 "크기 접두사"를 참조하세요.  
  
> [!IMPORTANT]
>  형식 지정 문자열이 사용자 정의 문자열이 아닌지 확인합니다.  예를 들어 프로그램에서 사용자에게 이름을 입력하라는 메시지를 표시하고 `name`이라는 문자열 변수에 입력을 저장할 수 있습니다.  `name`을 인쇄하려면 다음을 수행하지 마세요.  
>   
>  `printf( name ); /* Danger!  If name contains "%s", program will crash */`  
>   
>  대신 이 작업을 수행하세요.  
>   
>  `printf( "%s", name );`  
  
## 참고 항목  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [printf\_p 위치 매개 변수](../c-runtime-library/printf-p-positional-parameters.md)   
 [플래그 지시문](../c-runtime-library/flag-directives.md)   
 [printf 너비 사양](../c-runtime-library/printf-width-specification.md)   
 [전체 자릿수 사양](../c-runtime-library/precision-specification.md)   
 [크기 사양](../c-runtime-library/size-specification.md)   
 [printf 형식 필드 문자](../c-runtime-library/printf-type-field-characters.md)