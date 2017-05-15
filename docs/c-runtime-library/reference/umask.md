---
title: _umask | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _umask
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
- _umask
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: 21
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
ms.openlocfilehash: f2ad9c75caa5f3816ab4791dc4e67cb7937bfad4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="umask"></a>_umask
기본 파일 사용 권한 마스크를 설정합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_umask_s](../../c-runtime-library/reference/umask-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pmode`  
 기본 사용 권한 설정입니다.  
  
## <a name="return-value"></a>반환 값  
 `_umask`는 `pmode`의 이전 값을 반환합니다. 반환되는 오류가 없습니다.  
  
## <a name="remarks"></a>설명  
 `_umask` 함수에서 지정 된 모드를 현재 프로세스의 파일 권한 마스크 설정 `pmode`합니다. 파일 사용 권한 마스크는 `_creat`, `_open` 또는 `_sopen`에서 생성한 새 파일의 사용 권한 설정을 수정합니다. 마스크의 비트가 1이면 파일의 요청된 사용 권한 값에서 해당하는 비트가 0(허용되지 않음)으로 설정됩니다. 마스크의 비트가 0이면 해당하는 비트는 변경되지 않고 그대로 유지됩니다. 새 파일에 대한 사용 권한 설정은 파일을 처음으로 닫을 때까지 설정되지 않습니다.  
  
 정수 식 `pmode`에는 SYS\STAT.H에 정의된 다음 매니페스트 상수 중 하나 또는 둘 다가 포함되어 있습니다.  
  
 `_S_IWRITE`  
 쓰기를 허용합니다.  
  
 `_S_IREAD`  
 읽기를 허용합니다.  
  
 `_S_IREAD | _S_IWRITE`  
 읽기 및 쓰기를 허용합니다.  
  
 두 상수가 지정된 경우 비트 OR 연산자(`|`)를 사용하여 결합합니다. `pmode` 인수가 `_S_IREAD`이면 읽기는 허용되지 않으며 파일은 쓰기 전용으로 설정됩니다. `pmode` 인수가 `_S_IWRITE`이면 쓰기는 허용되지 않으며 파일은 읽기 전용으로 설정됩니다. 예를 들어 마스크에 쓰기 비트가 설정되어 있으면 모든 새 파일은 읽기 전용이 됩니다. MS-DOS 및 Windows 운영 체제에서는 모든 파일을 읽을 수는 있지만 쓰기 전용 권한을 부여할 수는 없습니다. 따라서 `_umask`를 사용하여 읽기 비트를 설정해도 파일 모드에는 아무런 변화가 없습니다.  
  
 `pmode`가 매니페스트 상수 중 하나의 조합이 아니거나 다른 상수 집합을 통합하는 경우 함수는 이러한 항목을 무시합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_umask`|\<io.h>, \<sys/stat.h>, \<sys/types.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_umask.c  
// compile with: /W3  
// This program uses _umask to set  
// the file-permission mask so that all future  
// files will be created as read-only files.  
// It also displays the old mask.  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask;  
  
   /* Create read-only files: */  
   oldmask = _umask( _S_IWRITE ); // C4996  
   // Note: _umask is deprecated; consider using _umask_s instead  
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
