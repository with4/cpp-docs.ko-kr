---
title: "_access, _waccess | Microsoft Docs"
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
  - "_access"
  - "_waccess"
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
  - "_waccess"
  - "_access"
  - "taccess"
  - "waccess"
  - "_taccess"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_access 함수"
  - "_taccess 함수"
  - "_waccess 함수"
  - "access 함수"
  - "taccess 함수"
  - "waccess 함수"
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
caps.latest.revision: 27
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _access, _waccess
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일이 읽기 전용인지 여부를 결정합니다.  더 안전한 버전을 사용할 수 있습니다. [\_access\_s, \_waccess\_s](../../c-runtime-library/reference/access-s-waccess-s.md) 를 참조하세요.  
  
## 구문  
  
```  
int _access(   
   const char *path,   
   int mode   
);  
int _waccess(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### 매개 변수  
 `path`  
 파일 또는 디렉터리 경로입니다.  
  
 `mode`  
 읽기\/쓰기 속성입니다.  
  
## 반환 값  
 각 함수는 파일에 지정 된 모드 0을 반환 합니다.  만일 이 이름을 가진 파일이 존재하지 않거나 주어진 모드에 없다면, 함수는 \-1을 반환합니다; 이경우, `errno` 는 다음 표에 나타나는 것 처럼 설정됩니다.  
  
 `EACCES`  
 액세스가 거부 되었습니다: 파일의 권한 설정이 지정된 액세스를 허용 하지 않습니다.  
  
 `ENOENT`  
 파일 이름 또는 경로를 찾을 수 없습니다.  
  
 `EINVAL`  
 잘못된 매개 변수입니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 파일을 사용할 때, `_access` 함수는 지정된 파일 또는 디렉터리가 존재하고 `mode` 의 값에 의해 지정된 특성이 있는지 여부를 확인합니다.  디렉터리와 함께 사용할 때, `_access` 는 오직 지정된 디렉터리가 존재하는지 여부만을 확인합니다; [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] 에서 그리고 이후의 운영체제에서, 모든 디렉터리는 읽기와 쓰기 액세스를 갖습니다.  
  
|`mode` 값|파일 검사|  
|--------------|-----------|  
|00|존재 합니다.|  
|02|쓰기 전용|  
|04|읽기 전용|  
|06|읽기와 쓰기|  
  
 이 함수는 오직 파일과 디렉터리의 읽기 전용또는 그외의 여부를 확인하고, 파일시스템 보안 설정은 확인하지 않습니다.  액세스 토큰이 필요합니다.  파일 시스템 보안에 대한 자세한 내용은, [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909)을 참고하세요.  이 기능을 제공하기 위해 ATL 클래스가 존재합니다; [CAccessToken Class](../../atl/reference/caccesstoken-class.md)을 참고하세요.  
  
 `_waccess`는 `_access`의 와이드 문자 버전이며, `_waccess`의 `path` 인수는 와이드 문자 문자열입니다.  `_waccess` 및 `_access` 는 동일하게 작동합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  만일 `path` 는 `NULL` 또는 `mode` 인 경우, 유효한 모드를 지정하지 않습니다, 잘못된 매개변수 처리기는 호출됩니다. 이는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 설명됩니다.  만약 계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 로 설정하고 \-1을 반환합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_taccess`|`_access`|`_access`|`_waccess`|  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_access`|\<io.h\>|\<\<errno.h\>\>|  
|`_waccess`|\<whcar.h\> 또는 \<io.h\>|\<\<errno.h\>\>|  
  
## 예제  
 다음 예제는 존재하는지의 여부와 쓰기가 허락되는지 여부를 위해 crt\_ACCESS.C로 명명된 파일을 확인하는데 `_access` 를 사용합니다.  
  
```  
// crt_access.c  
// compile with: /W1  
// This example uses _access to check the file named  
// crt_ACCESS.C to see if it exists and if writing is allowed.  
  
#include  <io.h>  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    // Check for existence.  
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )  
    {  
        printf_s( "File crt_ACCESS.C exists.\n" );  
  
        // Check for write permission.  
        // Assume file is read-only.  
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )  
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );  
    }  
}  
```  
  
  **crt\_ACCESS.C 파일에 있습니다.**  
**crt\_ACCESS.C 파일에 쓰기 권한이 없습니다.**   
## 해당 .NET Framework 항목  
 <xref:System.IO.FileAccess?displayProperty=fullName>  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat, \_wstat 함수](../../c-runtime-library/reference/stat-functions.md)