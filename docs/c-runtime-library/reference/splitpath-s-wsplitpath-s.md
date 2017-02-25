---
title: "_splitpath_s, _wsplitpath_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wsplitpath_s"
  - "_splitpath_s"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wsplitpath_s"
  - "splitpath_s"
  - "_splitpath_s"
  - "wsplitpath_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_splitpath_s 함수"
  - "_wsplitpath_s 함수"
  - "경로 이름"
  - "경로 이름"
  - "splitpath_s 함수"
  - "wsplitpath_s 함수"
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# _splitpath_s, _wsplitpath_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

경로 이름을 구성 요소로 나누기.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 에 설명된 대로 보안 향상 기능이 포함된 [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md) 의 버전입니다.  
  
## 구문  
  
```  
errno_t _splitpath_s(  
   const char * path,  
   char * drive,  
   size_t driveNumberOfElements,  
   char * dir,  
   size_t dirNumberOfElements,  
   char * fname,  
   size_t nameNumberOfElements,  
   char * ext,   
   size_t extNumberOfElements  
);  
errno_t _wsplitpath_s(  
   const wchar_t * path,  
   wchar_t * drive,  
   size_t driveNumberOfElements,  
   wchar_t *dir,  
   size_t dirNumberOfElements,  
   wchar_t * fname,  
   size_t nameNumberOfElements,  
   wchar_t * ext,  
   size_t extNumberOfElements  
);  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _splitpath_s(  
   const char *path,  
   char (&drive)[drivesize],  
   char (&dir)[dirsize],  
   char (&fname)[fnamesize],  
   char (&ext)[extsize]  
); // C++ only  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _wsplitpath_s(  
   const wchar_t *path,  
   wchar_t (&drive)[drivesize],  
   wchar_t (&dir)[dirsize],  
   wchar_t (&fname)[fnamesize],  
   wchar_t (&ext)[extsize]  
); // C++ only  
```  
  
#### 매개 변수  
 \[in\] `path`  
 전체 경로  
  
 \[out\] `drive`  
 드라이브 문자, 콜론 \(`:`\).  드라이브 문자가 필요하지 않은 경우, 매개 변수에 대해 `NULL` 를 전달할 수 있습니다.  
  
 \[in\] `driveNumberOfElements`  
 `drive` 버퍼의 크기는 단일 바이트 또는 와이드 문자 입니다.  `drive` 가 `NULL` 인 경우, 이 값은 0 이어야 합니다.  
  
 \[out\] `dir`  
 후행 슬래시를 포함 한 디렉터리 경로입니다.  착신 전환 슬래시 \( `/` \), 백슬래시 \( `\` \), 또는 둘 모두를 사용할 수 있습니다.  디렉토리 경로가 필요하지 않은 경우, 매개 변수에 대해 `NULL` 를 전달할 수 있습니다.  
  
 \[in\] `dirNumberOfElements`  
 `dir` 버퍼의 크기는 단일 바이트 또는 와이드 문자 입니다.  `dir` 가 `NULL` 인 경우, 이 값은 0 이어야 합니다.  
  
 \[out\] `fname`  
 기본 파일 이름 \(확장자가 없는\)입니다.  파일 이름이 필요하지 않은 경우, 매개 변수에 대해 `NULL` 를 전달할 수 있습니다.  
  
 \[in\] `nameNumberOfElements`  
 `fname` 버퍼의 크기는 단일 바이트 또는 와이드 문자 입니다.  `fname` 가 `NULL` 인 경우, 이 값은 0 이어야 합니다.  
  
 \[out\] `ext`  
 앞의 기간\(**.**\)을 포함하는 파일 확장명입니다. 파일 이름 확장명이 필요 없는 경우 이 매개 변수에 대해 `NULL` 를 전달할 수 있습니다.  
  
 \[in\] `extNumberOfElements`  
 `ext` 버퍼의 크기는 단일 바이트 또는 와이드 문자 입니다.  `ext` 가 `NULL` 인 경우, 이 값은 0 이어야 합니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
### 오류 조건  
  
|조건|반환 값|  
|--------|----------|  
|`path` 가 `NULL`입니다.|`EINVAL`|  
|`drive` 가 `NULL` 이고, `driveNumberOfElements` 는 0이 아닙니다.|`EINVAL`|  
|`drive` 가 `NULL` 이 아니고, `driveNumberOfElements` 는 0입니다.|`EINVAL`|  
|`dir` 는 `NULL` 이고 `dirNumberOfElements` 는 0이 아닙니다.|`EINVAL`|  
|`dir` 는 `NULL` 이 아니고 `dirNumberOfElements` 는 0입니다.|`EINVAL`|  
|`fname` 는 `NULL` 이고 `nameNumberOfElements` 는 0이 아닙니다.|`EINVAL`|  
|`fname` 는 `NULL` 이 아니고, `nameNumberOfElements` 는 0 입니다.|`EINVAL`|  
|`ext` 는 `NULL` 이고 `extNumberOfElements` 는 0이 아닙니다.|`EINVAL`|  
|`ext` 는 `NULL` 이 아니고 `extNumberOfElements` 는 0입니다.|`EINVAL`|  
  
 위의 조건이 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `EINVAL`을 반환합니다.  
  
 버퍼가 결과를 담기에 너무 짧은 경우, 이러한 함수는 모든 버퍼를 빈 문자열로 지우고, `errno` 를 `ERANGE` 로 설정하고 `ERANGE` 를 반환합니다.  
  
## 설명  
 `_splitpath_s`  함수는 네 가지 구성 요소로 경로를 중단 합니다.  `_splitpath_s`  는 최근에 사용한 멀티 바이트 코드 페이지에 따라서 멀티 바이트 문자 시퀀스를 인식하는 멀티 바이트 문자 문자열 인수를 자동으로 적절하게 처리 합니다.  `_wsplitpath_s`  는 `_splitpath_s` 의 와이드 문자 버전입니다. `_``wsplitpath_s` ``  에 대한 인수는 와이드 문자 문자열입니다.  그렇지 않다면 이러한 함수는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 전체 경로의 각 구성 요소는 별도 버퍼에 저장 됩니다. 매니페스트 상수 `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME`, 및 `_MAX_EXT`  는 \(STDLIB.H 에 정의 된\) 각 파일 구성 요소에 대한 최대 허용 크기를 지정 합니다.  해당 매니페스트 상수보다 큰 파일 구성 요소는 힙 손상을 유발합니다.  
  
 다음 표에서는 매니페스트 상수의 값을 보여줍니다.  
  
|Name|값|  
|----------|-------|  
|\_MAX\_DRIVE|3|  
|\_MAX\_DIR|256|  
|\_MAX\_FNAME|256|  
|\_MAX\_EXT|256|  
  
 전체 경로가 구성 요소 \(예를 들어, 파일 이름\)를 포함하지 않으면, `_splitpath_s` 는 해당 버퍼에 빈 문자열을 할당 합니다.  
  
 C\+\+에서는 이러한 함수를 사용하는 것은 템플릿 오버로드에 의해 단순화됩니다; 오버로드는 자동으로 버퍼의 길이를 추정할수 있고, 크기 인수를 지정할 필요를 없앱니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_splitpath_s`|\<stdlib.h\>|  
|`_wsplitpath_s`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)