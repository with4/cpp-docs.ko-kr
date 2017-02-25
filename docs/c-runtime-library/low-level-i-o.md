---
title: "하위 수준 I/O | Microsoft Docs"
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
  - "파일 핸들[C++]"
  - "파일 핸들[C++], I/O 함수"
  - "I/O[CRT], 함수"
  - "I/O[CRT], 하위 수준"
  - "하위 수준 I/O 루틴"
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 하위 수준 I/O
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 함수는 스트림 I\/O가 제공하는 것보다 낮은 수준의 운영 체제를 직접적으로 호출합니다.  낮은 레벨의 입출력 호출은 데이터를 버퍼 또는 형식화하지 않습니다.  
  
 낮은 레벨의 루틴은 프로그램이 시작할 때 다음 미리 정의된 파일 기술자를 사용하여 열리는 표준 스트림에 액세스할 수 있습니다.  
  
|스트림|파일 설명자|  
|---------|------------|  
|`stdin`|0|  
|`stdout`|1|  
|`stderr`|2|  
  
 낮은 수준 I\/O 루틴은 오류가 발생하면 [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 전역 변수를 설정합니다.  프로그램이 파일 끝 표시기\(`EOF`\)와 같은 STDIO.H에 정의된 상수를 요구하는 낮은 수준의 함수를 사용할 때는 반드시 STDIO.H를 포함해야만 합니다.  
  
### 낮은 수준 I\/O 함수  
  
|Function|기능|  
|--------------|--------|  
|[\_close](../c-runtime-library/reference/close.md)|파일 닫기|  
|[\_commit](../c-runtime-library/reference/commit.md)|파일을 디스크에 플러시|  
|[\_creat, \_wcreat](../c-runtime-library/reference/creat-wcreat.md)|파일을 만듭니다.|  
|[\_dup](../c-runtime-library/reference/dup-dup2.md)|주어진 파일에 대해 다음 사용 가능한 파일 기술자를 반환합니다.|  
|[\_dup2](../c-runtime-library/reference/dup-dup2.md)|주어진 파일의 두 번째 파일 기술자를 생성합니다.|  
|[\_eof](../c-runtime-library/reference/eof.md)|파일의 끝에 대한 테스트입니다.|  
|[\_lseek, \_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|파일 포인터를 주어진 위치로 위치 변경합니다.|  
|[\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)|파일 열기|  
|[\_read](../c-runtime-library/reference/read.md)|파일에서 데이터 읽기|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md), [\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|파일 공유를 위해 파일 열기|  
|[\_tell, \_telli64](../c-runtime-library/reference/tell-telli64.md)|파일 포인터의 현재 위치를 가져옵니다.|  
|[\_umask](../c-runtime-library/reference/umask.md), [\_umask\_s](../c-runtime-library/reference/umask-s.md)|파일 권한 마스크를 설정|  
|[\_write](../c-runtime-library/reference/write.md)|파일에 데이터 쓰기|  
  
 `_dup` 및 `_dup2`는 일반적으로 미리 정의된 파일 기술자를 다른 파일들에 연결하는 데에 사용됩니다.  
  
## 참고 항목  
 [입력 및 출력](../c-runtime-library/input-and-output.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [시스템 호출](../c-runtime-library/system-calls.md)