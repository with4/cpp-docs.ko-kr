---
title: "텍스트 및 이진 모드 파일 I/O | Microsoft Docs"
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
  - "이진 액세스"
  - "이진 액세스, 이진 모드 파일 I/O"
  - "파일[C++], 열기 함수"
  - "함수[CRT], 파일 액세스"
  - "I/O[CRT], 이진"
  - "I/O[CRT], 텍스트 파일"
  - "I/O[CRT], 변환 모드"
  - "텍스트 파일, I/O"
  - "변환 모드(파일 I/O)"
  - "변환, 모드"
ms.assetid: 3196e321-8b87-4609-b302-cd6f3c516051
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 텍스트 및 이진 모드 파일 I/O
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

파일 I\/O 작업은 텍스트 또는 이진, 두 변환 모드중 하나에서 파일이 열린 모드에 따라 발생합니다.  데이터 파일은 일반적으로 텍스트 모드에서 처리 됩니다.  파일 변환 모드를 제어 하려면 하나 다음과 같은 작업을 수행할 수 있습니다.  
  
-   현재 기본 설정을 유지 하고 선택한 파일을 열 때 다른 모드를 지정 합니다.  
  
-   [\_set\_fmode](../c-runtime-library/reference/set-fmode.md) 함수를 사용하여 새로 열린 파일에 대한 기본 모드를 변경합니다.  [\_get\_fmode](../c-runtime-library/reference/get-fmode.md) 를 사용하여 현재 기본 모드를 찾습니다.  초기 기본값은 텍스트 모드입니다. \(`_O_TEXT`\).  
  
-   프로그램에서 [\_fmode](../c-runtime-library/fmode.md) 전역변수를 직접적으로 설정하여 기본 변환 모드를 변경합니다.  함수 `_set_fmode` 는 이 변수의 값을 설정하지만 직접적으로 설정해야 합니다.  
  
 [\_open](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [\_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) 또는 [\_sopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md) 와 같은 파일 열기 함수를 호출 할 때, `_fmode` 의 현재 기본 설정을 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md) 함수에 대해 적절한 인수를 지정함으로서 오버라이드할 수 있습니다.  `stdin`, `stdout`, 및 `stderr` 스트림은 기본적으로 텍스트 모드에서 열리고, 이러한 파일을 열 때 기본값을 재정의 할 수도 있습니다.  [\_setmode](../c-runtime-library/reference/setmode.md) 를 사용하여 파일이 열린 후에 파일 설명자를 사용하여 변환 모드를 변경할 수 있습니다.  
  
## 참고 항목  
 [입력 및 출력](../c-runtime-library/input-and-output.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)