---
title: "_splitpath, _wsplitpath | Microsoft Docs"
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
  - "_wsplitpath"
  - "_splitpath"
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
  - "wsplitpath"
  - "_splitpath"
  - "splitpath"
  - "_wsplitpath"
  - "_tsplitpath"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_splitpath 함수"
  - "_tsplitpath 함수"
  - "_wsplitpath 함수"
  - "경로 이름"
  - "경로 이름"
  - "splitpath 함수"
  - "tsplitpath 함수"
  - "wsplitpath 함수"
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _splitpath, _wsplitpath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

경로 이름을 구성 요소로 나누기.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)를 참조하십시오.  
  
## 구문  
  
```  
void _splitpath(  
   const char *path,  
   char *drive,  
   char *dir,  
   char *fname,  
   char *ext   
);  
void _wsplitpath(  
   const wchar_t *path,  
   wchar_t *drive,  
   wchar_t *dir,  
   wchar_t *fname,  
   wchar_t *ext   
);  
```  
  
#### 매개 변수  
 `path`  
 전체 경로  
  
 `drive`  
 드라이브 문자, 콜론 \(`:`\).  드라이브 문자가 필요하지 않은 경우, 매개 변수에 대해 `NULL` 를 전달할 수 있습니다.  
  
 `dir`  
 후행 슬래시를 포함 한 디렉터리 경로입니다.  착신 전환 슬래시 \( `/`\), 백슬래시 \( `\` \), 또는 둘 모두를 사용할 수 있습니다.  디렉토리 경로가 필요하지 않은 경우, 매개 변수에 대해 `NULL` 를 전달할 수 있습니다.  
  
 `fname`  
 기본 파일 이름 \(확장명 제외\)입니다.  파일 이름이 필요하지 않은 경우, 매개 변수에 대해 `NULL` 를 전달할 수 있습니다.  
  
 `ext`  
 앞에 기간을 포함 하는 \(`.`\) 파일 확장명입니다.  파일 이름 확장명이 필요하지 않은 경우, 매개 변수에 대해 `NULL` 를 전달할 수 있습니다.  
  
## 설명  
 `_splitpath` 함수는 네 가지 구성 요소로 경로를 중단 합니다.  `_splitpath` 는 최근에 사용한 멀티 바이트 코드 페이지에 따라서 멀티 바이트 문자 시퀀스를 인식하는 멀티 바이트 문자 문자열 인수를 자동으로 적절하게 처리 합니다.  `_wsplitpath`는 `_splitpath`의 와이드 문자 버전이며, `_wsplitpath`에 대한 인수는 와이드 문자 문자열입니다.  그렇지 않다면 이러한 함수는 동일하게 작동합니다.  
  
 **보안 정보** 이 함수는 버퍼 오버런 문제에 대한 상태로 잠재적인 위협을 초래 합니다.  버퍼 오버런 문제는 자주 사용되는 시스템 공격 방법으로, 불필요한 권한 상승을 초래합니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  더 안전한 버전의 이 함수를 사용할 수 있습니다. [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md). 를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tsplitpath`|`_splitpath`|`_splitpath`|`_wsplitpath`|  
  
 전체 경로의 각 구성 요소는 별도 버퍼에 저장 됩니다. 매니페스트 상수 `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME`, 및 `_MAX_EXT` 는 \(STDLIB.H 에 정의 된\) 각 파일 구성 요소에 대한 최대 허용 크기를 지정 합니다.  해당 매니페스트 상수보다 큰 파일 구성 요소는 힙 손상을 유발합니다.  
  
 각 버퍼는 잠재적인 버퍼 오버런은 방지하기 위해 해당 매니페스트 상수보다 같거나 커야 합니다.  
  
 다음 표에서는 매니페스트 상수의 값을 보여줍니다.  
  
|Name|값|  
|----------|-------|  
|\_MAX\_DRIVE|3|  
|\_MAX\_DIR|256|  
|\_MAX\_FNAME|256|  
|\_MAX\_EXT|256|  
  
 전체 경로가 구성 요소 \(예를 들어, 파일 이름\)를 포함하지 않으면, `_splitpath` 는 해당 버퍼에 빈 문자열을 할당 합니다.  
  
 필요하지 않는 `path`  이외에 다른 매개 변수에 대해 `NULL` 을 `_splitpath` 에 전달할 수 있습니다.  
  
 `path`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `EINVAL` 을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_splitpath`|\<stdlib.h\>|  
|`_wsplitpath`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 예제를 보려면 [\_makepath](../../c-runtime-library/reference/makepath-wmakepath.md) 를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)