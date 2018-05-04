---
title: _putenv, _wputenv | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _putenv
- _wputenv
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
dev_langs:
- C++
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc7841963584bef19faf60de0112eeea25cb7ffd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="putenv-wputenv"></a>_putenv, _wputenv

환경 변수를 생성, 수정 또는 제거합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)를 참조하세요.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _putenv(
   const char *envstring
);
int _wputenv(
   const wchar_t *envstring
);
```

### <a name="parameters"></a>매개 변수

*envstring*<br/>
환경 문자열 정의입니다.

## <a name="return-value"></a>반환 값

성공 하면 0 또는 오류 발생 시도-1을 반환 합니다.

## <a name="remarks"></a>설명

**_putenv** 함수 새 환경 변수를 추가 하거나 기존 환경 변수 값을 수정 합니다. 환경 변수는 프로세스가 실행되는 환경을 정의합니다(예: 프로그램에 연결할 라이브러리의 기본 검색 경로). **_wputenv** 의 와이드 문자 버전이 **_putenv**; *envstring* 인수를 **_wputenv** 는 와이드 문자 문자열입니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

*envstring* 인수 형식의 문자열에 대 한 포인터 이어야 *varname*=*value_string*여기서 *varname* 은 추가 또는 수정할 환경 변수의 이름 및 *value_string* 은 변수의 값입니다. 경우 *varname* 환경의 일부인 이미 해당 값으로 대체 됩니다 *value_string*고, 그렇지 않으면, 새 *varname* 변수 및 해당 *value_string*  값은 환경에 추가 됩니다. 빈을 지정 하 여 환경에서 변수를 제거할 수 *value_string*만 지정 하 여 즉, *varname*= 합니다.

**_putenv** 및 **_wputenv** 현재 프로세스에 로컬인 환경에만 적용 되며, 명령 수준 환경을 수정에 사용할 수 없습니다. 즉, 이러한 함수는 운영 체제가 프로세스에 대해 만드는 환경 세그먼트가 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조에서만 작동합니다. 현재 프로세스가 종료되면 환경이 호출 프로세스의 수준(대부분의 경우 운영 체제 수준)으로 되돌아갑니다. 하지만 수정된 된 환경에서 만든 모든 새로운 프로세스에 전달할 수 있습니다 **_spawn**, **_exec**, 또는 **시스템**, 가져오고, 이러한 새로운 프로세스 에서추가한새항목 **_putenv** 및 **_wputenv**합니다.

환경 항목을 직접 변경 하지 마십시오: 대신를 사용 하 여 **_putenv** 또는 **_wputenv** 변경할 수 있습니다. 특히,의 요소를 직접 해제는 **_environ** 글로벌 배열 해결 하는 잘못 된 메모리 발생할 수 있습니다.

**getenv** 및 **_putenv** 전역 변수를 사용 하 여 **_environ** ; 환경 테이블에 액세스 하려면 **_wgetenv** 및 **_wputenv** 사용 **_wenviron**합니다. **_putenv** 및 **_wputenv** 의 값이 변경 **_environ** 및 **_wenviron**, 따라서 무효화는 **_envp** 인수를 **주** 및 **_wenvp** 인수를 **wmain**합니다. 따라서 것이 안전 하 게 사용 하 여 **_environ** 또는 **_wenviron** 환경 정보에 액세스할 수 있습니다. 관계에 대 한 자세한 내용은 **_putenv** 및 **_wputenv** 전역 변수 참조 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)합니다.

> [!NOTE]
> **_putenv** 및 **_getenv** 함수 패밀리는 스레드로부터 안전 하지 않습니다. **_getenv** 하는 동안 문자열 포인터를 반환할 수 **_putenv** 임의 오류가 발생 하는 문자열을 수정 합니다. 이러한 함수에 대한 호출은 동기화해야 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

샘플을 사용 하는 방법에 대 한 **_putenv**, 참조 [getenv, _wgetenv](getenv-wgetenv.md)합니다.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
