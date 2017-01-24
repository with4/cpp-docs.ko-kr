---
title: "_close | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_close"
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
  - "_close"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_close 함수"
  - "close 함수"
  - "파일[C++], 닫기"
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일을 닫습니다.  
  
## 구문  
  
```  
int _close(   
   int fd   
);  
```  
  
#### 매개 변수  
 `fd`  
 열려 있는 파일을 나타내는 파일 기술자입니다.  
  
## 반환 값  
 파일을 성공적으로 닫은 경우 `_close`는 0을 반환합니다.  반환값 \-1 은 오류를 나타냅니다.  
  
## 설명  
 `_close` 함수는 `fd`에 연결된 파일을 닫습니다.  
  
 파일 기술자와 기본 운영 체제의 파일 처리기가 닫힙니다.  그러므로, 파일이 원래 Win32 함수 `CreateFile`를 이용하여 열렸고 `_open_osfhandle`를 이용하여 파일 기술자로 변경되었다면 `CloseHandle`를 호출하는 것은 필수적이지 않습니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  여기 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 `fd` 이 잘못된 파일 기술자인 경우 잘못된 매개 변수 처리기가 호출됩니다.  실행이 계속되도록 허용된 경우, 이 함수는 \-1을 반환하고 `errno`를 `EBADF`로 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_close`|\<io.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [\_open](../../c-runtime-library/reference/open-wopen.md)의 예제를 참조하십시오.  
  
## 참고 항목  
 [하위 수준 I\/O](../../c-runtime-library/low-level-i-o.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_unlink, \_wunlink](../../c-runtime-library/reference/unlink-wunlink.md)