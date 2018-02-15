---
title: _splitpath_s, _wsplitpath_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wsplitpath_s
- _splitpath_s
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
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
dev_langs:
- C++
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9baa71ca1a3d624c08df8ff1cbd14a9386e1b83d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s
경로 이름을 구성 요소로 분해합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _splitpath_s(  
   const char * path,  
   char * drive,  
   size_t driveNumberOfElements,  
   char * dir,  
   size_t dirNumberOfElements,  
   char * fname,  
   size_t nameNumberOfElements,  
   char * ext,   
   size_t extNumberOfElements  
);  
errno_t _wsplitpath_s(  
   const wchar_t * path,  
   wchar_t * drive,  
   size_t driveNumberOfElements,  
   wchar_t *dir,  
   size_t dirNumberOfElements,  
   wchar_t * fname,  
   size_t nameNumberOfElements,  
   wchar_t * ext,  
   size_t extNumberOfElements  
);  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _splitpath_s(  
   const char *path,  
   char (&drive)[drivesize],  
   char (&dir)[dirsize],  
   char (&fname)[fnamesize],  
   char (&ext)[extsize]  
); // C++ only  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _wsplitpath_s(  
   const wchar_t *path,  
   wchar_t (&drive)[drivesize],  
   wchar_t (&dir)[dirsize],  
   wchar_t (&fname)[fnamesize],  
   wchar_t (&ext)[extsize]  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `path`  
 전체 경로입니다.  
  
 [out] `drive`  
 뒤에 콜론(`:`)이 붙은 드라이브 문자입니다. 드라이브 문자가 필요하지 않은 경우 이 매개 변수에 대해 `NULL`을 전달할 수 있습니다.  
  
 [in] `driveNumberOfElements`  
 싱글바이트 문자 또는 와이드 문자 단위의 `drive` 버퍼 크기입니다. `drive`이 `NULL`이면 이 값은 0이어야 합니다.  
  
 [out] `dir`  
 후행 슬래시를 포함한 디렉터리 경로입니다. 슬래시(`/`), 백슬래시(`\`) 또는 두 슬래시를 모두 사용할 수 있습니다. 디렉터리 경로가 필요하지 않은 경우 이 매개 변수에 대해 `NULL`을 전달할 수 있습니다.  
  
 [in] `dirNumberOfElements`  
 싱글바이트 문자 또는 와이드 문자 단위의 `dir` 버퍼 크기입니다. `dir`이 `NULL`이면 이 값은 0이어야 합니다.  
  
 [out] `fname`  
 확장명이 없는 기본 파일 이름입니다. 파일 이름이 필요하지 않은 경우 이 매개 변수에 대해 `NULL`을 전달할 수 있습니다.  
  
 [in] `nameNumberOfElements`  
 싱글바이트 문자 또는 와이드 문자 단위의 `fname` 버퍼 크기입니다. `fname`이 `NULL`이면 이 값은 0이어야 합니다.  
  
 [out] `ext`  
 선행 마침표(**.**)를 포함한 파일 이름 확장명입니다. 파일 이름 확장명이 필요하지 않은 경우 이 매개 변수에 대해 `NULL`을 전달할 수 있습니다.  
  
 [in] `extNumberOfElements`  
 싱글바이트 문자 또는 와이드 문자 단위의 `ext` 버퍼 크기입니다. `ext`가 `NULL`이면 이 값은 0이어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|조건|반환 값|  
|---------------|------------------|  
|`path`가 `NULL`인 경우|`EINVAL`|  
|`drive`가 `NULL`이고 `driveNumberOfElements`가 0이 아닌 경우|`EINVAL`|  
|`drive`이 `NULL`이 아니고 `driveNumberOfElements`가 0인 경우|`EINVAL`|  
|`dir`가 `NULL`이고 `dirNumberOfElements`가 0이 아닌 경우|`EINVAL`|  
|`dir`이 `NULL`이 아니고 `dirNumberOfElements`가 0인 경우|`EINVAL`|  
|`fname`가 `NULL`이고 `nameNumberOfElements`가 0이 아닌 경우|`EINVAL`|  
|`fname`이 `NULL`이 아니고 `nameNumberOfElements`가 0인 경우|`EINVAL`|  
|`ext`가 `NULL`이고 `extNumberOfElements`가 0이 아닌 경우|`EINVAL`|  
|`ext`가 `NULL`이 아니고 `extNumberOfElements`가 0인 경우|`EINVAL`|  
  
 이러한 조건 중 하나라도 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
 버퍼가 너무 짧아 결과를 저장할 수 없으면 이러한 함수는 모든 버퍼를 비워 빈 문자열로 만들고 `errno`를 `ERANGE`로 설정한 후에 `ERANGE`를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_splitpath_s` 함수는 경로를 4개 구성 요소로 분해합니다. `_splitpath_s`는 현재 사용 중인 멀티바이트 코드 페이지에 따라 멀티바이트 문자 시퀀스를 인식하며 멀티바이트 문자열 인수를 자동으로 적절히 처리합니다. `_wsplitpath_s`는 `_splitpath_s`의 와이드 문자 버전이며, `_wsplitpath_s`에 대한 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 전체 경로의 각 구성 요소는 별도의 버퍼에 저장됩니다. 매니페스트 상수 `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` 및 `_MAX_EXT`(STDLIB.H에 정의됨)는 각 파일 구성 요소의 허용 가능한 최대 크기를 지정합니다. 해당 매니페스트 상수보다 큰 파일 구성 요소가 있으면 힙이 손상됩니다.  
  
 다음 표에는 매니페스트 상수의 값이 나와 있습니다.  
  
|name|값|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 전체 경로에 파일 이름 등의 구성 요소가 포함되어 있지 않으면 `_splitpath_s`는 해당 버퍼에 빈 문자열을 할당합니다.  
  
 C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_splitpath_s`|\<stdlib.h>|  
|`_wsplitpath_s`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)