---
title: "errno, _doserrno, _sys_errlist 및 _sys_nerr | Microsoft Docs"
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
  - "_errno"
apilocation: 
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_sys_errlist"
  - "errno"
  - "_sys_nerr"
  - "_doserrno"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_doserrno 전역 변수"
  - "_sys_errlist 전역 변수"
  - "_sys_nerr 전역 변수"
  - "doserrno 전역 변수"
  - "errno 전역 변수"
  - "오류 코드, 인쇄"
  - "sys_errlist 전역 변수"
  - "sys_nerr 전역 변수"
ms.assetid: adbec641-6d91-4e19-8398-9a34046bd369
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# errno, _doserrno, _sys_errlist 및 _sys_nerr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로그램을 실행하는 동안 설정된 오류 코드를 보유한 전역 매크로와 표시용 오류 코드의 문자열에 해당하는 값입니다.  
  
## 구문  
  
```  
#define errno   (*_errno()) #define _doserrno   (*__doserrno()) #define _sys_errlist (__sys_errlist()) #define _sys_nerr (*__sys_nerr())  
```  
  
## 설명  
 `errno`와 `_doserrno`는 모두 프로그램을 시작하는 동안 런타임에 0으로 설정됩니다.  `errno`는 오류가 발생한 시스템 수준 호출에서 설정됩니다.  `errno`에 설정된 마지막 호출에 대한 값이 있으므로 이후 호출에 의해 이 값이 변경될 수도 있습니다.  오류에 대해 `errno`를 설정하는 런타임 라이브러리 호출은 성공 시 `errno`를 지우지 않습니다.  설정할 수 있는 호출 바로 전에 `_set_errno(0)`를 호출하여 항상 `errno`를 지우고 호출 후 바로 확인하세요.  
  
 오류 발생 시 `errno`를 시스템 호출에서 반환된 오류 코드와 동일한 값으로 설정할 필요가 없습니다.  I\/O 작업의 경우 `_doserrno`는 `errno` 코드에 대등한 운영 체제 오류 코드를 저장합니다.  대부분의 비I\/O 작업의 경우 `_doserrno` 값이 설정되지 않습니다.  
  
 각 `errno` 값은 [perror](../c-runtime-library/reference/perror-wperror.md) 함수 중 하나를 사용하여 인쇄하거나 [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) 또는 [strerror\_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) 함수 중 하나를 사용하여 문자열에 저장할 수 있는 `_sys_errlist`의 오류 메시지와 연결되어 있습니다.  `perror` 및 `strerror` 함수에서 `_sys_errlist` 배열 및 `_sys_nerr`\(`_sys_errlist`에서 요소 수\)을 사용하여 오류 정보를 처리합니다.  `_sys_errlist` 및 `_sys_nerr`에 대한 직접 액세스는 코드 보안상의 이유로 사용되지 않습니다.  다음과 같이 전역 매크로 대신 더욱 안전한 기능 버전을 사용하는 것이 좋습니다.  
  
