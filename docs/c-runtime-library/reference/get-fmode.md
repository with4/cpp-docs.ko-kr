---
title: "_get_fmode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_fmode"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_fmode"
  - "_get_fmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_fmode 함수"
  - "파일 변환[C++], 기본 모드"
  - "get_fmode 함수"
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _get_fmode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 I\/O 작업에 대한 기본 파일 변환 모드를 가져옵니다.  
  
## 구문  
  
```  
errno_t _get_fmode(   
   int * pmode   
);  
```  
  
#### 매개 변수  
 \[out\] `pmode`  
 현재 기본 모드를 사용 하여 입력 하는 정수에 대한 포인터: `_O_TEXT` 또는 `_O_BINARY`.  
  
## 반환 값  
 성공 시 0을 반환합니다. 실패 시 오류 코드를 반환합니다.  만일 `pmode` 가 `NULL` 인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 보여주는 것처럼 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `EINVAL` 을 반환합니다.  
  
## 설명  
 이 함수는 [\_fmode](../../c-runtime-library/fmode.md) 전역 변수의 값을 가져 옵니다.  이 변수는 `_open`, `_pipe`, `fopen`, 및 `freopen` 와 같은 모두 낮은 수준에 대한 기본 파일 변환 모드 및 스트림 파일 I\/O 연산자를 지정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_get_fmode`|\<stdlib.h\>|\<fcntl.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 예제를 보려면 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md) 를 참조하십시오.  
  
## NET Framework 사용  
 해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [\_fmode](../../c-runtime-library/fmode.md)   
 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)   
 [텍스트 및 이진 모드 파일 I\/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)