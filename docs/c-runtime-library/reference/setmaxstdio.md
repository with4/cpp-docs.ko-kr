---
title: "_setmaxstdio | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setmaxstdio"
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
  - "setmaxstdio"
  - "_setmaxstdio"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_setmaxstdio 함수"
  - "열려 있는 최대 파일 개수"
  - "열려 있는 파일, 최대"
  - "setmaxstdio 함수"
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _setmaxstdio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`stdio` 레벨에서 동시에 시작되는 파일의 최대 숫자를 설정합니다.  
  
## 구문  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### 매개 변수  
 `newmax`  
 `stdio` 레벨에서 동시에 시작되는 파일의 최대 숫자.  
  
## 반환 값  
 성공하면, `newmax` 를 반환하고, 그렇지 않으면 \-1를 반환합니다.  
  
 만일 `newmax` 이 `_IOB_ENTRIES` 보다 적거나 운영체제에서 이용할 수 있는 최대 갯수의 처기리보다 큰 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 것처럼 잘못된 처리기가 호출됩니다.  이 예외가 계속 되는 경우, 이 함수는 \-1을 반환하고 `errno` 을 `EINVAL` 로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_setmaxstdio` 함수는 `stdio` 수준에서 동시에 시작될 수 있는 파일의 최대 갯수를 변경합니다.  
  
 C 런타임 I\/O는 이전 버전보다 Win32 플랫폼에서 더 많은 파일들을 열 수 있도록 지원합니다.  동시에 [lowio 수준](../../c-runtime-library/low-level-i-o.md) \(즉, `_open`, `_read` , `_write` 등 I\/O 함수들에 의해 열리거나 액세스된\) 에서 동시에 최대 2,048개의 파일들을 열 수 있습니다.  동시에 [studio 수준](../../c-runtime-library/stream-i-o.md) \(즉, `fopen`, `fgetc` , `fputc` 등의 함수들에 의해 열리거나 액세스된\) 에서는 동시에 최대 512개의 파일들을 열 수 있습니다.  `stdio` 수준에서 512개의 제한은 `_setmaxstdio` 함수로 최대 2,048개까지 증가시킬 수 있습니다.  
  
 `fopen` 같은 `stdio`\-수준 함수들은 `lowio` 함수들의 기반됨으로써 C런타임 라이브러리를 통해 최대 2048개까지 도잇에 파일을 열거나 액세스합니다,.  
  
> [!NOTE]
>  이 상한 기능이외의 것은 특정 Win32 플랫폼 및 구성에 의해 지원됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_setmaxstdio`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 `_setmaxstdio` 을 사용하는 예제로 [\_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md) 를 참고하세요.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)