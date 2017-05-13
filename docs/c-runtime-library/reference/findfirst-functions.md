---
title: "_findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _findfirst
- _wfindfirst
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
- findfirst32i64
- wfindfirst32i64
- tfindfirst64
- _findfirst64i32
- _wfindfirst32i64
- _wfindfirsti64
- wfindfirst
- _tfindfirsti64
- findfirst32
- _tfindfirst32
- _findfirsti64
- findfirst
- wfindfirst64
- wfindfirst32
- tfindfirst32
- _wfindfirst64i32
- findfirst64i32
- tfindfirst64i32
- _wfindfirst
- findfirsti64
- _findfirst32i64
- wfindfirst64i32
- _wfindfirst32
- _findfirst32
- _tfindfirst32i64
- tfindfirst
- _tfindfirst64i32
- findfirst64
- _tfindfirst
- _findfirst64
- _tfindfirst64
- tfindfirst32i64
- _findfirst
- _wfindfirst64
dev_langs:
- C++
helpviewer_keywords:
- _tfindfirst64 function
- _wfindfirst64i32 function
- _wfindfirst32i64 function
- wfindfirst32 function
- _findfirst function
- wfindfirst64 function
- _wfindfirst function
- _findfirst64i32 function
- wfindfirst function
- _findfirst64 function
- tfindfirst32 function
- _tfindfirst64i32 function
- findfirst function
- findfirst32i64 function
- tfindfirst64 function
- _tfindfirst32 function
- tfindfirst32i64 function
- tfindfirst64i32 function
- _wfindfirsti64 function
- _findfirst32i64 function
- findfirst32 function
- findfirsti64 function
- findfirst64i32 function
- tfindfirsti64 function
- tfindfirst function
- _wfindfirst32 function
- wfindfirsti64 function
- _tfindfirsti64 function
- _tfindfirst function
- _tfindfirst32i64 function
- findfirst64 function
- _findfirst32 function
- _findfirsti64 function
- wfindfirst32i64 function
- wfindfirst64i32 function
- _wfindfirst64 function
ms.assetid: 9bb46d1a-b946-47de-845a-a0b109a33ead
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: baf853db4fe1a23ee726423a052604a0db8764c9
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="findfirst-findfirst32-findfirst32i64-findfirst64-findfirst64i32-findfirsti64-wfindfirst-wfindfirst32-wfindfirst32i64-wfindfirst64-wfindfirst64i32-wfindfirsti64"></a>_findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64
`filespec` 인수에 지정된 파일과 일치하는 파일 이름의 첫 번째 인스턴스에 대한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
intptr_t _findfirst(  
   const char *filespec,  
   struct _finddata_t *fileinfo   
);  
intptr_t _findfirst32(  
   const char *filespec,  
   struct _finddata32_t *fileinfo   
);  
intptr_t _findfirst64(  
   const char *filespec,  
   struct _finddata64_t *fileinfo   
);  
intptr_t _findfirsti64(  
   const char *filespec,  
   struct _finddatai64_t *fileinfo   
);  
intptr_t _findfirst32i64(  
   const char *filespec,  
   struct _finddata32i64_t *fileinfo   
);  
intptr_t _findfirst64i32(  
   const char *filespec,  
   struct _finddata64i32_t *fileinfo   
);  
intptr_t _wfindfirst(  
   const wchar_t *filespec,  
   struct _wfinddata_t *fileinfo   
);  
intptr_t _wfindfirst32(  
   const wchar_t *filespec,  
   struct _wfinddata32_t *fileinfo   
);  
intptr_t _wfindfirst64(  
   const wchar_t *filespec,  
   struct _wfinddata64_t *fileinfo   
);  
intptr_t _wfindfirsti64(  
   const wchar_t *filespec,  
   struct _wfinddatai64_t *fileinfo   
);  
intptr_t _wfindfirst32i64(  
   const wchar_t *filespec,  
   struct _wfinddata32i64_t *fileinfo   
);  
intptr_t _wfindfirst64i32(  
   const wchar_t *filespec,  
   struct _wfinddata64i32_t *fileinfo   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `filespec`  
 대상 파일 사양입니다(와일드카드 문자를 포함할 수 있음).  
  
 `fileinfo`  
 파일 정보 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 성공할 경우 `_findfirst`는 [_findnext](../../c-runtime-library/reference/findnext-functions.md) 또는 `_findclose`에 대한 후속 호출에서 사용될 수 있는 `filespec` 사양과 일치하는 파일 또는 파일 그룹을 식별하는 고유 검색 핸들을 반환합니다. 그렇지 않으면 `_findfirst` -1을 반환 하 고 설정 `errno` 를 다음 값 중 하나입니다.  
  
 `EINVAL`  
 잘못된 매개 변수: `filespec` 또는 `fileinfo`가 `NULL`이었습니다. 또는 운영 체제에서 예기치 않은 오류를 반환했습니다.  
  
 `ENOENT`  
 일치시킬 수 없는 파일 사양입니다.  
  
 `ENOMEM`  
 메모리가 부족합니다.  
  
 `EINVAL`  
 파일 이름 사양이 잘못되었거나 제공된 파일 이름이 `MAX_PATH`보다 컸습니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 잘못된 매개 변수가 전달되면 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다.  
  
## <a name="remarks"></a>설명  
 `_findfirst` 또는 `_findnext` 함수(또는 모든 변형) 사용을 마친 후에는 [_findclose](../../c-runtime-library/reference/findclose.md)를 호출해야 합니다. 그러면 응용 프로그램에서 이러한 함수에 사용된 리소스가 해제됩니다.  
  
 `w` 접두사가 있는 이러한 함수의 변형은 와이드 문자 버전입니다. 이외에는 해당하는 단일 바이트 함수와 동일합니다.  
  
 이러한 함수의 변형은 32비트 또는 64비트 시간 형식과 32비트 또는 64비트 파일 크기를 지원합니다. 첫 번째 숫자 접미사(`32` 또는 `64`)는 시간 형식의 크기를 나타내며, 두 번째 접미사(`i32` 또는 `i64`)는 파일 크기가 32비트 또는 64비트 정수로 표시되는지를 나타냅니다. 어떤 버전이 32비트 및 64비트 시간 형식과 파일 크기를 지원하는지에 대한 자세한 내용은 다음 표를 참조하세요. `i32` 또는 `i64` 접미사가 시간 형식의 크기와 같으면 접미사가 생략되므로 `_findfirst64`도 64비트 파일 길이를 지원하고 `_findfirst32`는 32비트 파일 길이만 지원합니다.  
  
 이러한 함수는 `fileinfo` 매개 변수에 대해 다양한 형태의 `_finddata_t` 구조체를 사용합니다. 구조체에 대한 자세한 내용은 [파일 이름 검색 함수](../../c-runtime-library/filename-search-functions.md)를 참조하세요.  
  
 64비트 시간 형식을 사용하는 변형을 통해 3000년 12월 31일 23:59:59(UTC)까지 파일 생성 날짜를 표현할 수 있습니다. 32비트 시간 형식을 사용하는 변형은 2038년 1월 18일 23:59:59(UTC)까지의 날짜만 나타냅니다. 1970년 1월 1일 자정은 이러한 모든 함수에 대한 날짜 범위의 하한입니다.  
  
 시간 크기를 명시적으로 지정하는 버전을 사용할 특별한 이유가 없다면 `_findfirst` 또는 `_wfindfirst`를 사용하고, 3GB보다 큰 파일 크기를 지원해야 한다면 `_findfirsti64` 또는 `_wfindfirsti64`를 사용하세요. 이러한 함수는 모두 64비트 시간 형식을 사용합니다. 이전 버전에서는 이러한 함수에서 32비트 시간 형식을 사용했습니다. 이것이 응용 프로그램에 대한 새로운 변경 내용일 경우 `_USE_32BIT_TIME_T`를 정의하여 이전 동작으로 되돌릴 수 있습니다. `_USE_32BIT_TIME_T`를 정의하면 `_findfirst`, `_finfirsti64` 및 해당 유니코드 버전에서는 32비트 시간을 사용합니다.  
  
### <a name="time-type-and-file-length-type-variations-of-findfirst"></a>_findfirst의 시간 형식 및 파일 길이 형식 변형  
  
|함수|`_USE_32BIT_TIME_T`가 정의되었나요?|시간 형식|파일 길이 형식|  
|---------------|----------------------------------|---------------|----------------------|  
|`_findfirst`, `_wfindfirst`|정의되지 않음|64비트|32비트|  
|`_findfirst`, `_wfindfirst`|정의됨|32비트|32비트|  
|`_findfirst32`, `_wfindfirst32`|매크로 정의의 영향을 받지 않음|32비트|32비트|  
|`_findfirst64`, `_wfindfirst64`|매크로 정의의 영향을 받지 않음|64비트|64비트|  
|`_findfirsti64`, `_wfindfirsti64`|정의되지 않음|64비트|64비트|  
|`_findfirsti64`, `_wfindfirsti64`|정의됨|32비트|64비트|  
|`_findfirst32i64`, `_wfindfirst32i64`|매크로 정의의 영향을 받지 않음|32비트|64비트|  
|`_findfirst64i32`, `_wfindfirst64i32`|매크로 정의의 영향을 받지 않음|64비트|32비트|  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfindfirst`|`_findfirst`|`_findfirst`|`_wfindfirst`|  
|`_tfindfirst32`|`_findfirst32`|`_findfirst32`|`_wfindfirst32`|  
|`_tfindfirst64`|`_findfirst64`|`_findfirst64`|`_wfindfirst64`|  
|`_tfindfirsti64`|`_findfirsti64`|`_findfirsti64`|`_wfindfirsti64`|  
|`_tfindfirst32i64`|`_findfirst32i64`|`_findfirst32i64`|`_wfindfirst32i64`|  
|`_tfindfirst64i32`|`_findfirst64i32`|`_findfirst64i32`|`_wfindfirst64i32`|  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_findfirst`|\<io.h>|  
|`_findfirst32`|\<io.h>|  
|`_findfirst64`|\<io.h>|  
|`_findfirsti64`|\<io.h>|  
|`_findfirst32i64`|\<io.h>|  
|`_findfirst64i32`|\<io.h>|  
|`_wfindfirst`|\<io.h> 또는 \<wchar.h>|  
|`_wfindfirst32`|\<io.h> 또는 \<wchar.h>|  
|`_wfindfirst64`|\<io.h> 또는 \<wchar.h>|  
|`_wfindfirsti64`|\<io.h> 또는 \<wchar.h>|  
|`_wfindfirst32i64`|\<io.h> 또는 \<wchar.h>|  
|`_wfindfirst64i32`|\<io.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [시스템 호출](../../c-runtime-library/system-calls.md)   
 [파일 이름 검색 함수](../../c-runtime-library/filename-search-functions.md)
