---
title: "텍스트 및 이진 모드의 유니코드 스트림 I/O | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "I/O[CRT], 유니코드 스트림"
  - "스트림 I/O 루틴"
  - "유니코드 스트림 I/O"
  - "Unicode, 스트림 I/O 루틴"
ms.assetid: 68be0c3e-a9e6-4fd5-b34a-1b5207f0e7d6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 텍스트 및 이진 모드의 유니코드 스트림 I/O
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

유니코드 스트림 I\/O 루틴\(`fwprintf`, `fwscanf`, `fgetwc`, `fputwc`ㅡ `fgetws`, 또는 `fputws`와 같은\)은 두 종류의 문자 변환이 일어나는 텍스트 모드\(기본값\)로 열린 파일에서 동작합니다.  
  
-   유니코드에서 MBCS 또는 유니코드에서 MBCS 변환입니다.  유니코드 스트림 I\/O 함수가 텍스트 모드에서 작동할 경우 소스 또는 대상 스트림은 멀티바이트 문자 시퀀스로 간주됩니다.  따라서 유니코드 스트림 입력 함수는 멀티바이트 문자를 와이드 문자로 변환합니다\(`mbtowc` 함수를 호출한 것으로 간주\).  마찬가지로 유니코드 스트림 출력 함수는 와이드 문자를 멀티바이트 문자로 변환합니다\(`wctomb` 함수를 호출한 것으로 간주\).  
  
-   캐리지 리턴\-줄 바꿈 \(CR\-LF\) 번역  MBCS–유니코드 변환\(유니코드 스트림 입력 함수\) 전 및 유니코드–MBCS 변환\(유니코드 스트림 출력 함수\) 이후에 이 번역은 일어납니다.  입력 하는 동안 각 캐리지 리턴 – 줄 바꿈 조합은 단일 줄 바꿈 문자로 변환됩니다.  출력 하는 동안 각 단일 줄 바꿈 문자는 각 캐리지 리턴 – 줄 바꿈 조합으로 변환됩니다.  
  
 그러나, 유니코드 스트림 I\/O 함수가 이진 모드에서 작동할 때, 파일이 유니코드로 간주되며 CR\-LF 번역 또는 문자 변환이 입력 또는 출력하는 동안 발생합니다.  유니코드 텍스트 파일에서 wcin을 올바르게 사용하기 위해서 \_setmode\( \_fileno\( stdin \), \_O\_BINARY \);를 사용합니다.  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [입력 및 출력](../c-runtime-library/input-and-output.md)