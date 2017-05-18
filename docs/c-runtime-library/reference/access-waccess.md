---
title: "_access, _waccess | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _access
- _waccess
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _waccess
- _access
- taccess
- waccess
- _taccess
dev_langs:
- C++
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: d0968ec14a43cfbbf1169f34ac929435787bc349
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="access-waccess"></a>_access, _waccess
파일이 읽기 전용인지 아닌지를 확인합니다. 더 안전한 버전을 사용할 수 있습니다. [_access_s, _waccess_s](../../c-runtime-library/reference/access-s-waccess-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `path`  
 파일 또는 디렉터리 경로입니다.  
  
 `mode`  
 읽기/쓰기 특성입니다.  
  
## <a name="return-value"></a>반환 값  
 파일에 지정된 모드가 있으면 각 함수는 0을 반환합니다. 명명 된 파일은 존재 하지 않거나 지정 된 모드;에 없는 경우-1을 반환 하는 함수 이 경우 `errno` 다음 표와 같이 설정 됩니다.  
  
 `EACCES`  
 액세스 거부됨: 파일의 권한 설정이 지정된 액세스를 허용하지 않습니다.  
  
 `ENOENT`  
 파일 이름 또는 경로를 찾을 수 없습니다.  
  
 `EINVAL`  
 잘못된 매개 변수입니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 파일과 함께 사용할 경우 `_access` 함수는 지정된 파일 또는 디렉터리가 존재하는지 또는 `mode`의 값으로 지정한 특성을 가지고 있는지를 확인합니다. 디렉터리와 함께 사용할 경우 `_access`는 지정된 디렉터리가 있는지만 확인합니다. [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] 이상의 운영 체제에서는 모든 디렉터리에 읽기 및 쓰기 권한이 있습니다.  
  
|`mode` 값|파일 검사|  
|------------------|---------------------|  
|00|존재만|  
|02|쓰기 전용|  
|04|읽기 전용|  
|06|읽기 및 쓰기|  
  
 이 함수는 파일과 디렉터리가 읽기 전용인지 아닌지만 확인하고, 파일 시스템 보안 설정은 확인하지 않습니다. 이를 확인하려면 액세스 토큰이 필요합니다. 파일 시스템 보안에 대한 자세한 내용은 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909)을 참조하세요. 이 기능을 제공하기 위해 ATL 클래스가 존재합니다. [CAccessToken 클래스](../../atl/reference/caccesstoken-class.md)를 참조하세요.  
  
 `_waccess`은 `_access`의 와이드 문자 버전이며, `path`에 대한 `_waccess` 인수는 와이드 문자열입니다. 그렇지 않으면 `_waccess`과 `_access`이 동일하게 작동합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `path`가 `NULL`이거나 `mode`가 유효한 모드를 지정하지 않으면, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 함수가 `errno`를 `EINVAL`로 설정하고 -1을 반환합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_taccess`|`_access`|`_access`|`_waccess`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|----------------------|  
|`_access`|\<io.h>|\<errno.h>|  
|`_waccess`|\<wchar.h> 또는 \<io.h>|\<errno.h>|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `_access`를 사용하여 crt_ACCESS.C라는 파일이 있는지, 쓰기가 허용되는지를 확인합니다.  
  
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
  
```Output  
File crt_ACCESS.C exists.  
File crt_ACCESS.C does not have write permission.  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat, _wstat 함수](../../c-runtime-library/reference/stat-functions.md)
