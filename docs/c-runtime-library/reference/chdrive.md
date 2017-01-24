---
title: "_chdrive | Microsoft Docs"
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
  - "_chdrive"
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
  - "chdrive"
  - "_chdrive"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_chdrive 함수"
  - "chdrive 함수"
  - "드라이브, 변경"
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _chdrive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 드라이브를 변경합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _chdrive(   
   int drive   
);  
```  
  
#### 매개 변수  
 `drive`  
 현재 작업을 지정 하는 1부터 26 까지의 정수 \(1 \= A, B \= 2, 등\) 드라이브.  
  
## 반환 값  
 영 \(0\) 현재 작업 드라이브 변경된 경우입니다; 그렇지 않으면\-1입니다.  
  
## 설명  
 `drive` 는 1부터 26 까지의 범위에서 벗어난 호출일 경우, 잘못된 매개변수 처리기는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명되어 호출됩니다.  계속해서 실행하도록 허용된 경우, **\_chdrive** 함수는 \-1을 반환합니다, `errno` 는 `EACCES`을 설정하고, `_doserrno` 는 `ERROR_INVALID_DRIVE` 설정합니다.  
  
 **\_chdrive** 함수는 스레드로부터 안전합니다. 왜냐하면 **SetCurrentDirectory** 함수 자체가 스레드로부터 안전 하지 않은 함수에 의존하고 있기 때문입니다.  **\_chdrive** 을 안전하게 다중 스레드 응용 프로그램에서 사용하기 위해, 자신의 스레드 동기화를 제공해야만 합니다.  자세한 내용은 [MSDN Library](http://go.microsoft.com/fwlink/?LinkID=150542) 를 참조하십시오. **SetCurrentDirectory**  
  
 **\_chdrive** 함수는 작업 드라이브만 변경합니다;  **\_chdir** 현재 작업 디렉터리를 변경합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|**\_chdrive**|\<direct.h\>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## 참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)