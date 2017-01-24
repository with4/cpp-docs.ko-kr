---
title: "_rmdir, _wrmdir | Microsoft Docs"
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
  - "_wrmdir"
  - "_rmdir"
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
  - "trmdir"
  - "_trmdir"
  - "wrmdir"
  - "_rmdir"
  - "_wrmdir"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_rmdir 함수"
  - "_trmdir 함수"
  - "_wrmdir 함수"
  - "디렉터리[C++], 제거"
  - "디렉터리[C++], 제거"
  - "rmdir 함수"
  - "trmdir 함수"
  - "wrmdir 함수"
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _rmdir, _wrmdir
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

디렉터리를 삭제합니다.  
  
## 구문  
  
```  
  
      int _rmdir(  
   const char *dirname   
);  
int _wrmdir(  
   const wchar_t *dirname   
);  
```  
  
#### 매개 변수  
 `dirname`  
 삭제할 디렉터리의 경로입니다.  
  
## 반환 값  
 이러한 함수들 각각은 디렉터리가 성공적으로 삭제되면 0을 반환합니다.  반환 값 \-1 은 오류를 나타냅니다. `errno`는 아래 값 중 하나로 설정 됩니다.  
  
 **ENOTEMPTY**  
 주어진 경로가 디렉터리가 아닙니다. 디렉터리가 비어있거나 또는 디렉터리가 현재 루트 디렉터리 또는 현재 작업 디렉터리입니다.  
  
 `ENOENT`  
 경로가 잘못되었습니다.  
  
 **EACCES**  
 프로그램에 디렉터리에 대한 열린 처리기가 있습니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_rmdir` 함수에는 `dirname`에 의해 지정된 디렉터리를 삭제합니다.  디렉터리가 비어 있어야 하며, 루트 디렉터리 또는 현재 작업 디렉터리가 아니어야 합니다.  
  
 `_wrmdir`는 `_rmdir`의 와이드 문자 버전이며, `_wrmdir`의 `dirname` 인수는 와이드 문자 문자열입니다.  `_wrmdir` 및 `_rmdir` 는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_trmdir`|`_rmdir`|`_rmdir`|`_wrmdir`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_rmdir`|\<direct.h\>|  
|`_wrmdir`|\<direct.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
 [\_mkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::IO::Directory::Delete](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)  
  
## 참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)