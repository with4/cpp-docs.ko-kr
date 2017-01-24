---
title: "링크 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "nothrownew.obj"
  - "newmode.obj"
  - "noenv.obj"
  - "psetargv.obj"
  - "loosefpmath.obj"
  - "smallheap.obj"
  - "fp10.obj"
  - "nochkclr.obj"
  - "chkstk.obj"
  - "pcommode.obj"
  - "pnoenv.obj"
  - "링크 옵션[C++]"
  - "invalidcontinue.obj"
  - "pnothrownew.obj"
  - "pwsetargv.obj"
  - "pinvalidcontinue.obj"
  - "wsetargv.obj"
  - "binmode.obj"
  - "setargv.obj"
  - "noarg.obj"
  - "pnewmode.obj"
  - "commode.obj"
  - "pthreadlocale.obj"
  - "pbinmode.obj"
  - "threadlocale.obj"
  - "pnoarg.obj"
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링크 옵션
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

CRT lib 디렉토리의 CRT 기능 코드를 변경 하지 않고 사용할 수 있는 작은 개체 파일에 있습니다.  그것을 사용하기 위해 링커 명령줄에 그것을 추가해야 하기 때문에 "링크 옵션" 이라고 부릅니다.  
  
 순수 모드 버전이 추가 되었습니다.  \/clr 및 네이티브 코드에 대한 일반 버전을 사용, \/clr:pure 모드에 대한 순수 버전\(a p 접두사로\) 사용  
  
|네이티브 및 \/clr|순수 모드|설명|  
|------------------|-----------|--------|  
|binmode.obj|pbinmode.obj|기본 파일 변환 모드를 이진으로 설정합니다.  [\_fmode](../c-runtime-library/fmode.md)를 참조하십시오.|  
|chkstk.obj|해당 없음|CRT 를 사용하지 않을 때 스택 검사 및 alloca 지원 기능을 제공합니다.|  
|commode.obj|pcommode.obj|전역 commit 플래그를 "commit"으로 설정합니다.  [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md) 및 [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)을 참조하십시오.|  
|fp10.obj|해당 없음|기본 정밀도 제어를 64 비트로 변경합니다.  [부동 소수점 지원](../c-runtime-library/floating-point-support.md)를 참조하십시오.|  
|invalidcontinue.obj|pinvalidcontinue.obj|아무것도 하지 않는 기본 잘못 된 매개 변수 처리기를 설정하는 것은 CRT 함수로 전달 된 잘못 된 매개 변수가 errno를 설정하고 오류 결과를 반환하는 것을 의미합니다.|  
|loosefpmath.obj|해당 없음|부동 소수점 코드는 비정상 적인 값을 용인 합니다.|  
|newmode.obj|pnewmode.obj|실패 시 새 처리기를 호출하기 위해 [malloc](../c-runtime-library/reference/malloc.md) 를 사용합니다.  [\_set\_new\_mode](../c-runtime-library/reference/set-new-mode.md), [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md) 및 [realloc](../c-runtime-library/reference/realloc.md)를 참조하십시오.|  
|noarg.obj|pnoarg.obj|argc 및 argv 의 모든 처리를 비활성화 합니다.|  
|nochkclr.obj|해당 없음|아무 작업도 하지 않습니다.  프로젝트에서 제거 합니다.|  
|noenv.obj|pnoenv.obj|CRT에 대해 캐시 된 환경을 만들 수 없습니다.|  
|nothrownew.obj|pnothrownew.obj|CRT에서 새 버전은 던지지 않을 수 있습니다.  [new 및 delete 연산자](../cpp/new-and-delete-operators.md)를 참조하십시오.|  
|setargv.obj|psetargv.obj|명령 줄 인수 와일드 카드 확장이 가능합니다.  [와일드카드 인수 확장](../c-language/expanding-wildcard-arguments.md)를 참조하십시오.|  
|smalheap.obj|해당 없음|아주 간단한 작은 힙 관리자를 설치합니다.|  
|threadlocale.obj|pthreadlocale.obj|기본적으로 모든 새 스레드들에 대해 각 스레드 로캘이 사용가능합니다.|  
|wsetargv.obj|pwsetargv.obj|명령 줄 인수 와일드 카드 확장이 가능합니다.  [와일드카드 인수 확장](../c-language/expanding-wildcard-arguments.md)를 참조하십시오.|  
  
## 참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)