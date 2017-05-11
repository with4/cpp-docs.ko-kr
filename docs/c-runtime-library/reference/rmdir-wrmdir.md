---
title: _rmdir, _wrmdir | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wrmdir
- _rmdir
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
- trmdir
- _trmdir
- wrmdir
- _rmdir
- _wrmdir
dev_langs:
- C++
helpviewer_keywords:
- _rmdir function
- directories [C++], deleting
- rmdir function
- directories [C++], removing
- trmdir function
- _trmdir function
- _wrmdir function
- wrmdir function
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
caps.latest.revision: 11
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
ms.openlocfilehash: 04b563468b9bc79ccd92d608dfeb4e7a3b85120a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="rmdir-wrmdir"></a>_rmdir, _wrmdir
디렉터리를 삭제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      int _rmdir(  
   const char *dirname   
);  
int _wrmdir(  
   const wchar_t *dirname   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dirname`  
 제거할 디렉터리의 경로입니다.  
  
## <a name="return-value"></a>반환 값  
 디렉터리가 정상적으로 삭제되면 이러한 각 함수는 0을 반환합니다. 반환 값이-1은 오류를 나타냅니다. 및 `errno` 다음 값 중 하나로 설정 됩니다.  
  
 **ENOTEMPTY**  
 지정된 경로가 디렉터리가 아니거나, 디렉터리가 비어 있지 않거나, 디렉터리가 현재 작업 디렉터리 또는 루트 디렉터리입니다.  
  
 `ENOENT`  
 경로가 잘못되었습니다.  
  
 **EACCES**  
 프로그램에 디렉터리에 대한 열린 핸들이 있습니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_rmdir` 함수는 `dirname`으로 지정된 디렉터리를 삭제합니다. 디렉터리는 비어 있어야 하고, 현재 작업 디렉터리나 루트 디렉터리가 아니어야 합니다.  
  
 `_wrmdir`은 `_rmdir`의 와이드 문자 버전이며, `dirname`에 대한 `_wrmdir` 인수는 와이드 문자열입니다. 그렇지 않으면 `_wrmdir`과 `_rmdir`이 동일하게 작동합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_trmdir`|`_rmdir`|`_rmdir`|`_wrmdir`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_rmdir`|\<direct.h>|  
|`_wrmdir`|\<direct.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
 [_mkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)
