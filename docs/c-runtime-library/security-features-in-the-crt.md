---
title: "CRT의 보안 기능 | Microsoft Docs"
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
  - "_CRT_SECURE_NO_DEPRECATE"
  - "_CRT_NONSTDC_NO_WARNINGS"
  - "_CRT_SECURE_NO_WARNINGS"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRT_NONSTDC_NO_DEPRECATE"
  - "_CRT_NONSTDC_NO_WARNINGS"
  - "_CRT_SECURE_NO_DEPRECATE"
  - "_CRT_SECURE_NO_WARNINGS"
  - "버퍼 오버런"
  - "버퍼[C++], 버퍼 오버런"
  - "CRT, 강화된 보안 기능"
  - "CRT_NONSTDC_NO_DEPRECATE"
  - "CRT_NONSTDC_NO_WARNINGS"
  - "CRT_SECURE_NO_DEPRECATE"
  - "CRT_SECURE_NO_WARNINGS"
  - "사용 중단 경고(보안 관련)"
  - "사용 중단 경고(보안 관련), 비활성화"
  - "매개 변수[C++], 유효성 검사"
  - "보안[CRT]"
  - "보안 사용 중단 경고[C++]"
  - "보안이 강화된 CRT"
ms.assetid: d9568b08-9514-49cd-b3dc-2454ded195a3
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CRT의 보안 기능
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

많은 오래된 CRT 함수는 보다 최신의, 그리고 안전한 버전들을 갖고 있습니다.  만일 보안 함수가 존재하지만, 더 오래되고, 이전의 보안 버전이면 사용되지 않는 것으로 표시되고 새 버전은 `_s`\("secure"\) 접미사를 가집니다.  
  
 이 컨텍스트에서, "사용 되지 않는" 이 의미 하는 함수는 사용하지 마세요: 이 함수는 CRT에서 제거 될 예정입니다.  
  
 보안 함수를 방지하지 않거나 보안 오류를 바로잡습니다; 오류가 발생했을 때, 오류를 받습니다.  오류 조건에 대한 추가적인 검사를 수행하고, 오류에 대한 경우에 따라 오류 처리기를 호출합니다.\([매개 변수 유효성 검사](../c-runtime-library/parameter-validation.md) 를 참고\)  
  
 예를 들어, `strcpy` 함수는 만일 복사되는 문자열이 대상 버퍼에 비해 큰 경우, 알리는 방법이 존재하지 않습니다.  그러나, 이것의 보안에 대응되는 `strcpy_s` 는 매개변수로써 버퍼의 크기를 받고, 만일 버퍼 오버런이 나타날때 결정할 수 있습니다.  만일 10개 문자 버퍼 로 11개 문자가 복사되는 경우 `strcpy_s` 사용하면, 오류가 발생합니다; `strcpy_s` 는 실수를 바로잡을 수는 없지만, 오류를 찾을 수 있고 잘못된 매개변수 처리기를 호출함으로써 알려줍니다.  
  
## 중단 경고를 제거하는 것  
 보안이 취약한 기능의 명령에 대한 중단경고를 제거하기 위한 몇가지 방법이 있습니다.  가장 간단한 것은 `_CRT_SECURE_NO_WARNINGS` 을 정의하는 것이나 [경고](../preprocessor/warning.md) pragma를 사용하는 것입니다.  두 가지 모두 중단 경고를 비활성화하지만, 여전히 경고를 발생시키는 보안적 문제가 존재합니다.  활성화된 중단 경고를 없애는 더 좋은 방법은 새로운 CRT 보안 기능의 장점을 활용하는 것입니다.  
  
 C\+\+에서, [안전한 템플릿 오버로드](../c-runtime-library/secure-template-overloads.md) 을 사용하는 가장 쉬운 방법은, 많은 경우에서 이들 기능의 새로운 보안 버전을 호출함으로써 사용되지 않는 함수들에 대해 호출을 대체하여 중단 경고를 제거하는 것입니다.  예를 들어, `strcpy` 호출은 더 이상 사용되지 않습니다.  
  
