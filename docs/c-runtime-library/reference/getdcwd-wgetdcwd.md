---
title: "_getdcwd, _wgetdcwd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getdcwd"
  - "_wgetdcwd"
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
  - "wgetdcwd"
  - "getdcwd"
  - "_getdcwd"
  - "tgetdcwd"
  - "_wgetdcwd"
  - "_tgetdcwd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wgetdcwd 함수"
  - "디렉터리 작업"
  - "getdcwd 함수"
  - "_getdcwd 함수"
  - "_wgetdcwd 함수"
  - "현재 작업 디렉터리"
  - "디렉터리 [c + +] 현재 작업"
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _getdcwd, _wgetdcwd
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정한 드라이브의 현재 작업 디렉터리의 전체 경로를 가져옵니다.  
  
## 구문  
  
```  
char *_getdcwd(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### 매개 변수  
 `drive`  
 드라이브를 지정하는 음수가 아닌 정수입니다\(0 \= 기본 드라이브, 1 \= A, 2 \= B 등\).  
  
 지정된 드라이브를 사용할 수 없는 경우 또는 드라이브 유형\(예: 이동식, 고정, CD\-ROM, RAM 디스크 또는 네트워크 드라이브\)을 확인할 수 없는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  
  
 `buffer`  
 경로 대 한 저장소 위치 또는 **NULL**합니다.  
  
 경우 **NULL** 지정,이 함수는 버퍼의를 적어도 할당 `maxlen` 크기를 사용 하 여 **malloc**, 및의 반환 값 `_getdcwd` 할당된 된 버퍼에 대 한 포인터입니다.`free`를 호출하고 포인터에 전달하여 버퍼를 해제할 수 있습니다.  
  
 `maxlen`  
 경로의 최대 길이를 지정하는 0이 아닌 양의 정수: `char`에 대한 `_getdcwd` 및 `wchar_t`에 대한 `_wgetdcwd`  
  
 `maxlen`이 0보다 크지 않는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  
  
## 반환 값  
 지정된 드라이브의 현재 작업 디렉터리의 전체 경로를 나타내는 문자열에 대한 포인터 또는 오류를 나타내는 `NULL`입니다.  
  
 `buffer`가 `NULL`로 지정되고 `maxlen` 문자를 할당할 메모리가 부족한 경우 오류가 발생하고 `errno`가 `ENOMEM`으로 설정됩니다. null 종결 문자를 포함하는 경로의 길이가 `maxlen`을 초과하는 경우 오류가 발생하고 `errno`가 `ERANGE`로 설정됩니다. 이러한 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 `_getdcwd` 함수는 지정된 드라이브에 있는 현재 작업 디렉터리의 전체 경로를 가져오고 `buffer`에 저장합니다. 현재 작업 디렉터리가 루트로 설정되는 경우 문자열이 백슬래시\(\\\)로 끝납니다. 현재 작업 디렉터리가 루트 이외의 디렉터리로 설정되는 경우 문자열은 백슬래시가 아닌 디렉터리의 이름으로 끝납니다.  
  
 `_wgetdcwd`가 `_getdcwd`의 와이드 문자 버전이고 해당 `buffer` 매개 변수 및 반환 값이 와이드 문자열입니다. 그렇지 않으면 `_wgetdcwd`과 `_getdcwd`은 동일하게 작동합니다.  
  
 의존 하는 경우에이 함수는 스레드로부터 안전 **GetFullPathName**, 스레드로부터 안전 하지 자체입니다. 그러나 다중 스레드 응용 프로그램 모두이 함수를 호출 하는 경우 스레드 안전성을 위반할 수 및 **GetFullPathName**합니다. 자세한 내용은 [MSDN Library](http://go.microsoft.com/fwlink/?LinkID=150542) 검색 한 다음 **GetFullPathName**합니다.  
  
 `_nolock` 접미사가 있는 이 함수의 버전은 이 함수와 동일하게 작동합니다. 단, 스레드로부터 안전하지 않고 다른 스레드의 간섭으로부터 보호받지 않습니다. 자세한 내용은 [\_getdcwd\_nolock, \_wgetdcwd\_nolock](../../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md)을 참조하세요.  
  
 `_DEBUG` 및 `_CRTDBG_MAP_ALLOC`이 정의될 때 `_getdcwd` 및 `_wgetdcwd`에 대한 호출이 `_getdcwd_dbg` 및 `_wgetdcwd_dbg`에 대한 호출에 의해 대체되므로 메모리 할당을 디버그할 수 있습니다. 자세한 내용은 [\_getdcwd\_dbg, \_wgetdcwd\_dbg](../../c-runtime-library/reference/getdcwd-dbg-wgetdcwd-dbg.md)를 참조하세요.  
  
### 제네릭 텍스트 루틴 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tgetdcwd`|`_getdcwd`|`_getdcwd`|`_wgetdcwd`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_getdcwd`|\<direct.h\>|  
|`_wgetdcwd`|\<direct.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)의 예제를 참조하세요.  
  
## 해당 .NET Framework 항목  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## 참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)