---
title: _get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_invalid_parameter_handler
- stdlib/_get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- stdlib/_get_thread_local_invalid_parameter_handler
dev_langs:
- C++
helpviewer_keywords:
- _get_thread_local_invalid_parameter_handler function
- _get_invalid_parameter_handler function
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0302f0ba8e7e34ca60ab73aa0193b48b8352bc77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="getinvalidparameterhandler-getthreadlocalinvalidparameterhandler"></a>_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler

CRT가 잘못된 인수를 발견할 때 호출되는 함수를 가져옵니다.

## <a name="syntax"></a>구문

```C
_invalid_parameter_handler _get_invalid_parameter_handler(void);
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);
```

## <a name="return-value"></a>반환 값

현재 설정된 잘못된 매개 변수 처리기 함수에 대한 포인터이거나, 아무것도 설정되지 않은 경우 null 포인터입니다.

## <a name="remarks"></a>설명

**_get_invalid_parameter_handler** 함수는 현재 설정 가져옵니다 전역 잘못 된 매개 변수 처리기입니다. 전역 잘못된 매개 변수 처리기가 설정되지 않은 경우 null 포인터를 반환합니다. 마찬가지로,는 **_get_thread_local_invalid_parameter_handler** 처리기를 설정한 경우, 호출 스레드가 또는 null 포인터의 현재 스레드 로컬 잘못 된 매개 변수 처리기를 가져옵니다. 전역 및 스레드 로컬 잘못된 매개 변수 처리기를 설정하는 방법에 대한 자세한 내용은 [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)를 참조하세요.

반환된 잘못된 매개 변수 처리기 함수 포인터의 형식은 다음과 같습니다.

```C
typedef void (__cdecl* _invalid_parameter_handler)(
    wchar_t const*,
    wchar_t const*,
    wchar_t const*,
    unsigned int,
    uintptr_t
    );
```

잘못된 매개 변수 처리기에 대한 자세한 내용은 [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)에서 프로토타입을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_get_invalid_parameter_handler**, **_get_thread_local_invalid_parameter_handler**|C: \<stdlib.h><br /><br /> C++: \<cstdlib> 또는 \<stdlib.h>|

**_get_invalid_parameter_handler** 및 **_get_thread_local_invalid_parameter_handler** 함수는 Microsoft 전용입니다. 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[보안이 강화된 CRT 함수 버전](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
