---
title: "_getdcwd_nolock, _wgetdcwd_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wgetdcwd_nolock"
  - "_getdcwd_nolock"
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
apitype: "DLLExport"
f1_keywords: 
  - "_wgetdcwd_nolock"
  - "tgetdcwd_nolock"
  - "wgetdcwd_nolock"
  - "_getdcwd_nolock"
  - "_tgetdcwd_nolock"
  - "getdcwd_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_getdcwd_nolock 함수"
  - "_tgetdcwd_nolock 함수"
  - "_wgetdcwd_nolock 함수"
  - "현재 작업 디렉터리"
  - "디렉터리[C++], 현재 작업"
  - "getdcwd_nolock 함수"
  - "tgetdcwd_nolock 함수"
  - "wgetdcwd_nolock 함수"
  - "디렉터리 작업"
ms.assetid: d9bdf712-43f8-4173-8f9a-844e82beaa97
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _getdcwd_nolock, _wgetdcwd_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정한 드라이브의 현재 작업 디렉터리의 전체 경로를 가져옵니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *_getdcwd_nolock(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd_nolock(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### 매개 변수  
 `drive`  
 디스크 드라이브  
  
 `buffer`  
 경로에 대한 저장소 위치입니다.  
  
 `maxlen`  
 문자가 경로의 최대 길이: `_getdcwd` 에 대한 `char` 및 `_wgetdcwd`에 대한 `wchar_t` .  
  
## 반환 값  
 [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)를 참조하십시오.  
  
## 설명  
 `_getdcwd_nolock` 과 `_wgetdcwd_nolock` 는 각 다른 스레드의 간섭으로 부터 보호되지 않은 `_getdcwd` 과 `_wgetdcwd` 을 제외하는 것이 동일합니다.  이들은 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다.  단일 스레드 응용 프로그램과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tgetdcwd_nolock`|`_getdcwd_nolock`|`_getdcwd_nolock`|`_wgetdcwd_nolock`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_getdcwd_nolock`|\<direct.h\>|  
|`_wgetdcwd_nolock`|\<direct.h\> 또는 \<wchar.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## 참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)