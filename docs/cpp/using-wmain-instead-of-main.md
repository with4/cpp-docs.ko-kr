---
title: "main 대신 wmain 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "wmain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main 함수, wmain과 비교"
  - "wmain 함수"
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# main 대신 wmain 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 유니코드 프로그래밍 모델에서 **main** 함수의 와이드 문자 버전을 정의할 수 있습니다.  유니코드 사양을 준수하는 이식 가능한 코드를 작성할 경우 **main** 대신 **wmain**을 사용합니다.  
  
 **main**과 유사한 형식을 사용하여 **wmain**에 대한 정식 매개 변수를 선언합니다.  와이드 문자 인수 또는 와이드 문자 환경 포인터를 프로그램에 전달할 수 있습니다.  **wmain**에 대한 `argv` 및 `envp` 매개 변수는 `wchar_t*` 형식입니다.  
  
 프로그램이 **main** 함수를 사용하는 경우 프로그램을 시작할 때 운영 체제에 의해 멀티바이트 문자 환경이 만들어집니다.  이 환경의 와이드 문자 복사본은 필요한 경우\(예: [\_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) 또는 [\_wputenv](../c-runtime-library/reference/putenv-wputenv.md) 함수를 호출하는 경우\)에만 만들어집니다.  `_wputenv` 또는 `_wgetenv`의 첫 번째 호출에서 MBCS 환경이 이미 있는 경우 해당 와이드 문자 문자열 환경이 만들어지고 `_environ` 전역 변수의 와이드 문자 버전인 `_wenviron` 전역 변수에 의해 가리킵니다.  이 시점에서 환경 복사본 두 개\(MBCS와 유니코드\)가 동시에 존재하며 프로그램의 수명 내내 운영 체제에 의해 유지 관리됩니다.  
  
 마찬가지로 프로그램이 **wmain** 함수를 사용하는 경우 MBCS\(ASCII\) 환경이 `_putenv` 또는 `getenv`에 대한 첫 번째 호출 시 만들어지고 `_environ` 전역 변수에 의해 가리킵니다.  
  
 MBCS 환경에 대한 자세한 내용은 *런타임 라이브러리 참조*의 [싱글바이트 및 멀티바이트 문자 집합](../c-runtime-library/single-byte-and-multibyte-character-sets.md)을 참조하십시오.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [main: 프로그램 시작](../cpp/main-program-startup.md)