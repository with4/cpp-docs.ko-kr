---
title: "_setmbcp | Microsoft Docs"
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
  - "_setmbcp"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_setmbcp"
  - "setmbcp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_setmbcp 함수"
  - "멀티바이트 코드 페이지"
  - "setmbcp 함수"
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _setmbcp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

새 멀티 바이트 코드 페이지를 설정합니다.  
  
## 구문  
  
```  
int _setmbcp(  
   int codepage   
);  
```  
  
#### 매개 변수  
 `codepage`  
 로캘 독립적인 멀티 바이트 루틴에 대한 새 코드 페이지 설정.  
  
## 반환 값  
 만일 코드 페이지를 성공적으로 설정된 경우, 0을 반환합니다.  만일 잘못된 코드 페이지 값이 `codepage` 에 의해 제공되는 경우, \-1을 반환하고 코드 페이지 설정은 변경되지 않습니다.  만일 메모리 할당 오류가 발생한 경우, `errno` 는 `EINVAL` 로 설정됩니다.  
  
## 설명  
 `_setmbcp` 함수는 새 멀티바이트 코드 페이지를 지정합니다.  기본적으로, 런타임시스템은 기본적으로 멀티바이트 코드 페이지를 시스템 기본 ANSI 코드 페이지로 설정합니다.  멀티 바이트 코드 페이지 설정은 로캘에 종속 되지 않는 모든 멀티 바이트 루틴에 영향을 끼칩니다.  그러나, 이것은 현재 로캘\(다음 매니페스트 상수들과 동작 결과와 연결된 목록을 참고\)에 대해 정의된 코드 페이지를 사용하기 위해 `_setmbcp` 지시하는 것이 가능합니다.  멀티바이트 코드페이지보다 로캘 코드페이지에 따라 멀티바이트 루틴들의 목록에 대하여, [멀티 바이트 문자 순서의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)을 참고하세요.  
  
 멀티 바이트 코드 페이지 역시 다음 런타임 라이브러리 루틴들에 의해 멀티바이트 문자 처리에 영향을 미칩니다.  
  
||||  
|-|-|-|  
|[\_exec 함수](../../c-runtime-library/exec-wexec-functions.md)|[\_mktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)|[\_stat](../../c-runtime-library/reference/stat-functions.md)|  
|[\_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[\_spawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)|[\_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[\_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)|[\_splitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)|[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
  
 또한, \(`_exec` `_spawn` 와 같은\)매개변수로써 `envp` 프로그램 인수들 또는 멀티 바이트 문자 `argv` 를 받는 모든 런타임 라이브러리 루틴은 멀티바이트 코드 페이지에 따라 이들 문자열을 처리합니다.  따라서, 이러한 루틴 역시 멀티바이트 코드 페이지를 변경하는 `_setmbcp` 를 호출에 의해 영향을 받습니다.  
  
 `codepage` 인수 값은 다음 중 하나로 설정할 수 있습니다:  
  
-   \_MB\_CP\_ANSI 는 프로그램이 시작할 때, 운영체제로부터 얻어지는 ANSI 코드 페이지를 사용합니다.  
  
-   `_MB_CP_LOCALE` 는 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 로 이전에 호출하여 얻은 현재 로캘의 코드 페이지를 사용합니다.  
  
-   `_MB_CP_OEM` 는 프로그램이 사작할 때 운영체제로부터 얻어진 OEM 코드페이지를 사용합니다.  
  
-   `_MB_CP_SBCS` 는 단일 바이트 코드 페이지를 사용합니다.  코드 페이지가 `_MB_CP_SBCS` 로 설정될 때, [ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md) 같은 루틴은 항상 false를 반환합니다.  
  
-   모든 다른 유효한 코드 페이지 값과 값이 ANSI, OEM 또는 다른 운영체제가 지원되는 코드 페이지\(지원되지 않는 UTF\-7과 UTF\-8을 제외하고\)인지의 여부는 관계가 없습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_setmbcp`|\<mbctype.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 참고 항목  
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)