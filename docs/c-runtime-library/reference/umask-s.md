---
title: _umask_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _umask_s
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
- unmask_s
- _umask_s
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
caps.latest.revision: 17
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 5c8efcdf5d3f44a6cd3bbcc39f2a98e3659c95ab
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="umasks"></a>_umask_s
기본 파일 사용 권한 마스크를 설정합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_umask](../../c-runtime-library/reference/umask.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _umask_s(  
   int mode,  
   int * pOldMode  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `mode`  
 기본 사용 권한 설정입니다.  
  
 [out] `oldMode`  
 사용 권한 설정의 이전 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `Mode`가 유효한 모드를 지정하지 않거나 `pOldMode` 포인터가 `NULL`이면 오류 코드를 반환합니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`mode`|`pOldMode`|**반환 값**|****`oldMode`의 내용|  
|------------|----------------|----------------------|--------------------------------|  
|모두|`NULL`|`EINVAL`|수정 안 됨|  
|잘못된 모드|모두|`EINVAL`|수정 안 됨|  
  
 위의 오류 조건 중 하나가 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 `_umask_s`는 `EINVAL`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `_umask_s` 함수에서 지정 된 모드를 현재 프로세스의 파일 권한 마스크 설정 `mode`합니다. 파일 사용 권한 마스크는 `_creat`, `_open` 또는 `_sopen`에서 생성한 새 파일의 사용 권한 설정을 수정합니다. 마스크의 비트가 1이면 파일의 요청된 사용 권한 값에서 해당하는 비트가 0(허용되지 않음)으로 설정됩니다. 마스크의 비트가 0이면 해당하는 비트는 변경되지 않고 그대로 유지됩니다. 새 파일에 대한 사용 권한 설정은 파일을 처음으로 닫을 때까지 설정되지 않습니다.  
  
 정수 식 `pmode`에는 SYS\STAT.H에 정의된 다음 매니페스트 상수 중 하나 또는 둘 다가 포함되어 있습니다.  
  
 `_S_IWRITE`  
 쓰기를 허용합니다.  
  
 `_S_IREAD`  
 읽기를 허용합니다.  
  
 `_S_IREAD | _S_IWRITE`  
 읽기 및 쓰기를 허용합니다.  
  
 두 상수가 지정된 경우 비트 OR 연산자(`|`)를 사용하여 결합합니다. `mode` 인수가 `_S_IREAD`이면 읽기는 허용되지 않으며 파일은 쓰기 전용으로 설정됩니다. `mode` 인수가 `_S_IWRITE`이면 쓰기는 허용되지 않으며 파일은 읽기 전용으로 설정됩니다. 예를 들어 마스크에 쓰기 비트가 설정되어 있으면 모든 새 파일은 읽기 전용이 됩니다. MS-DOS 및 Windows 운영 체제에서는 모든 파일을 읽을 수는 있지만 쓰기 전용 권한을 부여할 수는 없습니다. 따라서 `_umask_s`를 사용하여 읽기 비트를 설정해도 파일 모드에는 아무런 변화가 없습니다.  
  
 `pmode`가 매니페스트 상수 중 하나의 조합이 아니거나 다른 상수 집합을 통합하는 경우 함수는 이러한 항목을 무시합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_umask_s`|\<io.h>, \<sys/stat.h> 및 \<sys/types.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_umask_s.c  
/* This program uses _umask_s to set  
 * the file-permission mask so that all future  
 * files will be created as read-only files.  
 * It also displays the old mask.  
 */  
  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask, err;  
  
   /* Create read-only files: */  
   err = _umask_s( _S_IWRITE, &oldmask );  
   if (err)  
   {  
      printf("Error setting the umask.\n");  
      exit(1);  
   }  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
```Output  
Oldmask = 0x0000  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)
