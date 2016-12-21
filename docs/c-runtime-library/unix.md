---
title: "UNIX | Microsoft Docs"
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
  - "unix"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "POSIX 호환성"
  - "POSIX 파일 이름"
  - "UNIX"
  - "UNIX, 호환성"
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# UNIX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로그램을 UNIX로 이식 하려는 경우 다음의 지침을 따르십시오.  
  
-   헤더 파일을 시스템 하위 디렉터리에서 제거 하지 마십시오.  UNIX 프로그램을 전송 하지 않을 경우에 다른 시스템 헤더 파일을 배치할 수 있습니다.  
  
-   루틴에서 인수로 경로와 파일 이름을 나타내는 문자열을 UNIX 호환 경로 구분 기호로사용합니다.  Win32에서 운영 체제는 백 슬래시 \(\\\) 및 슬래시 \(\/\)를 모두 지원하는 반면, UNIX는 이러한 목적으로 만 슬래시 \(\/\)를 지원합니다.  예를 들어, 따라서 이 문서는 `#include` 문의 경로 구분 기호로서 UNIX 호환 착신 전환 슬래시를사용합니다. \(단, 윈도우 운영 체제 명령 셸, CMD.EXE는 명령 프롬프트에서 입력 한 명령에 슬래시를 지원하지 않습니다.\)  
  
-   UNIX 에서 현재 작업하는 경로 및 파일 이름을 대소문자로 사용합니다.  Win32 운영 체제에서 파일 할당 테이블 \(FAT\) 파일 시스템은 대\/소문자 입니다.. NTFS 파일 시스템 디렉터리 목록은 대\/소문자를 유지 하지만 검색 파일 및 기타 시스템 작업은 대\/소문자를 무시합니다.  
  
    > [!NOTE]
    >  Visual C\+\+, UNIX 호환성의 버전 정보는 함수 설명자에서 제거되었습니다.  
  
## 참고 항목  
 [호환성](../c-runtime-library/compatibility.md)