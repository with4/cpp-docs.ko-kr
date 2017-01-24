---
title: "파일 및 스트림 | Microsoft Docs"
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
  - "파일[C++]"
  - "스트림"
ms.assetid: f61e712b-eac9-4c28-bb18-97c3786ef387
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 파일 및 스트림
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로그램은 파일을 읽고 씀으로써 대상 환경과 통신합니다.  파일은 다음 형식일 수 있습니다:  
  
-   반복적으로 읽고 쓸수 있는 데이터를 설정합니다.  
  
-   \(예: 파이프라인\) 프로그램에 의해 생성 되는 바이트 스트림.  
  
-   바이트 스트림을에서 받거나 또는 주변 장치를 전송 합니다.  
  
 마지막 두 항목은 대화형 파일입니다.  파일은 일반적으로 프로그램과 상호 작용 하는 주요 방법입니다.  마찬가지로 이러한 모든 종류의 대부분의 파일을 조작\-라이브러리 함수를 호출합니다.  이러한 대부분의이 함수를 선언하기 위한 STDIO.H 표준 헤더를 포함합니다.  
  
 대부분의 파일 작업을 수행 하기 전에 파일을 열어야 합니다.  파일 스트림, 다양 한 종류의 파일 간에 많은 차이 통해 glosses 표준 C 라이브러리는 데이터 구조를 연결 합니다.  라이브러리 파일 형식의 개체의 각 스트림의 상태를 유지합니다.  
  
 대상 환경 프로그램을 시작하기 전에 세 가지 파일을 엽니다.  두 개의 인수를 사용하여 라이브러리 함수 [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md) 를 호출함으로써 파일을 열 수 있습니다. \(이 `fopen` 함수는 사용되지 않았고, 대신 [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) 를 사용했습니다.\) 첫 번째 인수는 파일 이름입니다.  두 번째 인수는 지정 하는 C 문자열:  
  
-   파일에서 데이터 읽기 또는 데이터 또는 둘 다를 기록 하려는 여부.  
  
-   새 컨텐트 파일 생성 \(또는 이전에 존재 하지 않는 파일을 생성하기 위하여\) 하려는 것인지 또는 기존 콘텐츠를 그대로 둘것인지를 의도합니다.  
  
-   파일에 쓰기는 기존 내용을 변경할 수 있습니다 여부 바이트 파일의 끝에 추가 해야 합니다.  
  
-   텍스트 스트림 또는 이진 스트림을 조작 하려는 여부.  
  
 파일이 성공적으로 열리면 스트림 지향 바이트 \(바이트 스트림\) 인지 여부를 확인할 수 있습니다 또는 와이드 \(와이드 스트림\)를 지향 합니다.  스트림을 처음에 바인딩되어 있지 않습니다.  스트림에서 작동 하도록 특정 함수 호출 동안 다른 특정 기능 수 지향 지향 바이트가 있습니다.  한번 설정됬다면, [fclose](../c-runtime-library/reference/fclose-fcloseall.md) 또는 [freopen](../c-runtime-library/reference/freopen-wfreopen.md) 을 호출할때까지, 스트림은 그 방향을 유지합니다.  
  
 © 1989\-2001 by P.J.  Plauger와 Jim Brodie입니다.  All rights reserved.  
  
## 참고 항목  
 [텍스트 및 이진 스트림](../c-runtime-library/text-and-binary-streams.md)   
 [바이트 및 와이드 스트림](../c-runtime-library/byte-and-wide-streams.md)   
 [스트림 제어](../c-runtime-library/controlling-streams.md)   
 [스트림 상태](../c-runtime-library/stream-states.md)