```  
char szBuf[10];   
strcpy(szBuf, "test"); // warning: deprecated   
```  
  
 `strcpy_s` 로 `strcpy` 호출을 변경함으로써 경고를 하나 제거하는 것은 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` 정의하여, 버퍼 오버런을 막는 것입니다.  자세한 내용은 [안전한 템플릿 오버로드](../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
 보안 템플릿 오버로드들 없이 중단된 이들 함수에 대해, 보안 버전들을 사용하기 위해 수동으로 코드를 업데이트해야 합니다.  
  
 또다른 보안과 관련되지 않은 중단 경고의 다른 소스는 POSIC 함수들입니다.  POSIX함수들은 이들의 동일한 표준 함수로 대체하거나\(예를 들어 [access](../c-runtime-library/reference/access-crt.md) 를 [\_access](../c-runtime-library/reference/access-waccess.md) 로 변경합니다.\) POSIX 관련 중단 경고를 `_CRT_NONSTDC_NO_WARNINGS` 를 정의함으로써 비활성화합니다.  자세한 내용은 [Deprecated CRT Functions](http://msdn.microsoft.com/ko-kr/7e259932-c6c8-4c1a-9637-639e591681a5)을 참조하십시오.  
  
## 추가 보안 기능  
 다음은 보안 기능 중 일부를 포함합니다.  
  
-   `Parameter Validation`.  보안 함수들과 많은 함수들의 기존 버전에서 모두 CRT 함수로 전달된 매개변수는 인증됩니다.  이러한 유효성 검사는 다음과 같습니다:  
  
    -   함수에 전달된 `NULL` 값에 대한 검사.  
  
    -   열거된 값에 대한 유효성을 검사.  
  
    -   유효 범위내 에서 정수 값이 있는지 검사.  
  
-   자세한 내용은 [매개 변수 유효성 검사](../c-runtime-library/parameter-validation.md)을 참조하십시오.  
  
-   잘못된 매개변수에 대한 처리기 역시 개발자가 액세스 할 수 있습니다.  기존의 응용프로그램과 어셜션 대신 잘못된 매개변수를 발견한 경우, CRT는 [\_set\_invalid\_parameter\_handler, \_set\_thread\_local\_invalid\_parameter\_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) 함수를 사용하여 이런 문제를 검사하는 방법을 제공합니다.  
  
-   `Sized Buffers`.  보안 기능는 버퍼로 쓰는 모든 함수로 전달되는 버퍼 크기를 필요로 합니다.  보안 버전은 이것을 쓰기 전에 버퍼가 충분히 큰지 유효성을 검사하여, 악의적인 코드를 실행할 수 있는 위험한 버퍼 오버런 오류를 피하도록 도와줍니다.  이러한 함수는 일반적으로 오류코드의 `errno` 형식을 반환하고 만일 버퍼의 크기가 너무 작은 경우 잘못된 매개변수 처리기를 호출합니다.  `gets` 와 같은, 입력 버퍼로부터 읽는 기능은 최대값을 지정하기 위해 필요한 보안 버전을 가집니다.  
  
-   `Null termination`.  잠재적으로 끝나지 않는 문자열을 받는 몇몇 함수들은 null로 종료되는 문자열을 확인하는 보안 버전을 가집니다.  
  
-   `Enhanced error reporting`.  보안 기능은 기존에 존재하는 함수들을 사용하여 이용할 수 있는 보다 많은 오류 정보와 함께 오류 코드들을 반환합니다.  보안 함수들과 많은 기존 함수들은 이제 `errno` 을 설정하고 종종 더 나은 오류 보고를 제공하기 위해, `errno` 코드 형식을 반환합니다.  
  
-   `Filesystem security`.  보안 파일 I\/O API들은 기본적으로 파일 액세스를 지원합니다.  
  
-   `Windows security`.  보안 프로세스 API들은 보안 정책을 적용하고 지정된 ACL들을 사용하게 합니다.  
  
-   `Format string syntax checking`.  잘못된 문자열이 발견됩니다. 예를 들어,  `printf` 형식 문자열들에서 잘못된 형식 필드 문자를 사용하는 경우.  
  
## 참고 항목  
 [매개 변수 유효성 검사](../c-runtime-library/parameter-validation.md)   
 [안전한 템플릿 오버로드](../c-runtime-library/secure-template-overloads.md)   
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)