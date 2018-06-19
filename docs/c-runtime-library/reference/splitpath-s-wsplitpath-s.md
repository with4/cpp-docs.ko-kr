---
title: _splitpath_s, _wsplitpath_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5fd1407aa6c2b7630e0720eeec179ca27e7d31a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417434"
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s

경로 이름을 구성 요소로 분해합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_splitpath, _wsplitpath](splitpath-wsplitpath.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
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

### <a name="parameters"></a>매개 변수

*path*<br/>
전체 경로입니다.

*드라이브*<br/>
드라이브 문자를 뒤에 콜론 (**:**). 전달할 수 **NULL** 드라이브 문자 필요 하지 않은 경우이 매개 변수에 대 한 합니다.

*driveNumberOfElements*<br/>
크기는 *드라이브* 단일 바이트 또는 와이드 문자 버퍼입니다. 경우 *드라이브* 은 **NULL**,이 값이 0 이어야 합니다.

*dir*<br/>
후행 슬래시를 포함한 디렉터리 경로입니다. 슬래시 ( **/** ), 백슬래시 ( **\\** ), 또는 둘 다 사용할 수 있습니다. 전달할 수 **NULL** 디렉터리 경로 필요 하지 않은 경우이 매개 변수에 대 한 합니다.

*dirNumberOfElements*<br/>
크기는 *dir* 단일 바이트 또는 와이드 문자 버퍼입니다. 경우 *dir* 은 **NULL**,이 값이 0 이어야 합니다.

*fname*<br/>
확장명이 없는 기본 파일 이름입니다. 전달할 수 **NULL** 파일 이름이 필요 하지 않은 경우이 매개 변수에 대 한 합니다.

*nameNumberOfElements*<br/>
크기는 *fname* 단일 바이트 또는 와이드 문자 버퍼입니다. 경우 *fname* 은 **NULL**,이 값이 0 이어야 합니다.

*ext*<br/>
파일 이름 확장명을 선행 기간을 포함 하 여 (**.**). 전달할 수 **NULL** 파일 이름 확장자가 필요 하지 않은 경우이 매개 변수에 대 한 합니다.

*extNumberOfElements*<br/>
크기 *ext* 단일 바이트 또는 와이드 문자 버퍼입니다. 경우 *ext* 은 **NULL**,이 값이 0 이어야 합니다.

## <a name="return-value"></a>반환 값

성공 시 0이고, 실패 시 오류 코드입니다.

### <a name="error-conditions"></a>오류 조건

|조건|반환 값|
|---------------|------------------|
|*경로* 은 **NULL**|**EINVAL**|
|*드라이브* 은 **NULL**, *driveNumberOfElements* 0이 아닌|**EINVAL**|
|*드라이브* 이 아닌**NULL**, *driveNumberOfElements* 0|**EINVAL**|
|*dir* 은 **NULL**, *dirNumberOfElements* 0이 아닌|**EINVAL**|
|*dir* 이 아닌**NULL**, *dirNumberOfElements* 0|**EINVAL**|
|*fname* 은 **NULL**, *nameNumberOfElements* 0이 아닌|**EINVAL**|
|*fname* 이 아닌**NULL**, *nameNumberOfElements* 0|**EINVAL**|
|*ext* 은 **NULL**, *extNumberOfElements* 0이 아닌|**EINVAL**|
|*ext* 이 아닌**NULL**, *extNumberOfElements* 0|**EINVAL**|

이러한 조건 중 하나라도 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 허용 된, 이러한 함수 설정 **errno** 를 **EINVAL** 다음 다시 돌아와 **EINVAL**합니다.

이러한 함수에 빈 문자열을 설정 하는 모든 버퍼가 지우기 결과 저장 하기에 너무 짧은 경우 버퍼의 **errno** 를 **ERANGE**, 다음 다시 돌아와 **ERANGE**합니다.

## <a name="remarks"></a>설명

**_splitpath_s** 함수를 4 개의 구성 요소로 경로 중단 합니다. **_splitpath_s** 자동으로에서 현재 사용 중인 멀티 바이트 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 하며 멀티 바이트 문자열 인수를 적절 하 게 처리 합니다. **_wsplitpath_s** 의 와이드 문자 버전이 **_splitpath_s**;에 대 한 인수 **_wsplitpath_s** 는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

전체 경로의 각 구성 요소는 별도 버퍼에 저장 됩니다. 매니페스트 상수 **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME**, 및 **_MAX_EXT** (STDLIB에 정의 합니다. H) 각 파일 구성 요소에 대 한 최대 허용 크기를 지정 합니다. 해당 매니페스트 상수보다 큰 파일 구성 요소가 있으면 힙이 손상됩니다.

다음 표에는 매니페스트 상수의 값이 나와 있습니다.

|이름|값|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

전체 경로 (예를 들어 filename) 구성 요소가 포함 되어 있지 않으면 **_splitpath_s** 일치 하는 버퍼를 빈 문자열을 할당 합니다.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
