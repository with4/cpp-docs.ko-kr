---
title: "_get_osfhandle | Microsoft Docs"
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
  - "_get_osfhandle"
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
  - "get_osfhandle"
  - "_get_osfhandle"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "운영 체제, 파일 핸들 가져오기"
  - "get_osfhandle 함수"
  - "_get_osfhandle 함수"
  - "파일 핸들[C++], 운영 체제"
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_osfhandle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정 된 파일 설명자와 연결 된 운영 체제 파일 핸들을 검색 합니다.  
  
## 구문  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
#### 매개 변수  
 `fd`  
 기존 파일 설명자입니다.  
  
## 반환 값  
 `fd` 가 유효한 경우, 운영 체제 파일 핸들입니다.  그렇지 않으면, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명 된 대로 잘못 된 매개 변수 처리기가 호출됩니다.  실행이 계속 되도록 허용된 경우, 함수는 잘못 된 파일 핸들을 나타내는 `INVALID_HANDLE_VALUE` \(\-1\) 을 반환하고 `errno` 를 `EBADF` 로 설정합니다.  
  
## 설명  
 `_get_osfhandle` 을 사용하여 열린 파일을 닫으려면 `_close` 을 호출하십시오.  기본 핸들도 `_close` 에 대한 호출로 닫힙니다. 따라서 원래 핸들에 대해 Win32 함수 `CloseHandle` 를 호출할 필요가 없습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_osfhandle`|\<io.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)