---
title: set_unexpected(CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- set_unexpected
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
apitype: DLLExport
f1_keywords:
- set_unexpected
dev_langs:
- C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0c97f46a66a26f107061676dba313b068e9aebf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="setunexpected-crt"></a>set_unexpected(CRT)

**unexpected**로 호출하는 자체 종료 함수를 설치합니다.

## <a name="syntax"></a>구문

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>매개 변수

*unexpFunction*<br/>
대체를 작성 하는 함수에 대 한 포인터는 **예기치 않은** 함수입니다.

## <a name="return-value"></a>반환 값

이전 종료 함수에 대 한 포인터에 의해 등록 반환 **_set_unexpected** 이전 함수는 나중에 복원할 수 있도록 합니다. 이전 함수가 설정되지 않은 경우 반환 값은 기본 동작을 복원하는 데 사용되며 이 값은 NULL일 수 있습니다.

## <a name="remarks"></a>설명

**set_unexpected** 설치 함수 *unexpFunction* 호출한 함수로 **예기치 않은**합니다. **예기치 않은** 현재 c + + 예외 처리 구현에서 사용 되지 않습니다. **unexpected_function 형식** 형식이 EH에 정의 되어 있습니다. 사용자 정의 예기치 않은 함수에 대 한 포인터로 H *unexpFunction* 반환 하는 **void**합니다. 사용자 지정 *unexpFunction* 함수는 호출자에 반환 되지 해야 합니다.

```cpp
typedef void ( *unexpected_function )( );
```

기본적으로 **예기치 않은** 호출 **종료**합니다. 자체 종료 함수를 작성 하 고 호출 하 여이 기본 동작을 변경할 수 있습니다 **set_unexpected** 의 인수로 서 함수 이름으로 합니다. **예기치 않은** 에 대 한 인수로 주어진 마지막 함수를 호출 **set_unexpected**합니다.

사용자 지정 종료 함수를 호출 하 여 설치와 달리 **set_terminate**, 내에서 예외가 throw 될 수 *unexpFunction*합니다.

다중 스레드 환경에서 unexpected 함수는 각 스레드에 대해 개별적으로 유지 관리됩니다. 각 새 스레드는 자체 unexpected 함수를 설치해야 합니다. 따라서 각 스레드는 자체 unexpected 처리를 담당합니다.

Microsoft c + + 예외 처리의 현재 구현에서 **예기치 않은** 호출 **종료** 기본적으로 및 예외 처리 런타임 라이브러리에 의해 호출 되지 않습니다. 호출을 특정 소용이 없습니다 **예기치 않은** 대신 **종료**합니다.

단일 **set_unexpected** 처리기에 대 한 모든 동적으로 연결 된 Dll 또는 Exe; 호출 하는 경우에 **set_unexpected** 처리기 다른 대체 될 수 있습니다 또는 설정한 처리기를 대체 하는 다른 DLL 또는 EXE 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**set_unexpected**|\<eh.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_unexpected](get-unexpected.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
