---
title: "안전한 템플릿 오버로드 | Microsoft Docs"
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
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT"
  - "보안 템플릿 오버로드"
ms.assetid: 562741d0-39c0-485e-8529-73d740f29f8f
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 안전한 템플릿 오버로드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

더 새롭고, 보안이 강화된 버전 덕에 많은 CRT 함수가 더 이상 사용되지 않습니다. \(예를 들어, `strcpy_s`는 `strcpy`보다 더 안전한 대체입니다.\)  CRT는 더 안전한 변형으로의 전환을 용이하게 하기 위하여 템플릿 오버로드를 제공합니다.  
  
 예를 들어, 이 코드는 `strcpy`가 더 이상 사용되지 않기 때문에 경고를 발생시킵니다.  
  
 `char szBuf[10];`  
  
 `strcpy(szBuf, "test"); // warning: deprecated`  
  
 이 경고를 무시할 수 있습니다.  이 경고를 나타내지 않게 하기 위하여 `_CRT_SECURE_NO_WARNINGS` 기호를 정의하거나 `strcpy_s`를 사용하는 코드로 업데이트합니다.  
  
 `char szBuf[10];`  
  
 `strcpy_s(szBuf, 10, "test"); // security-enhanced _s function`  
  
 템플릿 오버로드는 추가 옵션을 제공합니다.  `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES`를 1로 정의하는 것은 더 안전한 변형을 자동으로 호출하는 표준 CRT 함수의 템플릿 오버로드를 활성화시킵니다.  만약 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES`가 1이면, 코드에 어떠한 변경도 필요하지 않습니다.  내부적으로, `strcpy`의 호출은 자동으로 제공된 크기 인수와 함께 `strcpy_s`의 호출로 변경됩니다.  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1`  
  
 `...`  
  
 `char szBuf[10];`  
  
 `strcpy(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")`  
  
 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES`는 `strncpy`와 같이 수를 세는 함수에 영향을 미치지 않습니다.  수를 세는 함수에 대해 템플릿 오버로드를 적용시키려면, `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT`를 1로 정의합니다.  그러나 이를 수행하기 전에, 코드가 버퍼의 크기가 아니라 문자의 수를 전달하는지를 확실히 해야 합니다. \(보편적인 실수\)  또한 안전한 변형이 호출되었을 때, 함수 호출 이후 버퍼의 끝에 명시적으로 null 종료 문자를 쓰는 코드는 필요하지 않습니다.  잘라내기 동작을 해야 할 경우에는 [\_TRUNCATE](../c-runtime-library/truncate.md)를 참조하십시오.  
  
> [!NOTE]
>  `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` 매크로는 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES`도 또한 1로 정의될 것을 요구합니다.  `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT`가 1로 정의되고 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES`이 0으로 정의되면, 응용 프로그램은 템플릿 오버로드를 수행하지 않습니다.  
  
 `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES`를 1로 정의하는 것은 안전한 변형\("\_s"로 끝나는 이름\)의 템플릿 오버로드를 활성화시킵니다.  이 경우, `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES`이 1이면, 원본 코드에서 작은 변경 하나가 있어야 합니다.  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1`  
  
 `...`  
  
 `char szBuf[10];`  
  
 `strcpy_s(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")`  
  
 함수의 이름만 바뀔 필요가 있습니다\("\_s"를 추가함으로써\). 템플릿 오버로드는 크기 인수 제공을 관할합니다.  
  
 기본적으로, `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` 및 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT`는 0\(사용 안 함\)으로 정의되고 `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES`은 1\(사용\)로 정의됩니다.  
  
 이러한 템플릿 오버로드는 정적 배열에만 작업된다는 것을 유의하십시오.  추가 소스 코드를 변경해야 하는 동적으로 할당된 버퍼입니다.  위 예제를 다시 봅니다.  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1`  
  
 `...`  
  
 `char *szBuf = (char*)malloc(10);`  
  
 `strcpy(szBuf, "test"); // still deprecated; have to change to`  
  
 `// strcpy_s(szBuf, 10, "test");`  
  
 또 다른 예입니다.  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1`  
  
 `...`  
  
 `char *szBuf = (char*)malloc(10);`  
  
 `strcpy_s(szBuf, "test"); // doesn't compile; have to change to`  
  
 `// strcpy_s(szBuf, 10, "test");`  
  
## 참고 항목  
 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md)   
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)