---
title: "_access_s, _waccess_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_access_s"
  - "_waccess_s"
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
  - "waccess_s"
  - "access_s"
  - "_waccess_s"
  - "_access_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_access_s 함수"
  - "_taccess_s 함수"
  - "_waccess_s 함수"
  - "access_s 함수"
  - "taccess_s 함수"
  - "waccess_s 함수"
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# _access_s, _waccess_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 읽기\/쓰기 사용 권한을 결정합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 에 설명된 대로 이 버전은 보안 향상 기능이 포함된 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md) 버전입니다.  
  
## 구문  
  
```  
errno_t _access_s(   
   const char *path,   
   int mode   
);  
errno_t _waccess_s(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### 매개 변수  
 `path`  
 파일 또는 디렉터리 경로입니다.  
  
 `mode`  
 권한 설정  
  
## 반환 값  
 각 함수는 파일에 지정 된 모드 0을 반환 합니다.  명명된 된 파일이 존재 하지 않거나 지정한 모드에 액세스할 수 없는 경우 오류 코드를 반환 합니다.  이 경우 함수 집합에서 다음과 같은 오류 코드를 반환하고 설정한 `errno` 같은 값입니다.  
  
 `EACCES`  
 액세스가 거부되었습니다.  파일의 권한 설정이 지정된 액세스를 허용하지 않습니다.  
  
 `ENOENT`  
 파일 이름 또는 경로를 찾을 수 없습니다.  
  
 `EINVAL`  
 잘못된 매개 변수입니다.  
  
 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 파일을 사용 하는 경우는, `_access_s` 함수는 지정한 파일이 있으면 액세스할 수 있는지 여부를 결정하고 이는 값으로 지정 된 `mode` 에 접근합니다.  디렉터리와 함께 사용할 경우, `_access_s` 는 지정한 디렉터리가 있는지 여부만 확인 합니다.  [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] 및 뒤 이은 운영 체제에서 , 모든 디렉터리는 읽기 및 쓰기에 접근합니다.  
  
|모드 값|파일 검사|  
|----------|-----------|  
|00|존재 합니다.|  
|02|쓰기 권한입니다.|  
|04|읽기 권한입니다.|  
|06|읽기 및 쓰기 권한입니다.|  
  
 읽거나 파일에 쓸 수 있는 권한이 있는 파일을 열기에는 충분하지 않습니다.  예를 들어, 파일이 다른 프로세스에 의해 잠겨 있으면, 액세스할 수 없습니다 `_access_s` 0을 반환 합니다.  
  
 `_waccess_s`는 `_access_s`의 와이드 문자 버전이며, `_waccess_s`의 `path` 인수는 와이드 문자 문자열입니다.  그렇지 않으면 `_waccess_s`과 `_access_s`은 동일하게 작동합니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  만일 `path` 는 `NULL` 또는 `mode` 인 경우, 유효한 모드를 지정하지 않습니다, 잘못된 매개변수 처리기는 호출됩니다. 이는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 설명됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `EINVAL`을 반환합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_taccess_s`|`_access_s`|`_access_s`|`_waccess_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_access_s`|\<io.h\>|\<\<errno.h\>\>|  
|`_waccess_s`|\<whcar.h\> 또는 \<io.h\>|\<\<errno.h\>\>|  
  
## 예제  
 이 예제에서는 `_access_s` 를 존재 여부와 쓰기 허용 되는지 여부를 확인 하기 위해  crt\_access\_s.c 라는 파일을 체크 합니다.  
  
```  
// crt_access_s.c  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    errno_t err = 0;  
  
    // Check for existence.   
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )  
    {  
        printf_s( "File crt_access_s.c exists.\n" );  
  
        // Check for write permission.   
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )  
        {  
            printf_s( "File crt_access_s.c does have "  
                      "write permission.\n" );  
        }  
        else  
        {  
            printf_s( "File crt_access_s.c does not have "  
                      "write permission.\n" );  
        }  
    }  
    else  
    {  
        printf_s( "File crt_access_s.c does not exist.\n" );  
    }  
}  
```  
  
  **Crt\_access\_s.c 파일에 있습니다.**  
**Crt\_access\_s.c 파일에 쓰기 권한이 없습니다.**   
## 해당 .NET Framework 항목  
 <xref:System.IO.FileAccess?displayProperty=fullName>  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat, \_wstat 함수](../../c-runtime-library/reference/stat-functions.md)