|전역 매크로|해당 기능|  
|------------|-----------|  
|`_doserrno`|[\_get\_doserrno](../c-runtime-library/reference/get-doserrno.md), [\_set\_doserrno](../c-runtime-library/reference/set-doserrno.md)|  
|`errno`|[\_get\_errno](../c-runtime-library/reference/get-errno.md), [\_set\_errno](../c-runtime-library/reference/set-errno.md)|  
|`_sys_errlist`, `_sys_nerr`|[strerror\_s, \_strerror\_s, \_wcserror\_s, \_\_wcserror\_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|  
  
 라이브러리 수학 루틴이 [\_matherr](../c-runtime-library/reference/matherr.md)을 호출하여 `errno`를 설정합니다.  수학 오류를 다르게 처리하려면 `_matherr` 참조 설명에 따라 고유한 루틴을 작성하고 이름을 `_matherr`로 지정합니다.  
  
 다음 표에 있는 모든 `errno` 값은 \<errno.h\>에서 미리 정의된 상수이며 UNIX와 호환됩니다.  `ERANGE`, `EILSEQ` 및 `EDOM`만 ISO C99 표준에 지정되어 있습니다.  
  
|상수|시스템 오류 메시지|값|  
|--------|----------------|-------|  
|`EPERM`|작업이 허용되지 않음|1|  
|`ENOENT`|해당 파일 또는 디렉터리 없음|2|  
|`ESRCH`|해당 프로세스 없음|3|  
|`EINTR`|중단된 함수|4|  
|`EIO`|I\/O 오류|5|  
|`ENXIO`|해당 장치 또는 주소 없음|6|  
|`E2BIG`|인수 목록이 너무 김|7|  
|`ENOEXEC`|실행 형식 오류|8|  
|`EBADF`|잘못된 파일 번호|9|  
|`ECHILD`|생성된 프로세스 없음|10|  
|`EAGAIN`|추가 프로세스가 없거나 메모리가 부족하거나 최대 중첩 수주에 도달함|11|  
|`ENOMEM`|메모리 부족|12|  
|`EACCES`|사용 권한이 거부됨|13|  
|`EFAULT`|잘못된 주소|14|  
|`EBUSY`|장치 또는 리소스 사용 중|16|  
|`EEXIST`|파일이 있음|17|  
|`EXDEV`|장치 간 연결|18|  
|`ENODEV`|해당 장치 없음|19|  
|`ENOTDIR`|디렉터리가 아님|20|  
|`EISDIR`|디렉터리임|21|  
|`EINVAL`|잘못된 인수|22|  
|`ENFILE`|시스템에 너무 많은 파일이 열려 있음|23|  
|`EMFILE`|열려 있는 파일이 너무 많음|24|  
|`ENOTTY`|부적절한 I\/O 제어 작업|25|  
|`EFBIG`|파일이 너무 큼|27|  
|`ENOSPC`|장치에 남은 공간이 없음|28|  
|`ESPIPE`|잘못된 검색|29|  
|`EROFS`|읽기 전용 파일 시스템|30|  
|`EMLINK`|링크가 너무 많음|31|  
|`EPIPE`|파이프가 끊어짐|32|  
|`EDOM`|산술 인수|33|  
|`ERANGE`|결과가 너무 큼|34|  
|`EDEADLK`|리소스 교착 상태가 발생함|36|  
|`EDEADLOCK`|이전 Microsoft C 버전과의 호환성을 위해 EDEADLK와 동일|36|  
|`ENAMETOOLONG`|파일 이름이 너무 김|38|  
|`ENOLCK`|잠금을 사용할 수 없음|39|  
|`ENOSYS`|함수가 지원되지 않음|40|  
|`ENOTEMPTY`|디렉터리가 비어 있음|41|  
|`EILSEQ`|바이트 시퀀스가 잘못됨|42|  
|`STRUNCATE`|문자열이 잘림|80|  
  
## 요구 사항  
  
|전역 매크로|필수 헤더|선택적 헤더|  
|------------|-----------|------------|  
|`errno`|\<errno.h\> 또는 \<stdlib.h\>, \<cerrno\> 또는 \<cstdlib\>\(C\+\+\)||  
|`_doserrno`, `_sys_errlist`, `_sys_nerr`|\<stdlib.h\>, \<cstdlib\>\(C\+\+\)|\<errno.h\>, \<cerrno\>\(C\+\+\)|  
  
 `_doserrno`, `_sys_errlist` 및 `_sys_nerr` 매크로는 Microsoft 확장입니다.  호환성에 대한 자세한 내용은 [호환성](../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 참고 항목  
 [전역 변수](../c-runtime-library/global-variables.md)   
 [errno 상수](../c-runtime-library/errno-constants.md)   
 [perror, \_wperror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror, \_strerror, \_wcserror, \_\_wcserror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [strerror\_s, \_strerror\_s, \_wcserror\_s, \_\_wcserror\_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)   
 [\_get\_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [\_set\_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [\_get\_errno](../c-runtime-library/reference/get-errno.md)   
 [\_set\_errno](../c-runtime-library/reference/set-errno.md)