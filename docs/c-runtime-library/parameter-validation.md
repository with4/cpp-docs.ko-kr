---
title: "매개 변수 유효성 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "매개 변수, 유효성 검사"
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 매개 변수 유효성 검사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대부분의 보안 CRT 함수 및 대부분의 기존 함수 매개 변수를 확인합니다.  Null 포인터 검사, 검사 유효 범위에 속하는 정수 또는 열거형 값이 유효한 지 확인하는 것을 포함합니다.  잘못 된 매개 변수가 발견 되면 잘못 된 매개 변수 처리기가 실행 됩니다.  
  
## 잘못 된 매개 변수 처리기 루틴  
 잘못 된 매개 변수가 발견 되면 C 런타임 동작은 현재 할당 된 잘못 된 매개 변수 처리기를 호출 합니다.  잘못 된 기본 매개 변수는 응용 프로그램 충돌 및 분석을 위해 Microsoft에 크래시 덤프를 로드할 것인지 묻는 Watson 크래시 보고를 호출 합니다.  디버그 모드에서 잘못 된 매개 변수는 또한 실패한 어설션에 발생합니다.  
  
 이 동작은 [\_set\_invalid\_parameter\_handler, \_set\_thread\_local\_invalid\_parameter\_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) 함수를 사용하여 잘못된 매개 변수 처리기를 자체 함수로 설정하여 변경할 수 있습니다.  사용자가 지정한 함수가 응용 프로그램을 종료하지 않으면 컨트롤은 잘못된 매개 변수를 받는 함수에게 반환됩니다. 그리고 이러한 함수는 일반적으로 에러 코드를 반환하며 실행을 중단하고 `errno` 를 에러 코드로 설정합니다.  대부분의 경우에는 `errno` 값과 반환 값은 모두 잘못된 매개 변수를 나타내는 `EINVAL` 입니다.  경우에 따라 잘못된 파일 포인터를 매개 변수로 전달하는 `EBADF` 과 같은 구체적인 오류 코드를 반환합니다.  errno 에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 참고 항목  
 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md)   
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)