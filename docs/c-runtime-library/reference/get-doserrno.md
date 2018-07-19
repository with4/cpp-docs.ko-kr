---
title: _get_doserrno | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_doserrno
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
- _get_doserrno
- get_doserrno
dev_langs:
- C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7cef2c068fad2f18cb1d11d33e551588800cb64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399571"
---
# <a name="getdoserrno"></a>_get_doserrno

으로 변환 되기 전에 운영 체제에서 반환 된 오류 값을 가져옵니다는 **errno** 값입니다.

## <a name="syntax"></a>구문

```C
errno_t _get_doserrno( 
   int * pValue 
);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
현재 값으로 채워질 정수에 대 한 포인터는 **_doserrno** 글로벌 매크로입니다.

## <a name="return-value"></a>반환 값

경우 **_get_doserrno** 성공 하면 0을 반환 합니다; 실패 한 경우 오류 코드를 반환 합니다. 경우 *pValue* 은 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 반환 **EINVAL**합니다.

## <a name="remarks"></a>설명

**_doserrno** 프로세스 전에 실행을 시작, 전역 매크로 CRT 초기화 하는 동안 0으로 설정 됩니다. 운영 체제 오류를 반환하는 시스템 수준 함수 호출에 의해 반환되는 운영 체제 오류 값으로 설정되며, 실행 중 0으로 다시 설정되지 않습니다. 항상 일반 함수에 의해 반환 된 오류 값을 확인 하는 코드를 작성할 때 **_doserrno** 를 사용 하 여 [_set_doserrno](set-doserrno.md) 함수 호출 전에 합니다. 다른 함수를 호출 덮어쓸 수 있으므로 **_doserrno**를 사용 하 여 값을 확인 **_get_doserrno** 함수 호출 후 바로 합니다.

권장 [_get_errno](get-errno.md) 대신 **_get_doserrno** 휴대용 오류 코드에 대 한 합니다.

가능한 값 **_doserrno** 에 정의 된 \<. h >입니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib>(C++)|\<errno.h>, \<cerrno>(C++)|

**_get_doserrno** Microsoft 확장입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
